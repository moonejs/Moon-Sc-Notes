
**Password** = ==263JGJPfgU6LtdEvgfWU1XP5yac29mFx==

---

`-` A "dashed filename" is ==a file whose name contains a hyphen or dash (-)==,

we have to use 

- Double Dash `--` or
- ==`./` prefix==  (we will use this )

| Operation  | Standard Command          | Command for Dashed Filename (`-file.txt`)                     |
| ---------- | ------------------------- | ------------------------------------------------------------- |
| **Create** | `touch file.txt`          | `touch -- -file.txt` or `touch ./-file.txt`                   |
| **View**   | `cat file.txt`            | `cat -- -file.txt` or `cat ./-file.txt`                       |
| **Rename** | `mv file.txt newfile.txt` | `mv -- -file.txt newfile.txt` or `mv ./-file.txt newfile.txt` |
| **Delete** | `rm file.txt`             | `rm -- -file.txt` or `rm ./-file.txt`                         |
| **Edit**   | `nano file.txt`           | `nano -- -file.txt` or `nano ./-file.txt`                     |


#### `~`

Home directory of the current user

