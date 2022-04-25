# Shell

- echo $0
- ls /bin | grep bash
- vi backup.sh
- chmod u+x backup
- chmod +x backup
- ./backup

## Shell Script

```bash
#!/bin/bash
if ! [ -d bak ]; then
  mkdir bak
fi

cp *.log bak
```
