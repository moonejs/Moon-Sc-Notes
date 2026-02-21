
#### `tar`

`tar` stands for:

> **T**ape **AR**chive

Originally used for tape backup.

>`tar` by itself **does NOT compress**  
It only **archives (combines files into one file)**

###### syntax

```shell
tar [options] archive_name files

```

|Option|Meaning|
|---|---|
|`c`|Create archive|
|`x`|Extract|
|`t`|List contents|
|`v`|Verbose (show progress)|
|`f`|File name|

```shell
tar -cvf file.tar folder/
```

Meaning:

- `c` → create
    
- `v` → show files
    
- `f` → file name is file.tar

**Extract Archive**

```shell
tar -xvf file.tar
```

**View Contents**


```shell
tar -tvf file.tar
```

### `zip`

`zip`:

- Archives AND compresses at same time
    
- Common in Windows
    
- Creates `.zip` file

```shell
zip file.zip file1.txt

```

**Zip a Folder (Important)**