### What is a Hypervisor?

>A **hypervisor** is software (or firmware) that lets you run **virtual machines (VMs)** on your computer.

it is between the hardware and the os

Without hypervisor:

- You can run **only one OS at a time** (Windows OR Linux)
    

With hypervisor:

- You can run **Windows + Linux + another Linux** together

`uname` === show the details of the OS

---

##### `groups`

It shows **which groups your user belongs to**.

![[Pasted image 20260205215344.png]]

---

### Command substitution and arithmetic expansion


##### Variables

```shell
x=5
echo $x
```

output `5`

`$x`  -> read value

### Math in bash → `$(( ))`

```shell
echo $((2 + 3))
```

output `5`

#### Run a command inside another → `$( )`

```shell
echo $(pwd)
echo "I am in $(pwd)"
```

![[Pasted image 20260206222433.png]]

![[Pasted image 20260206222518.png]]

>[!note]
>`/` escapes the `$`

`"\$((2+2))"`

The backslash `\` **escapes** the `$`  
So Bash treats `$((2+2))` as **plain text**, not as math.

```
"\$((2+2))"  →  literal string:  $((2+2))
```
