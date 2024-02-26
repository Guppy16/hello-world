# Useful Bash Commands

Get the total file size of `<FILE NAME>` in all sub-directories:

```bash
du -h -BM -a| grep <FILE NAME> | awk '{sum += $1} END {print sum}'
```
