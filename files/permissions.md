
# Permissions

- rwx:rwx:rwx [User/Grop/Others] => [u/g/o]
- rwx [Read/Write/Execute]

## chmod (change file mode bits)

- chmod 777 filename
- chmod u+r filename
- chmod u-r filename
- chmod g+w filename
- chmod g-w filename
- chmod o+x filename
- chmod o-x filename

## chown (change file owner and group)

- sudo chown username filename
- chown username filename (root permission)
- chown :usergroup filename
- chown username:usergroup filename

## chgrp (change group ownership)

- chgrp usergroup filename
- chgrp -R usergroup filename
