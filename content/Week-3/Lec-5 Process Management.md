
### `sleep`


> [!PDF|] [[Navigating Linux.pdf#page=197&selection=6,0,21,46|Navigating Linux, p.175]]
> > sleep is a command that is used to delay the execution of a process for a specified amount of time. sleep itself is a no-op command, ‗ but it takes a variable amount of time to execute, depending on the argument of the command. This is useful when you want to delay the execution of another command or chain of commands by a certain amount of time.


### `coproc`


It lets you run a command **in the background** and  
**talk to it using input/output pipes**.

![[Pasted image 20260212075333.png]]

**kill** command will kill it

we can also use `&` 

![[Pasted image 20260212075547.png]]

#### `jobs`

also show what commands are running in the background

![[Pasted image 20260212075754.png]]

`help jobs` will work


### `top`

this will command will tell what proccess are running with the cpu utilization

![[Pasted image 20260212080032.png]]

---
#### `fg`

this command will help to come the background job to **f**or**g**round 

```
help fg
```

![[Pasted image 20260212080404.png]]


#### `ctrl + z` to stop it (no kill)

---

### `$`

![[Pasted image 20260212082013.png]]


![[Pasted image 20260212082147.png]]

![[Pasted image 20260212082217.png]]


---
### `history`

this command will give all the commands that has run in the shell

![[Pasted image 20260212082414.png]]

we can use `!` followed by the number to run the particular command

---
### `{}` Brace expantion

![[Pasted image 20260212082654.png]]

![[Pasted image 20260212082739.png]]
![[Pasted image 20260212083147.png]]

---
### `echo $?`

it will a give a integer between **0 to 55** 
on the basis of error occurred in the previous command if no error answer would be **0**

![[Pasted image 20260212083418.png]]
