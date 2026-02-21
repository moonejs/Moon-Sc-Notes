
#### solution

```shell
mv *.txt level1
```

| Pattern | Meaning                             |
| ------- | ----------------------------------- |
| `*`     | anything (any number of characters) |
| `?`     | exactly one character               |
| `[abc]` | one of a, b, c                      |
| `[0-9]` | any digit                           |

Move all `.txt` files to a folder

```shell
mv *.txt texts/
```

Move all `.jpg` and `.png` files

```shell
mv *.jpg *.png images/
```

Move all files starting with `log`

```shell
mv log* logs/
```


Move all files ending with numbers
```shell
mv *[0-9] numbers/
```

Move files with 3-letter extensions

```shell
mv *.??? 
```


