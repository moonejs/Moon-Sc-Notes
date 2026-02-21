
| Command | Purpose            | Example            |
| ------- | ------------------ | ------------------ |
| `touch` | Create empty file  | `touch a.txt`      |
| `mkdir` | Create directory   | `mkdir test`       |
| `cp`    | Copy files/folders | `cp a.txt b.txt`   |
| `mv`    | Move / Rename      | `mv a.txt folder/` |
| `rm`    | Delete             | `rm file.txt`      |
| `file`  | Identify file type | `file a.txt`       |


#### `cp SOURCE DESTINATION`

>Copy SOURCE → and name it DESTINATION

![[Pasted image 20260105160735.png]]

**Copy file into a folder**

```shell
cp hello.txt backup/
```

Copy hello.txt → inside backup folder

#### Copy a directory

```shell
cp -r folder1 folder2
```

**`-r` = recursive  
 Without `-r`, folders won’t copy**


---
#### `mv` — move or rename files


**Rename a file**

```shell
mv old.txt new.txt
```

**Move a file**

```shell
mv file.txt folder/
```

---
#### `rm` delete files or folders

**Delete a file**

```shell
rm file.txt
```

**Delete a folder**

```shell
rm -r folder
```

---
#### `file`  - Identify file type

>Tells **what kind of file** something is

![[Pasted image 20260105161529.png]]

![[Level 4 to Level 5]]