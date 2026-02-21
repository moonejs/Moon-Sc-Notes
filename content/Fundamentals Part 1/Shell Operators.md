
| Symbol | What it Does                                                     | Example                    |
| ------ | ---------------------------------------------------------------- | -------------------------- |
| `&`    | Runs a command in the background so the terminal is free         | `cp bigfile.zip backup/ &` |
| `&&`   | Runs the next command **only if** the previous one succeeds      | `mkdir test && cd test`    |
| `>`    | Sends command output to a file and **replaces** existing content | `echo hey > welcome`       |
| `>>`   | Sends command output to a file and **adds** to existing content  | `echo hello >> welcome`    |


#### `&`

>This operator allows us to execute commands in the background.

 For example, let's say we want to copy a large file. This will obviously take quite a long time and will leave us unable to do anything else until the file successfully copies.

The `&` shell operator allows us to execute a command and have it run in the background (such as this file copy) allowing us to do other things!

![[Pasted image 20260105132654.png]]


---

#### `&&`

>Run the next command ONLY IF the previous one succeeded

![[Pasted image 20260105132741.png]]

---
#### `>`

>Take output and put it into a file (overwrite)

Let's say we wanted to create a file named "welcome" with the message "hey". We can run `echo hey > welcome` where we want the file created with the contents "hey" like so:

![[Pasted image 20260105133042.png]]

---
#### `>>`

>Take output and add it to the end of a file

![[Pasted image 20260105133204.png]]