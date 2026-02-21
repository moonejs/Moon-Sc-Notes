
In Linux, you **don’t usually download software from random websites** like in Windows.

Instead, Linux has something called a **Package Manager**.

>Play Store for Linux (but in terminal)


It helps you:

- install software
    
- update software
    
- remove software
    
- keep everything safe and clean
    

This whole system is called **Software Management**.


### Package

A **package** is just:

> A file that contains a software program + instructions on how to install it

Example packages:

- firefox
    
- vlc
    
- python
    
- git
    

Each one is a package in Linux.


#### Package Types

In Linux, software comes in **package formats**.  
Think of formats like file types:

- `.exe` → Windows
    
- `.apk` → Android
    
- `.deb` → Ubuntu / Debian
    
- `.rpm` → RedHat / Fedora
- `.dmg` → mac

![[Pasted image 20260209160437.png]]

##### Let's check what type of os we have 

```shell
lsb_release -a
```

![[Pasted image 20260209160611.png]]

### Architecture

>Architecture = the type of CPU / processor your computer uses

- Laptop / PC → Intel / AMD
    
- Raspberry Pi / phones → ARM
    
- Servers → different architectures
    

So Linux packages are built **specifically for each CPU type**.

You can’t install the wrong type.

### `amd64` or `x86_64`

This is **most normal laptops & PCs today**  
Even Intel laptops show `amd64`  
It means **64-bit computer**

![[Pasted image 20260209160827.png]]


to check run this command

```shell
uname -a
```

![[Pasted image 20260209161222.png]]

![[Pasted image 20260209161321.png]]

#### `DEB`

- ##### `apt` (Advanced Package Tool)


 - Downloads software
    
- Installs it
    
- Handles dependencies
    
- Updates software


- ##### `dpkg`

Low-level tool.

- Installs `.deb` files directly
    
- Does NOT download from internet
    
- Does NOT handle dependencies well

---
![[Pasted image 20260209161728.png]]

###### package database

Ubuntu keeps a **local list (database)** of all available software:

- names
    
- descriptions
    
- versions
    
- info about each package


#### `apt-cache` lets you **read/search** this database.

let's us check if this command exist or not 

```shell
which apt-cache
```

```shell
apt-cache search fortune
```

![[Pasted image 20260209162349.png]]


to list the packages in sorting order and read the file page by page 

```shell
apt-cache pkgnames | sort | less
```

![[Pasted image 20260209162536.png]]

is it easy to search by name use `command name`

##### how details of a package

```shell
apt-cache show -a package
```

Shows **full information** about a package:

- what it does
    
- version
    
- size
    
- dependencies
    
- description

### Package Names

![[Pasted image 20260209163341.png]]

```
vlc_3.0.20-1_amd64.deb
```

| Part     | Meaning                               |
| -------- | ------------------------------------- |
| `vlc`    | Package name (software name)          |
| `3.0.20` | Version of the software               |
| `-1`     | Revision (Ubuntu’s packaging version) |
| `amd64`  | Architecture (64-bit PC)              |
| `.deb`   | Ubuntu package type                   |

![[Pasted image 20260209163505.png]]

Ubuntu labels packages by **how important they are to the system**.  
This helps decide:

- what must be installed
    
- what can be skipped
    
- what is risky to remove


#### `required` – MUST have

These are **core system packages**.  
If you remove them, your system may:

- not boot
    
- break badly
    

Example (conceptual):

- basic shell
    
- core utilities

#### `important` – System health stuff

> **Provides functionality that enables the system to run well**

Not as critical as `required`, but still very important.

If removed:

- system might work
    
- but features can break
    
- tools may stop working

#### `standard` – Normal stuff

> **Included in a standard system installation**

These are things most users expect to have:

- basic tools
    
- common programs
    

You can remove them safely if you want a minimal system, but normally you don’t.

#### ## `optional` – Extra convenience

> **Can omit if you don’t have enough storage**


####  `extra` – Very specific / niche

> **May conflict with higher priority packages, specialized use**


---
![[Pasted image 20260209164218.png]]


A **checksum** is like a **digital fingerprint** of a file.

When you download a file (like a `.deb` package):

- Linux calculates a checksum
    
- Compares it with the official checksum
    
- If they match → file is safe and unchanged 
    
- If they don’t match → file is corrupted or tampered


![[Pasted image 20260209164559.png]]