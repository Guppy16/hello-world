# Notes from Python Testing With Pytest

Link to book:

[Errata](https://devtalk.com/books/python-testing-with-pytest-second-edition/errata) 

[View the source code in this page](https://pragprog.com/titles/bopytest2/python-testing-with-pytest-second-edition/)

### General

This book assumes that the application code is installed as a package. You may need other ways to get the test code to see the application code. Check out Chaper 12, pg 165.

`pathlib.Path` objects are the standard way to represent file system paths as documented [here](https://docs.python.org/3/library/pathlib.html#basic-use).

The `packaging` package seems to have some useful utilities

The [`faker`](https://faker.readthedocs.io/en/master/) package is useful for generating fake data.

### Chap 1

pytest can discover tests, as long as the path, filename or classname contains "test" at the beginning (or end) of the filename. This is conigurable. Interestingly, chap 2 mentions that classes should only be used to group tests, because anything fancier (e.g. using inheritance) will get confusing.
Tests can alse be run be selecting them: `pytest -k "Substring and/(or)/not substring..."`

- `pytest --tb=no` shows a traceback
- `-s` or `--capture=no` shows print statements for passing tests
- `-r` reason for test result. Default `-rfE` (fail and Error). `-ra` (all except pass)

The possible outcomes of a test are:
- Passed, failed, skipped, xfail, xpass, error

### Chap 2

Reasons to fail a test:
- Assertion Error
- pytest.fail()
- Exceptions

pytest uses **assert rewriting** to intercept assert calls and replace them with something that can give you much more verbose infromation. Note that assert rewriting is only done to `conftest.py` and `test` files as per the [docs](https://docs.pytest.org/en/latest/how-to/assert.html#assertion-introspection-details)

**Assertion Helper** functions can be used to wrap complicated assertion checks such as `assert_identical(c1, c2)`. You can also use `__tracebackhide__ = True` so that the function doesn't appear in the traceback display (for visual purposes).

**Expected Exceptions** can be handled as shown below. This test expects a specific exception and will fail if that is _not_ raised. Also, the error message can be checked using a regular expression or by checking the exception info.
```python
def test_divide_by_zero_error():
    match_regex = r'.*'
    with pytest.raises(ZeroDivisionError, match=match_regex) as exc_info:
        1 / 0
    assert "ZeroDivisionError" in str(exc_info.value)
```

Follow the Arrange-Act-Assert method aka Given-When-Then.


### Chap 3: pytest fixtures

Fixtures are useful to setup a state before tests are run and teardown the resources used after all the tests are performed. 
Use the `@pytest.fixture()` decorator. You must put the fixture method name inside the test function that you want to use it in.
Assertion in fixture methods reports an "Error" result in pytest. This helps diffrentiatie between exceptions in fixtures and actual tests. 
Inside this fixture method, use 
```python
with ...
    [setup]
    yield x
    [teardown]
```
The contex manager ensures that both parts either side of the `yield` are called no matter the test result. 


Use `pytest --setup-show [test.py]` to view the setup and teardown phase for debugging. This will also show you the scope of the fixture methods (default to function). 
If you have a slow resource, it can be beneficial to change the scope: `@pytest.fixture(scope="module")`. 
The various scopes are: `function, class, module, package, session`. A bit tricker to setup is using dynamc fixtures, autouse. Note that fixtures can use other fixtures, but the scope must be the same or higher level! E.g. a session scope fixture cannot use a function scope fixture.

Note that fixtures can be renamed.
Use `conftest.py` to place any fixtures that are shared between multiple files. Note that you shouldn't import this file!
There can be a `conftest.py` file in each directory; to view all the fixtures use `pytest --fixtues -v` (you can supply a dir/file). List the fixtures by test using `pytest --fixtures-per-test [test.py::test]`.


Note that test functions shouldn't depend on the order they are run. Hence use fixture methods with the `function` scope to reset anything as required.

### Chap 4: [Builtin fixtures](https://docs.pytest.org/en/latest/reference/fixtures.html)

Use `pytest --basetemp=mydir` to specifiy the base dir for temporary dirs.

`tmp_path` - (function scope) returns a `Path` object:
```Python
def test_tmp_path(tmp_path):
    f = tmp_path / "file.txt"
    ...
```

`tmp_path_factory` - (session-scope) returns a `TempPathFactory` object that can make many tamporary dirs using `mktemp()`

`capsys` - capturing output. This is useful to test CLI directly as opposed to using `import subprocess...` (see page 51/52 for more details). It can also be used to disable output capture on passing tests:
```python
def test_disabled(capsys):
    with capsys.disabled():
        print("\ncapsys disabled print")
```
Similar fitures are: 
`capfd` - file descriptors 1 and 2
`capsysbinary` - captures bytes
`capfdbinary` - bytes on file descriptors 1 and 2
`caplog` - captures output written with the logging package

`monkeypatch` - changing the environment / application code ("lightweight form of mocking"). E.g can be used to set the environment variable for a temp dir.

`cache` - store and retreive vales across pytest runs

`record_property record_testsuite_property` - add extra properties to the test / suite, which is useful for adding data to an XML report for CI tools

`recwarn` - test warning msgs

`request` - provide information on the executing test function. (But?) most commonly used during ficture parametrization

### Chap 5: Parametrization

_Motivation_: without parametrization, you could have a list that you want to test. This leads to the following problems: 
- only one test case is reported
- if one of the cases fails, we need more debugging info
- if one case fails, the other cases aren't tested.



**Paremtrizing functions**

```python
@pytest.mark.parametrize(
    "arg1, arg2",
    [
        ("arg1", "arg2"),   # Case 1
        ("arg1", "arg2")    # Case 2
    ]
)
def test(arg1, arg2):
    ...
```

**Parametrizing fixtures**

```python
@pytest.fixture(params=["p1", "p2",])
def fixture_foo(request):
    return request.param

def test(fixture_foo):
    # Use fixture_foo here
```

This is useful for:
- setup and teardown code is required for each parameter
- multiple tests use the same parameters


**Hook function**: `pytest_generate_tests`

This uses the `metafunc` object in a function to add functionality:
```python
def pytest_generate_tests(metafunc):
    if "start_state" in metafunc.fixturenames:
        metafunc.parametrize("start_state", ["p1", "p2"])

def test(start_state):
    ...
```

`metafunc` is very powerful because it can be used to read command line flags, which can be used for certain types of testing. It can also be used to paramtrise relate parametrs at the same time, even if they're used in separate functions.

Note that the same rules apply for selecting a subset of tests when using the `-k` parameter. 

Note that you can't parametrise the same parameter more than once.

### Chap 6: Markers

_Markers_ are a way to tell pytest that there's something special about this test. 
Syntax: `@pytest.mark.[maker]`. List all the markers and desc in terminal using: `pytest --markers`.

- `paremtrize(parameters)`: 
- `skip(reason=None)` - marker skips the test with an optional reason
- `skipif(condition, ..., *, reason)` - skips test if any condition is true
- `xfailxfail(condition, ..., *, reason, run=True, raises=None, strict=xfail_strict)` - expect the test to fail by raising one of the Exceptions mentioned. 

- `slow` - pytest will skip these when in a hurry
- `smoke` - run these as the first stage (Note that this is a custom test)
- `filterwarnings(warning)` - adds a warning filter to the test
- `usefixtures(f1, f2)` - marks the test as needing all the specified fixtures??

Custom _markers_ can be added to `pytest.ini` like shown below. Run specific markers using: `pytest -m [marker]`. Note that specific markers can also be selected to run in a format similar to using the `-k` paramter!
```ini
[pytest]
markers = 
    smoke: subset of tests
addopts = 
    --strict-markers        # Optional paremter so that an error is raised if an unknown marker is used in the tests
    -ra         # reason for the result if test not passed

xfail_strict = true         # Ensure that xfail tests have to fail
```

Markers can be used on different scales:
- test module: `pytest = [pytest.mark.m1, pytest.mark.m2]` add this line in the file
- class: `@pytest.mark.smoke` add this on top of the class
- functions
- test cases: `pytest.param(p, marks=pytest.mark.m)` substitute this for a parameter

**Markers with fixtures**

This is useful if you want to paremtrise a fixture based on a marker. 
E.g. The starting state of a database could have N cards. 
In the fixture, use `request.node` to access the test function. 
Use `request.node.get_closest_marker(<marker>)` to get the marker closest to the function (remembering that markers can be added at different scopes). 
Access the parameters using `.args` or `.kwargs`.

### Chap 7: Strategy

Very important to tets user visible functionality: security, performance, loading requests, input validation

Priortise features based on these factors: recent, core, risk, problematic, expertise.

Start with a non-trivial "happy path" test case. Look at the test cases that represent: interesting set of inputs, starting states, end states, or all possoble error states

Knowing what each file / layer does, can be useful to remove redundant tests. For example, creating thin layers for a CLI / database means that most of the testing can be focused on the API layer.

