# Commandline cheatsheet
Helpful commands and options to remember

### vi 
  ```
  b     Back one word
  cc    Replace current line
  cw    Replace current word
  dw    Delete current word
  dd    Delete current line
  w     Forward one word
  yy    Yank
  pp    Put
  :q!   Quit without save
  :wq   Quit with save
  /     Search forward
  ?     Search backward
  n     Find next occurrence
  u     undo last change, can be repeated
  U     undo all changes on line
  ```

### find
  ```
  -exec   Execute specified command for each file found
  -name   Search by filename
  -size   Search by file size
  -type   Search by file type
  ```
###### find examples
  ```
  # Find file with the name foo.txt
  find / -name <foo.txt>
  # Find script named foo.sh and execute it
  find / -name foo.sh 2>&1 -exec {} \;
  # Find script named foo.sh and execute it but ignore "Permission Denied" search warnings
  find / -name foo.sh 2>&1 -exec {} \; | grep -v "Permission denied"
  ```
    
### docker
   ```
   # List all containers
   docker ps -aq
   # Get only container IDs
   docker container ls | awk '{print $1}'
   # Stop all containers
   docker stop $(docker ps -aq)
   # Remove all containers
   docker rm $(docker ps -aq)
   # Remove all images
   docker rmi $(docker images -q)
   ```
Log in with docker default user  
`docker exec -it <dockerid> /bin/bash`

Log in force to be root  
`docker exec -u root -it <dockerid> /bin/bash`

Tail logs for your container  
`docker logs -f <dockerid> --tail 200`

Show mem/cpu usage of your container  
`docker stats --no-stream=true $(docker ps -q) | sed -n '1!p' | sed 's/ \+/,/g' | awk -F',' '{print $1","$2","$3","$7}'`

show the processes running in your container  
`docker top <dockerid> | sed -n '1!p' | sed 's/ \+/ /g'`

