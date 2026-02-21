
### Pattern Matching

>Pattern matching means **searching for specific text based on a rule (pattern)**.

Instead of searching for an exact word, you search using a **rule**.

### What is Regex?

Regex (Regular Expression) is:

> A special language used to create patterns for searching text.

Think of it like:

- 🔹 Normal search → search exact word
    
- 🔹 Regex search → search using smart rules

![[Pasted image 20260213161552.png]]

######  Simple Example

If a file contains:

```
cat
dog
car
cow

```

**Regex Pattern**
```shell
c.*
```

Matches:

- cat
    
- car
    
- cow
    

Because:

- `c` → starts with c
    
- `.*` → anything after that
    

That is regex working as a pattern template.

#### BRE: POSIX Basic Regular Expression engine

It is:

- The default regex type used in `grep`
    
- Slightly limited
    
- Requires `\` for some symbols


```shell
grep "\(hello\)" file.txt
```

You must use `\(` and `\)` for grouping.


#### ERE: POSIX Extended Regular Expression engine

### What is ERE?

ERE = **Extended Regular Expression**

It is:

- More powerful
    
- Easier syntax
    
- Used with:

```shell
grep -E
```


---

### `grep`

`grep` is a Linux command used to **search text inside files using patterns**.

It prints lines that match your pattern.

1.
```shell
grep pattern filename
```

**Search inside a file for lines matching a pattern.**

2.
```shell
command | grep 'pattern'
```

The `|` symbol means:

> Take output of first command and give it to grep.

```shell
ls | grep ".txt"
```

Step-by-step:

- `ls` → lists files
    
- `grep ".txt"` → filters only .txt files
    

So you are filtering command output.

![[Pasted image 20260213162501.png]]

>By default BRE

**Switch to ERE**

```shell
egrep "pattern" file.txt
```

```shell
grep -E "pattern" file.txt
```

**Both are same.**

######  Why use ERE?

Because you can use:

- `+`
    
- `?`
    
- `|`
    
- `( )`
    

Without backslash.


---

```
.   Any single character except null or newline
*   Zero or more of the preceding character/expression
[ ] Any of the enclosed characters
^   Beginning of line (or negation inside [ ])
$   End of line
\   Escape special characters

```

##### `.` dot

>Matches **any single character**

Except:

- newline
    
- null

Example

```shell
cat
cot
cut
c9t
```

pattern
```shell
c.t
```

Matches:
```shell
cat
cot
cut
c9t
```

Because:

- `c` = c
    
- `.` = anything
    
- `t` = t


##### `*` start

>Matches **0 or more of previous character**

>It works on the character BEFORE it.

Example
```shell
ab*
```

Matches:

```shell
a
ab
abb
abbb
```

Why?

- `b*` = zero or more b
    

So:

- zero b → a
    
- one b → ab
    
- many b → abbb


##### `[]` character set

>Match **any one character inside brackets**

Example 1
```shell
[abc]
```

Matches:

- a
    
- b
    
- c

Example 2 (range)

`[a-z]`

**Matches any lowercase letter.**

Example
`[0-9]`
Matches any digit.

##### `^`

Two meanings depending on location.

###### Case 1: Beginning of line

```shell
^hello
```

>Matches lines that START with hello.

###### Case 2: Negation inside brackets


```shell
[^0-9]
```


##### `$`

>Matches END of line

```shell
hello$
```

##### `\`

>Escape special characters.

If you want to search actual `.` or `*`, you must escape them.

Example:

Search for actual dot:

```shell
grep "\." file.txt
```


#### Important Combination Examples

```shell
^a.*z$
```

Meaning:

- Starts with a
    
- Ends with z
    
- Anything in between

```shell
^[0-9]*
```

Lines that start with digits.

|Symbol|Meaning|
|---|---|
|`.`|Any one character|
|`*`|0 or more of previous|
|`[ ]`|Any character inside|
|`^`|Start of line|
|`$`|End of line|
|`\`|Escape character|

### Special Characters (BRE vs ERE differences)

Your slide shows two sections:

##### BRE Special Characters

```
\{n,m\}  Range of occurrences
\( \)    Grouping

```

#### ERE special characters

```
{n,m}    Range of occurrences
( )      Grouping
+        One or more
?        Zero or one
|        OR operator

```

##### `{n,m}` (Repetition Range)

>Match the previous character **at least n times and at most m times**.

Example
```shell
a{2,4}
```

```
aa
aaa
aaaa
```

But not:

```
a
aaaaa
```

##### In BRE:

You must escape it:

```shell
a\{2,4\}
```

> - ERE → `{2,4}`
> - BRE → `\{2,4\}`

##### `( )` Grouping

>Grouping lets you treat multiple characters as one unit.

**Example (ERE):**

```
(ab){2}
```

Matches:
```
abab
```

Because:

- `(ab)` is one unit
    
- Repeat it twice

##### In BRE:

You must write:

```shell
\(ab\)\{2\}
```

##### `+` (Only in ERE)

>One or more of previous character.

```shell
a+
```

Matches

```
a
aa
aaa

```

In BRE, you must write:

```shell
a\+
```

##### `?` (Only in ERE)

>Zero or one of previous character.

Example:

```shell
colou?r
```

##### `|` (OR operator)

>Match either left side OR right side.

```shell
cat|dog
```

Matches:

- cat
    
- dog
    

Used with:

```shell
grep -E "cat|dog" file.txt
```


|Feature|BRE|ERE|
|---|---|---|
|`{n,m}`|`\{ \}`|`{ }`|
|`( )`|`\( \)`|`( )`|
|`+`|`\+`|`+`|
|`?`|`\?`|`?`|
|`|`|❌|


---

![[Pasted image 20260213210909.png]]

### What Are Character Classes?

>Character classes are **predefined groups of characters**.

Instead of writing:

```shell
[a-zA-Z]
```

we can write

```shell
[[:alpha:]]
```

It is cleaner and more portable.

##### `[[:digit:]]`

```
0 1 2 3 4 5 6 7 8 9
```

```shell
grep "[[:digit:]]" file.txt
```
Matches lines containing numbers.

##### `[[:alpha:]]`

All letters (a-z, A-Z)

```shell
grep "[[:alpha:]]" file.txt
```

##### `[[:alnum:]]`

Letters + numbers

```shell
grep "[[:alnum:]]" file.txt
```
