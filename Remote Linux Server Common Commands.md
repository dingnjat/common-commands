1. Connect to server via ssh

`ssh -l [username] [ip address] -> then enter password of username`

2. Copy file from local to server

`scp [file-path] [username]@[ip address]:[directory or file path(rename file) on server]`

3. Copy file from server to local

`scp [username]@[ip address]:[file-path] [local dir or file path]`

4. Copy multiple files from local to server

`scp [file-path-1] [file-path-2] [username]@[ip address]:[directory on server]`

5. Copy dir from local to server

`scp -r [local dir] [username]@[ip address]:[remote dir]`

6. Copy dir from server to local

`scp -r [username]@[ip address]:[remote dir] [local dir]`

