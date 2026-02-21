suppose we want to find a file and it is very difficult to look into each folder so if we remember the file name we can use `find -name password.txt`

![[Pasted image 20260105130235.png]]

if we don't know the name of the file, or want to search for every file that has an extension such as `.txt`. Find let's us do that too!

We can simply use what's known as a wildcard ( * ) to search for anything that has .txt at the end. In our case, we want to find every .txt file that's in our current directory. We will construct a command such as `find -name *.txt` . Where "Find" has been able to _find_ every .txt file and has then given us the location of each one:

![[Pasted image 20260105130535.png]]

