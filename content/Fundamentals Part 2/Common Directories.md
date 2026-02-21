
![[Pasted image 20260106142656.png]]

#### `/etc`

it stores system files that are use by our operating system.

`/etc` is a folder that stores **system settings files**

Examples of settings:

- users    
- passwords (encrypted)
- sudo rules
- network config

⚠️ These are **NOT your personal files**  
⚠️ These belong to the **system**

>[!important ]
>Linux is just files and folders arranged in a tree starting from `/`

```
/home/moon/file.txt   # exact location
./file.txt            # file in current folder
~ /file.txt           # file in my home folder
```

---
#### `/var` 

`/var` is a folder where Linux keeps files that CHANGE frequently.

Linux has:

- **files** (documents)
- **directories** (folders)
    
`/var` is just a **folder** inside `/`.

![[Pasted image 20260120120646.png]]

---
#### `/root`
> **`/root` is the HOME folder of the root user**

⚠️ **NOT the same as `/`**

In Linux:

- Normal user → has home folder in `/home`
    
- Root user → has home folder in `/root`

---
#### `/tmp`

`/tmp` is a folder for temporary files
Files in `/tmp` are often:

- deleted on reboot
    
	- auto-cleaned by system
- --
#### `/bin`

stands for **binary**.

It contains **essential command programs** that Linux needs to:

- boot
    
- run basic commands
    
- recover the system
    

These are **executable files**, not normal text files.

![[Pasted image 20260120115852.png]]

![[Pasted image 20260120120040.png]]

---
#### `/usr`

**`/usr` = UNIX System Resources**  
❌ It does **NOT** mean “user”

So:

`/usr`

stores **installed programs and system resources**, not personal files.

![[Pasted image 20260120120555.png]]


![[Pasted image 20260120121009.png]]