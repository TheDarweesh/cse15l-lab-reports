# Lab Report 3 # 

### The less command shows the contents of a file one screen at a time and is able to scroll through using certain keys
<br><br>
The syntax for the less command 
### 
```
less <file-name>
```
<br>

## **Three command options with exammples**

### 1) The first command option that will be demonstrated is the -N option

### It enumerates the results by line which is helpful considering that most times in terminal the lines are not enumerated. This makes scrolling though results much more practical 

```
less -N <file-name>
```

### An example of the -N option used on the technical directory search results for .txt files. 

![screenshot1](Screenshot1Lab3.PNG)
 
 ### The command typed 

![screenshot2](Screenshot2Lab3.PNG)

### The first page of results

### After pressing the space button it will increment by the number of results shown on the screen. 

![screenshot3](Screenshot3Lab3.PNG)

### To exit simply press the q key:
```
q
```

### 2) The second command option is done within the contents of a file shown by the command less. Simply type 
```
/<search-term>
```

#### The term will be highlighted if found

![screenshot4](Screenshot4Lab3.PNG) 

### After pressing enter

![screenshot5](Screenshot5Lab3.PNG)

### It highlights the search results 

<br>

### Another example 
![screenshot6](Screenshot6Lab3.PNG)

### Final Example 

![screenshot7](Screenshot7Lab3.PNG)

### 3) The -X command 

### The -X command keeps the content on the terminal screen even after quitting. 


![screenshot8](Screenshot8Lab3.PNG)

### The highlighted file on the bottom indicates that we are still in the file 

![screenshot9](Screenshot9Lab3.PNG)

### Even after quitting and typing in another command and viewing the contents of another file and exiting out the file above is still visible 

![screenshot10](Screenshot10Lab3.PNG)

### As shown, less README.md was entered and quitted and we still see the contents of Server.java

![screenshot11](Screenshot11Lab3.PNG)

### After -X for README.md we can still see the contents of Server.java and README.md



