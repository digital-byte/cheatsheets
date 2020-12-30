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
###### exapmles
    ```
    find / -name <foo.txt>
    ```
### Docker
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
