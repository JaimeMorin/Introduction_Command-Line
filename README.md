# Introduction to Command-Line Tools

## Set Unix terminal
Windows Subsystem for Linux (WSL)
```
https://learn.microsoft.com/en-us/windows/wsl/install 
```
## Access to the server
Useful tutorials 
```
http://evomics.org/learning/unix-tutorial/ 
```
Access the working server using the Secure Shell (SSH) Protocol. 
```
ssh user_id@example.server.direction.no
```
Change your passport 
```
smbpasswd 
```
## Basic commands 

### Set Up
Before starting intensive processes, you can check graphically how busy the server is. Press **"Q"** to quit the viewer. 
```
htop
```
If you need to create a shortcut, you can use **alias**. 
```
alias jaime='cd /path/to/my/folder/jaime/'
```

### Files
List all files
```
ls
```
List all files, sizes, and permissions
```
ls -lh
```
List all documents with a given description (Example: ending on jpg), on this directory.
```
ls *.gz
```
List all documents with a given description (_example: ending on .gz_), even within subfolders.
```
find . -name "*.gz"
```

Unzip a **".gz"** file 
```
gunzip document.gz
```

Create a new file; you can create and see documents using **nano** or options such as **touch**
```
nano nameoffile
```


### Folders
Create a folder
```
mkdir nameofdirectory 
```
Remove empty folder
```
rm -d nameofdirectory  
```
Remove non-empty folder
```
rm -r nameofdirectory 
```




