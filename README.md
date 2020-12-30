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
