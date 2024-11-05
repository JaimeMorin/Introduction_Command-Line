# Introduction to Command-Line Tools

## 1. Set Unix terminal
Windows Subsystem for Linux (WSL)
```
https://learn.microsoft.com/en-us/windows/wsl/install 
```
## 2. Access to the server
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
## 3. Basic commands 

### Set Up and Processes 
Before starting intensive processes, you can check graphically how busy the server is. Press **"Q"** to quit the viewer. 
```
htop
```
Stop a process
```
Ctrl + Z
```
Terminate current script 
```
Ctrl + C
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
List all files, sizes, and permissions.
```
ls -lh
```
List all documents with a given description (Example: ending on jpg), on this directory.
```
ls *.gz
```
List all documents with a given description (_example: ending on .gz_), even within subfolders.
```
find . -name *.gz
```
Create a new file; you can create and see documents using **nano** or options such as **touch**
```
nano nameoffile
```
### Files Management 

Unzip a **".gz"** file 
```
gunzip document.gz
```
Copy a **file** to a certain **directory**
```
cp file Path/to/directory/
```
Copy a file **from the server to your local computer**. Open the terminal and input locally: 
```
# scp user_id@example.server.direction.no:/path/to/source/document/name_of_file path/to/local/folder/
```
Copy a file **from your computer to your server**.
```
scp /Path/to/file/Desktop/name_of_file user_id@example.server.direction.no:/path/to/source/document/
```
Send a document via email | A = Attached 
```
echo "Message Body Here" | mail -s "Subject Here" example_user@gmail.com -A document.txt
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




