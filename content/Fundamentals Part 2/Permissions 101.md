
```shell
ls -l
```

this command will list down things like that 

![[Pasted image 20260105162710.png|90%]]


>[!note]
>![[Pasted image 20260105162903.png|90%]]

![[Pasted image 20260105163238.png]]


![[Pasted image 20260121140141.png]]


![[Pasted image 20260121140510.png]]

For **Directories (folders)**

| Permission    | What it allows                                         | Example commands you can run                                        |
| ------------- | ------------------------------------------------------ | ------------------------------------------------------------------- |
| `r` (read)    | List names inside folder                               | `ls folder/`                                                        |
| `w` (write)   | Create / delete / rename entries (files _and_ folders) | `touch a.txt`, `mkdir newdir`, `rm a.txt`, `rmdir olddir`, `mv a b` |
| `x` (execute) | Enter folder & access items                            | `cd folder/`, `cat folder/file.txt`                                 |
Important combos for folders

|Permission|What happens|
|---|---|
|`r-x`|You can **see file names** and **enter folder**, but cannot create/delete|
|`-wx`|You can **enter folder & create/delete**, but cannot list names|
|`r--`|You can **see names**, but **cannot cd into folder**|
|`--x`|You can **cd into folder**, but cannot list names|

#### for files

|Permission|What it allows|Example commands|
|---|---|---|
|`r` (read)|Read file content|`cat file`, `less file`, `head file`|
|`w` (write)|Edit file|`nano file`, `vim file`, `echo hi >> file`|
|`x` (execute)|Run file as program|`./script.sh`, `./a.out`|

| Permission | What happens                             |
| ---------- | ---------------------------------------- |
| `rw-`      | Can read + edit                          |
| `r-x`      | Can read + run                           |
| `--x`      | Can run but not read source              |
| `r--`      | Read only                                |
| `-w-`      | Can edit blindly (weird but possible 😅) |

---
## What is an inode?

An **inode (index node)** is a **data structure** used by Linux to store **metadata about a file**.

 **Important:**  
An inode **does NOT store the file name**
It stores **information ABOUT the file**


## What information does an inode store?

Each inode contains:

- File type (file, directory, link, etc.)
    
- File permissions (rwx)
    
- Owner (user ID)
    
- Group ID
    
- File size
    
- Timestamps (created, modified, accessed)
    
- Number of links
    
- Location of file data on disk (block pointers)
    

 **Not stored in inode**:

- File name
    
- File content itself

So Linux finds files like this:

`filename → inode → data blocks`

#### `ls -i <name>`

---


![[Pasted image 20260121141531.png]]

---
### Changing File permissions 

#### `chmod`

`chmod` = **change mode**

It changes **file permissions** stored in the file’s **inode**.

So when you run `chmod`, Linux updates the **permission bits inside the inode**.

Each file has **3 permission sets**:

|Who|Symbol|
|---|---|
|User (owner)|`u`|
|Group|`g`|
|Others|`o`|

Each set can have:

- `r` → read
    
- `w` → write
    
- `x` → execute


- `+` → add permission
    
- `-` → remove permission


### Give write permission to group

```shell
chmod g+w file.txt
```


we can also give numbers 

|Permission|Value|
|---|---|
|read (r)|4|
|write (w)|2|
|execute (x)|1|

```shell
chmod 700 <name>
```


## What is a hard link?

A **hard link** is **another name for the same file**.

 Both names point to the **same inode**  
 Same inode = same data on disk

So:

> **Hard link ≠ copy**  
> It’s the _same file with two names_.

to work with it first we have to see the inode number of each file or folder

`ls -li`

### Minimum hard links for a directory

- Every directory has **at least 2 hard links**:
    
    - `.` (self)
        
    - `..` (parent)

### Creating a subdirectory

`mkdir subdir`

- Creates `subdir/..` pointing to parent
    
- Parent directory hard link count **increases by 1**
    

---

### 🔹 Creating a file

`touch file.txt`

- File gets its own inode
    
- **Directory hard link count does NOT change**
    
- Files do not create `..` references
![[Pasted image 20260122141240.png]]