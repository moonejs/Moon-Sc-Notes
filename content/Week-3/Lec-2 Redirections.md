
![[Pasted image 20260205170103.png]]

![[Pasted image 20260205170153.png]]

### Redirect errors

```shell
ls not_exist 2> error.txt
```

![[Pasted image 20260205211230.png]]

### Save output & error separately

```shell
ls $HOME /blah > output.txt 2>error.txt
```

#### `command < file1`

>Take input for `command` from `file1` instead of the keyboard.

![[Pasted image 20260205212755.png]]

---

### `command > file1 2>&1`

“Send **normal output** of `command` to `file1`,  
and also send **error output** to the **same place**.

`command > file1`

Redirects **stdout (1)** into `file1`

`2>&1`
Redirect **stderr (2)** to **where stdout (1) is going**

![[Pasted image 20260205213159.png]]

![[Pasted image 20260206214508.png]]

![[Pasted image 20260206215206.png]]

Take the **output of `command1`**, feed it into **`command2`**,  
then take the **output of `command2`** and **save it into `file1`**.

![[Pasted image 20260206215520.png]]

![[Pasted image 20260206215635.png]]

![[Pasted image 20260206215724.png]]