

| Command               | Description                             |
| --------------------- | --------------------------------------- |
| `ctrl + l` or `clear` | to clear the terminal                   |
| `cd -`                | previous directory in which are working |
| `cd .`                | single dot current directory            |
| `cd ..`               | Double dot parent directory             |
| `cd ~`                | `~` is for home directory               |
| `cd /`                | `/` is for root directory               |
| `cd -`                | `-` to go to pervious working directory |
| `batcat`              | to read the file                        |
| `*`                   | anything (any number of characters)     |
| `?`                   | anything (any number of characters)     |
| `[abc]`               | one of a b c                            |
| `[0-9]`               | any digit                               |


### Cheat for IIT M terminal `tmux`

```shell
Start tmux:        tmux
Detach tmux:       Ctrl + b, then d
Attach tmux:       tmux attach
Split horizontal:  Ctrl + b, then "
Split vertical:    Ctrl + b, then %
Move panes:        Ctrl + b, then arrow key
Close pane:        exit

```


for **Mouse Navigation**

```shell
vim ~/.tmux.conf
```

inside the file

```shell
set -g mouse on
```

then save the file

```shell
tmux source ~/.tmux.conf
```

to make **copy** and **paste**

```shell
setw -g mode-keys vi
```
