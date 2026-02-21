
```shell
cd ///usr///bin
pwd

```

In Linux:

- Multiple slashes (`//`, `///`, `////`) are treated as **a single `/`**
    
- Linux **normalizes the path**
Extra `/` are ignored.

```shell
///usr///bin  ==  /usr/bin

```

---
#### `ls`

```shell
ls -l level1
```

will list the items inside the level1

```shell
ls -ld level1
```

It **shows information about the directory `level1` itself**,  
**not the files inside it**.

![[Pasted image 20260122165404.png]]

#### `ls -ldi level1`

it will also show the inode

![[Pasted image 20260122165458.png]]

---

The order of options (`-l -d -i`) does NOT matter in `ls`.

## The commands you ran

```
s -l level1 -di
ls -d level1 -li 
ls -i level1 -ld
 ls level1 -idl
```

 **All four commands give the SAME output**.

Why?  
Because **Linux combines options**, no matter where you place them.

`-d` → directory itself

---

|Command|Best For|
|---|---|
|`cat`|Small files, quick output|
|`less`|Large files, safe viewing|
|`more`|Basic paging|
|`head`|File start|
|`tail`|File end / logs|
|`wc`|File statistics|

![[Pasted image 20260122170014.png]]



## `cat` (concatenate / display file)

### Purpose:

- Display the **entire content** of a file on the terminal
    

### Syntax:

```shell
cat filename
```

### Use cases:

- View small files
    
- Combine files
    
- Create files


## `less` (best file viewer)

### Purpose:

- View file **page by page**
    
- Scroll up/down safely
    

### Syntax:

```shell
less filename
```

### Useful keys inside `less`:

- `Space` → next page
    
- `b` → previous page
    
- `/word` → search
    
- `q` → quit
    

### Why `less` is preferred:

- Efficient for large files
    
- Doesn’t load entire file into memory


## `more` (older pager)

### Purpose:

- View file page by page (older version of `less`)
    

### Syntax:

` more filename `

### Limitation:

- Mostly scroll **only forward**
    
- Less flexible than `less`


## `head`

### Purpose:

- Show the **first lines** of a file
    

### Syntax:

`head filename`

### Default:

- Shows first **10 lines**
    

### Custom lines:

`head -n 5 filename`

### Use cases:

- Preview file
    
- Check headers in logs / CSV files


## `tail`

### Purpose:

- Show the **last lines** of a file
    

### Syntax:

`tail filename`

### Default:

- Shows last **10 lines**
    

### Custom lines:

`tail -n 20 filename`

### Live monitoring (very important):

`tail -f logfile.log`

Used for:

- Logs
    
- Debugging
    
- Server monitoring


## `wc` (word count)

### Purpose:

- Count **lines, words, characters**
    

### Syntax:

`wc filename`

### Output format:

`lines  words  characters  filename`

### Common options:

`wc -l filename   # lines wc -w filename   # words wc -c filename   # bytes`


![[Pasted image 20260122215910.png]]

## `man` (manual)

### Purpose:

- Shows the **official manual page** of a command


## `which`

### Purpose:

- Shows the **path of the command executable** that will run


## `apropos`

### Purpose:

- Search **manual pages by keyword**

```shell
apropos keyword
```


### Purpose:

- Shows **detailed documentation** (GNU style)


## `whatis`

### Purpose:

- Shows a **one-line description** of a command

## `help`

### Purpose:

- Shows help for **shell built-in commands**

## `type`

### Purpose:

- Tells **what kind of command** it is

### `info`

will give information about all the commands


---
# Multiple Arguments

```shell
touch a.txt b.txt c.txt
```

`touch file`
 Creates an empty file (or updates timestamp if it exists).

**Single argument** :- - Creates **one file** → `a.txt`

**Multiple** **arguments**  

- `touch` sees **multiple arguments**
    
- It **treats EACH argument separately**
    
- Creates **three files**

>For `touch`:
> **All arguments are independent files**

same goes with `mkdir` command but to create nested folders we have to tell the paths 

```shell
mkdir -p project/src project/bin project/docs
```


#### `cp`

```shell
cp a b dir1
```

How Linux reads this:

- `a`, `b` → sources
    
- `dir1` → **destination**
    

 **Rule**:

> If there are **more than one source**, the **last argument MUST be a directory**.


# What is Recursion? (Linux context)

## 🔹 Simple definition

> **Recursion means: doing the same action again and again on everything inside, including sub-things.**

In Linux:

- A **directory** can contain:
    
    - files
        
    - other directories
        
- **Recursion** means:
    
    > go inside each directory → then inside its subdirectories → and so on
    
    ## Without recursion (normal behavior)

Imagine this structure:

```
dir1/
├── a.txt
├── b.txt
└── subdir/
    └── c.txt

```


now run 
```shell
cp dir1 dir2

```

This fails because:

- `cp` sees a directory
    
- It does **NOT** automatically go inside it

With recursion (`-r`)


```shell
cp -r dir1 dir2
```

What happens:

1. Copy `dir1`
    
2. Go inside `dir1`
    
3. Copy `a.txt`
    
4. Copy `b.txt`
    
5. Go inside `subdir`
    
6. Copy `c.txt`
    

 This “go inside again and again” is **recursion**.

## Why `mv` doesn’t need `-r`

```shell
mv dir1 dir2
```

Works because:

- `mv` **assumes recursion**
    
- It moves the directory as a whole
    

 No copying, just changing location.


**Commands that commonly use recursion**

| Command | Recursive option |
| ------- | ---------------- |
| `cp`    | `-r`             |
| `rm`    | `-r`             |
| `chmod` | `-R`             |
| `chown` | `-R`             |
| `ls`    | `-R`             |

---
**Inode = the real file**  
**Filename = just a name pointing to the inode**

## HARD LINK

### 🔹 What is a hard link?

A **hard link** is **another filename for the SAME inode**.

 - Same inode  
 - Same data 
 - Same file

---

### 🔹 How to create a hard link

```shell
ln file1 file2
```

- `file1` and `file2` are **the same file**
    
- Just two different names

Proof (inode number)
```shell
ls - i file1 file2
```

if write on one file will appear on another file if delete another file will remain there

### What is a symbolic link?

A **symbolic link** is a **special file that stores a PATH to another file**.

Different inode  
Points to filename, not inode  
 Like a shortcut

```shell
ln -s file1 link1
```

```shell
ln -s TARGET LINK_NAME

```

That stored path is understood starting from **where the link is located**,  
NOT from where you ran the command.

***refer Grpa_2.2***

---
### file sizes

![[Drawing 2026-01-30 10.49.18.excalidraw]]

here the red box is the file size in bytes

human readable

```shell
ls -lh
```

![[Pasted image 20260130105252.png]]

### What is `stat`?

`stat` shows **detailed information about a file or directory**.

 It reads information from the **inode**.
![[Pasted image 20260130105722.png]]

### What is `du`?

`du` shows **disk usage** —  
 how much **actual disk space** a file or directory uses.

 NOT file size, but **space on disk**.
![[Pasted image 20260130105906.png]]


---
### `/proc` and `/sys`


> **`/proc` and `/sys` are NOT real directories on disk.**  
> They are **virtual filesystems** created by the **kernel**.

- They **do not store data permanently**
    
- Files are **generated on the fly**
    
- Used to **view and control kernel information**

## `/proc` — Process & System Information

### 🔹 What is `/proc`?

`/proc` provides **runtime information** about:

- running processes
    
- memory
    
- CPU
    
- kernel status
    

 It reflects **what is happening right now**.


various file to explore in this

for memory `free` is good command

## `/sys` — Hardware & Kernel Objects

### 🔹 What is `/sys`?

`/sys` exposes:

- hardware devices
    
- drivers
    
- kernel subsystems
    

 It shows **how hardware is connected and configured**.