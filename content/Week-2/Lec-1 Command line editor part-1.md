	
![[Pasted image 20260131115502.png]]

![[Pasted image 20260131115508.png]]



> [!PDF|yellow] [[Navigating Linux.pdf#page=131&selection=99,0,115,3&color=yellow|Navigating Linux, p.109]]
> > We invoke ed by using the executable ed and providing the filename as an argument. 1 $ ed test.txt 2 117


> [!PDF|red] [[Navigating Linux.pdf#page=131&selection=125,12,133,1&color=red|Navigating Linux, p.109]]
> > we can use the P command. The default prompt is *

> ([[Navigating Linux.pdf#page=132&selection=30,0,40,8&color=red|Navigating Linux, p.110]])
> Lets go to the first line of the file using the 1 command. We can also go to the last line of the file using the $ command.


> ([[Navigating Linux.pdf#page=132&selection=62,0,74,8&color=yellow|Navigating Linux, p.110]])
> To print out all the lines of the file, we can use the , or \% with p command.

> ([[Navigating Linux.pdf#page=132&selection=118,0,128,14&color=important|Navigating Linux, p.110]])
> However, if we use the , command without the p command, it will not print all the lines. Rather, it will just move the cursor to the last line and print the last line.


> ([[Navigating Linux.pdf#page=132&selection=138,1,139,33&color=red|Navigating Linux, p.110]])
> e can also print any arbitrary line range using the line numbers separated by a comma followed by p command


```shell
*/hello/
```

> ([[Navigating Linux.pdf#page=133&selection=53,0,58,5&color=note|Navigating Linux, p.111]])
> We can advance to the next line using the + command.



> [!PDF|note] [[Navigating Linux.pdf#page=133&selection=76,0,80,7&color=note|Navigating Linux, p.111]]
> > And go to the previous line using the - command

> [!PDF|note] [[Navigating Linux.pdf#page=133&selection=98,0,103,8&color=note|Navigating Linux, p.111]]
> > We can also print all the lines from the current line to the end of the file using the ;p command.

> [!PDF|note] [[Navigating Linux.pdf#page=133&selection=130,0,135,9&color=note|Navigating Linux, p.111]]
> > We can also run arbitrary shell commands using the ! command.

![[Pasted image 20260131141352.png]]

> ([[Navigating Linux.pdf#page=134&selection=29,0,36,7&color=note|Navigating Linux, p.112]])
> The output of the command is shown to the screen, however, it is not saved in the buffer. To read the output of a command into the buffer, we can use the r command


> ([[Navigating Linux.pdf#page=137&selection=70,0,77,36&color=note|Navigating Linux, p.115]])
> We can move a line from its current position to another line using the m command. Lets insert a line-0 at the end of the file and then move it to the beginning of the file


```shell
*3m1

```
- `3` → line to move
    
- `m` → move
    
- `1` → destination
    
- Move **line 3 AFTER line 1**
