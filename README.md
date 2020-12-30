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
