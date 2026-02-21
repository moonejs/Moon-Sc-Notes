![[Pasted image 20260204150105.png]]

- `;` → run commands one after another
    
- `&&` → run next only if previous succeeded
    
- `||` → run next only if previous failed
    
- `|` → pipe output into another command


`|` (pipe output into another command)

This is the most powerful one.

`command1 | command2`

Meaning:

> Take the output of `command1` and feed it as input to `command2`


## Redirection (send output to files)

### Overwrite file: `>`

`ls > files.txt`

### Append to file: `>>`

`echo "hello" >> notes.txt`

### Use file as input: `<`

`wc -l < notes.txt`


---
`(ls ; date ; wc -l /etc/profile;)`

This is the **same commands**, but wrapped in **parentheses**.

### What parentheses do in Bash

> They run the commands in a **subshell** (a child shell).

Meaning:

- Commands run in a **temporary shell**
    
- Any changes inside do **not affect your main shell**
    

Output is the same, but **environment is different**.

![[Pasted image 20260204153103.png]]

In Linux, **everything is treated like a file** — including keyboard input and screen output.

So Linux gives every program **three default “files”** to talk to the world:

| Number | Name   | Meaning          |
| ------ | ------ | ---------------- |
| `0`    | stdin  | Input (keyboard) |
| `1`    | stdout | Normal output    |
| `2`    | stderr | Error output     |

These numbers are called **file descriptors**.

![[Pasted image 20260204153914.png]]

When you type a command and press **Enter**, this happens:

1. Your keyboard input goes to the **shell** (bash/zsh)
    
2. The shell finds the **program**
    
3. The program runs
    
4. The program reads from **stdin (0)**
    
5. The program writes to **stdout (1)** and **stderr (2)**
    
6. The terminal displays whatever comes to stdout/stderr

![[Pasted image 20260204155500.png]]

