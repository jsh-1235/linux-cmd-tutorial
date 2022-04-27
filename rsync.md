# rsync

- touch test{1..10}
- rsync -a src dest
- rsync -a src/ dest
- ls -al dest
- rsync -av src/ dest (update)
- ls -al dest
- chmod -R 777 rsync
- rsync -azP ~/rsync/src/ jsh@192.168.0.72:~/rsync/dest

- ssh-keygen
- cd ~
- cd .ssh
- ssh-copy-id jsh@192.168.0.72
