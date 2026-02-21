![[Pasted image 20260216220701.png]]

##### enable line number

```shell
:set number

```

#### Super Trick (Very Powerful Concept)

**In Vim**

```shell
[number][command]
```

**Examples**

```shell
5dd   → delete 5 lines
3yy   → copy 3 lines
10j   → move down 10 lines

```

#### Every powerful Vim command follows this structure:

```
operator + motion

```

**like this**

```
action + where
```

**Action** `what to do `

Common operators:

|Operator|Meaning|
|---|---|
|`d`|delete|
|`y`|yank (copy)|
|`c`|change|
|`>`|indent|
|`<`|un-indent|

**What Is a Motion?**

A **motion** = movement or range.

It tells Vim **where to apply the action**.

Common motions:

| Motion | Meaning           |
| ------ | ----------------- |
| `w`    | next word         |
| `b`    | previous word     |
| `e`    | end of word       |
| `$`    | end of line       |
| `0`    | beginning of line |
| `j`    | down one line     |
| `k`    | up one line       |

==So motion = direction or target==

```shell
dw
```

Break it:

- `d` → delete (operator)
    
- `w` → to next word (motion)

Meaning:  
Delete from cursor to start of next word.

---

```shell
d$
```
- `d` → delete
    
- `$` → to end of line
    

Meaning:  
Delete from cursor to end of line.

### Insert Mode (Typing Mode)

| Command | Meaning                     |
| ------- | --------------------------- |
| `i`     | Insert before cursor        |
| `I`     | Insert at beginning of line |
| `a`     | Insert after cursor         |
| `A`     | Insert at end of line       |
| `o`     | New line below              |
| `O`     | New line above              |

Press `Esc` → Go back to Normal Mode

### Save & Exit Commands (Command Mode `:`)

|Command|Meaning|
|---|---|
|`:w`|Save|
|`:q`|Quit|
|`:wq`|Save & quit|
|`:x`|Save & quit|
|`:q!`|Quit without saving|
|`:w filename`|Save as new file|
### Movement Commands (Normal Mode)

|Key|Action|
|---|---|
|`h`|Left|
|`l`|Right|
|`j`|Down|
|`k`|Up|
|`0`|Start of line|
|`$`|End of line|
|`gg`|Go to first line|
|`G`|Go to last line|
|`:n`|Go to line number n|


`6G` ---> move to the 6th line 

`3j` --> move down 3 lines from current line 

**we can use numbers with these commands**


### Delete Commands

| Command | Meaning               |
| ------- | --------------------- |
| `x`     | Delete character      |
| `dd`    | Delete line           |
| `D`     | Delete to end of line |
| `dw`    | Delete word           |
| `d$`    | Delete till end       |
- `dd` → delete 1 line
    
- `2dd` → delete 2 lines
    
- `3j` → move 3 lines
    
- `G` → last line
    
- `gg` → first line
    
- `0` → start of line
    
- `$` → end of line
### Copy & Paste

|Command|Meaning|
|---|---|
|`yy`|Copy line|
|`yw`|Copy word|
|`p`|Paste after|
|`P`|Paste before|

### Undo / Redo

|Command|Meaning|
|---|---|
|`u`|Undo|
|`Ctrl + r`|Redo|

###  Search


|Command|Meaning|
|---|---|
|`/word`|Search forward|
|`?word`|Search backward|
|`n`|Next result|
|`N`|Previous result|

### Replace

| Command         | Meaning                 |
| --------------- | ----------------------- |
| `r`             | Replace one character   |
| `R`             | Replace mode            |
| `:%s/old/new/g` | Replace all in file     |
| `:s/old/new/g`  | Replace in current line |

```
:[range]s/old/new/[flags]
```

Breakdown:

- `:` → enter command mode
    
- `s` → substitute
    
- `old` → word to search
    
- `new` → replacement
    
- `g` → global (replace all matches in that line)

After the last `/`, you can add flags:

|Flag|Meaning|
|---|---|
|g|global (all matches in line)|
|c|confirm each replacement|
|i|ignore case|
### Visual Mode

**Visual mode = **Selection mode in Vim***


|Command|Meaning|
|---|---|
|`v`|Select characters|
|`V`|Select whole line|
|`Ctrl + v`|Block selection|
After selecting:

- `d` → delete
    
- `y` → copy

- Normal mode → you give commands
    
- Insert mode → you type
    
- Visual mode → you select text
### Split Windows

|Command|Meaning|
|---|---|
|`:split`|Horizontal split|
|`:vsplit`|Vertical split|
|`Ctrl + w w`|Switch window|

### Word Movement 

```
w  → jump to next word
b  → jump backward one word
e  → jump to end of word

```


### change and insert in one go 

`c` 

to change the word `cw` it will automatically go into insert mode 

`cw`:

- Deletes entire word
    
- Automatically enters Insert mode
    
- Works with numbers (`c3w`)
    
- Works with motions (`c$`, `ciw`)


### `.` (dot command)

Dot repeats your last change.

Example:

If you do:

```
cw orange Esc

```
Then move to another word and press:

`.`

It repeats the same change.


---

### `iw`=inside word

```shell
d + iw
```

means:  
Delete the whole word your cursor is inside.

Not from cursor forward.  
The WHOLE word.

This is more precise.


| Command | What it does               |
| ------- | -------------------------- |
| `dw`    | delete from cursor forward |
| `diw`   | delete whole word          |
| `cw`    | change from cursor forward |
| `ciw`   | change whole word          |

### `*` 

What it does:

- Takes the word under your cursor
    
- Searches forward automatically
    
- Jumps to next occurrence
    

No typing `/word`.

press `n` next again press `N` previosu match


---
### `%`

That is one of the most important code-navigation commands.

What it does:

- If cursor is on `{` → jumps to matching `}`
    
- If on `(` → jumps to matching `)`
    
- If on `[` → jumps to matching `]`
    

This is massive for programming.