# rsync

- touch test{1..10}
- rsync -a src dest
- rsync -a src/ dest
- ls -al dest

## Local update

- rsync -av src/ dest (update)
- ls -al dest

## Remote Update

- mkdir -p rsync/des
- chmod -R 777 rsync
- rsync -azP ~/rsync/src/ jsh@192.168.0.72:~/rsync/dest
