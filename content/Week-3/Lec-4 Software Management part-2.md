[[Lec-3 Software Management in Linux]]


>In Linux, **normal users are not allowed** to change system software.  
Only special users called **sudoers** can do that.

That’s why you type:

```shell
sudo apt instal abc
```

`sudo` = “do this as admin”

This protects your system from:

- accidental damage
    
- malware
    
- wrong commands


#### `/etc/sudoers`

This is the **configuration file** that decides:

> Which users are allowed to use `sudo`


#### `/etc/apt`

This folder contains **settings for apt**.

It tells Ubuntu:

>  “Which internet servers (repositories) should I download software from?”


#### `sources.list`

>This file contains:

- the main list of Ubuntu software sources


```shell
sudo apt update
```

Ubuntu:

- reads `sources.list`
    
- goes to those servers
    
- updates the package list


```shell
sources.list.d/
```

This folder contains:

- extra source files
    

When you add software like:

- Google Chrome
    
- Docker
    
- VS Code
    

They add their own `.list` file here.


---
#### `apt-get update`

```shell
sudo apt-get update
```

This **does NOT install anything**.

It just:

- contacts Ubuntu servers
    
- downloads the **latest list of available software & versions**
    

Think of it as:

>  “Refresh the app store list”

 Rule:

>  Run this before installing/upgrading software


**Modern version:**

```shell
sudo apt update
```

#### `apt-get upgrade`

**Upgrade all installed packages**

```shell
sudo apt-get upgrade
```

>[!Note]
>In new version we don't have to use `get`


#### `apt-get install package`

**Install a package**

```shell
sudo apt-get install vlc

```

###### What this does:

- Downloads VLC
    
- Installs VLC
    
- Installs dependencies automatically


#### `apt-get reinstall package`


```shell
sudo apt install --reinstall vlc
```


![[Pasted image 20260210171624.png]]

#### `apt-get autoremove`

```shell
sudo apt autoremove
```

When you install apps, Ubuntu installs **extra helper packages (dependencies)**.

Later, when you remove the main app, those helpers may stay behind.

`autoremove` removes:

>  packages that are no longer needed by anything


#### `apt-get clean`

**Clean downloaded package files**

```shell
sudo apt clean
```

When you install software, Ubuntu downloads `.deb` files and keeps them in cache.

`clean` removes:

- cached `.deb` files
    
- frees disk space
    

Your installed apps stay intact


#### `apt-get remove package`

**Remove a package (keep config files)**

```shell
sudo apt remove vlc
```

##### What this does:

- Removes the program
    
- Keeps configuration files
    

So if you reinstall later, your settings come back.


#### `apt-get purge package`

**Remove package + config files**

```shell
sudo apt purge vlc
```


##### What this does:

- Removes the program
    
- Deletes configuration files too
    

This is a **full clean uninstall**.


---
### Package management in Ubuntu using `dpkg`

#### `/var/lib/dpkg`

This folder is **dpkg’s internal database**.  
It stores records about:

- what packages are installed
    
- their status
    
- files they installed

- Files:
    
    - `arch` → architecture info
        
    - `available` → available packages (legacy)
        
    - `status` → what’s installed and their state
        
- Folder:
    
    - `info/` → scripts + file lists for each package


#### Useful `dpkg` commands

These are **safe info commands** (they don’t change anything):

 -  List packages matching a name
 
 ```shell
 dpkg -l vlc

 ```

**Shows whether VLC is installed.**



- List files installed by a package

```shell
dpkg -L vlc

```

**Shows all files VLC put on your system.**



- Show package status/info

```shell
dpkg -s vlc
```
**Shows version, status, description.**



- Find which package owns a file

```shell
dpkg -S /usr/bin/vlc
```

**Tells you which package installed that file.**


#### Installing a `.deb` file with dpkg

```shell
sudo dpkg -i package_version-revision_architecture.deb
```


######  When is this used?

Only when:

- you manually downloaded a `.deb` file
    
- e.g., Google Chrome, some third-party app