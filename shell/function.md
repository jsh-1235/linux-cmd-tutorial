# function

## Shell Script

```bash
#!/bin/bash

sum() {
  echo "parameter: $1 $2"
  #return $(($1+$2))
  return `expr $1 + $2`
}

sum 5 8

echo "Return value : $?"
```

```bash
#!/bin/bash
echo "===================================="
echo $*
echo "===================================="

sum() {
  echo "parameter: $1 $2"
  return `expr $1 + $2`
}

sum $1 $2

echo "sum = $?"
```
