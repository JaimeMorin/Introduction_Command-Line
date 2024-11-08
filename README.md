# Introduction to Command-Line Tools

## 1. Set Unix terminal
Ubuntu 
```
https://ubuntu.com/
```
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

Unzip a **".gz"** file 
```
gunzip document.gz
```
Copy a **file** to a certain **directory**
```
cp file Path/to/directory/
```
### Downloading or sending data
Copy a file **from the server to your local computer**. Open the terminal and input locally: 
```
scp user_id@example.server.direction.no:/path/to/source/document/name_of_file path/to/local/folder/
```
Copy a file **from your computer to your server**.
```
scp /Path/to/file/Desktop/name_of_file user_id@example.server.direction.no:/path/to/source/document/
```
Send a document via email | A = Attached 
```
echo "Message Body Here" | mail -s "Subject Here" example_user@gmail.com -A document.txt
```
Create a Symbolic Link (Shortcut or Direct access). Useful for organizing data without duplicating it 
```
ln -s /path/to/source/directory path/to/target/location/for/folder/link
```


### Text Data Management 
Print the first **X** lines (e.g. four lines) of a **file**
```
head -n 4  nameofthefile
```

**List** all documents or folders from a directory | then **split** the name of the document using a separator, and **print** the specified field 
1. **Text Delimitation**: Space (no need to specify), underscore -F'_' 
2. **Print**: First line _$1_; Last line _$NF_; Second-to-last _$NF-1_
```
ls path/to/folder/ | awk -F'_' '{print $NF}' 
ls path/to/folder/ | awk -F'_' '{print $NF-1}' 
ls path/to/folder/ | awk '{print $NF-1}'
ls path/to/folder/ | awk '{print $1}' 
```
You can specify a specific type of file like here
```
ls *bam | awk -F'_' '{print $NF}'
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

## 4. awk
awk is a tool for processing and analyzing text data, handy for handling structured data like tables and log files. It reads each line of a file or input, splits it into fields following separator criteria (space, comma, underscore), and lets you manipulate or extract those specific extracts. For example, if you have **data.txt** like this: 
```
James  25  Engineer
Jorde  30  Doctor
Vania  22  Artist
```
You can print the second column in data.txt (_space delimitation is the default_)
```
awk '{print $2}' data.txt
```
and you will get
```
25
30
22
```


## 5. grep
Grep is similar but mainly used for searching and filtering text based on patterns (Like a SEARCH function). It is convenient for working with fasta files. Let's suppose you have a fasta file, e.g., "scaffolds.fasta". There are many things you can do
```
>NODE_01
ATGCGTACGATCGACTGACG...
...
>NODE_02
TACGATCGTACGTAGCATCG...
...
>NODE_03
TACGATCGTACGTAGCATCG...
....
.
.
.
```

Find All Headers: Search for lines starting (^) by ">"
```
grep "^>" scaffolds.fasta
```
Count (-c) the Number of Sequences in a FASTA file
```
grep -c "^>" sequences.fasta
```
Print the matching query line and the next line. _Useful when it is a single-line fasta file_
```
grep -A 1 NODE_12 scaffolds.fasta
```
Print the line with the query (NODE_12) and the 10 lines after (-A)
```
grep -A 10 NODE_12 scaffolds.fasta
```
List Only the IDs of Sequences with a Specific Keyword (e.g., mitochondria). The second grep is second filter to get only headers (>) 
```
grep "mitochondria" scaffolds.fasta | grep "^>" 
```


