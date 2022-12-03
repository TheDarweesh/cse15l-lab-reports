# Lab Report 4 # 


## Lab Report Part 1
---
### We will demonstrating how to change keywords in a file through Vim using the least amount of key strokes possible. 
<br>
<br>

### The instruction we will replicate from Week 6 will be: 

>In DocSearchServer.java, change the name of the ```start``` parameter of ```getFile```, and all of its uses, to instead be called ```base```.

---


<br>

### This is our ```DocSearchServer.java``` file open in vim inside the VS Code terminal

![screenshot1](Screenshots\Step1Lab4.png)

<br>

---


### We type in ```/``` in our console in ```normal mode``` to start a search. 

### We type in ```start``` after ```/``` as ```/start``` to indicate to Vim that we want to search for the word ```start```. 
### As can be seen, all entries that fit the search parameter are highlighted yellow with the first instance highlighted in gray to indicate which one we are selecting first.
![screenshot2](Screenshots\Step2Lab4.png)

<br>

---

### When we press ```<enter>``` our cursor moves to the first character. 
![screenshot3](Screenshots\Step3Lab4.png)



### We type in the letters ```ce``` which will 
![screenshot4](Screenshots\Step4Lab4.png)

### As we can see the only part that was deleted is the single word that came after the cursor which we had pointed it to after searching.

### Pressing ```ce``` takes us automatically into insert mode and so the next step is to simply write ```base```.
![screenshot5](Screenshots\Step5Lab4.png)

### The next step is much simpler and takes one less command. We first press ```<esc>``` in order to return back to normal mode. We search again for start by using ```/start```. However instead of pressing ```ce``` and typing in ```base``` we may now simply press the period button  ```.``` and it will automatically replicate the last command! 

<br>

### Again, simply search for the next ```start``` entry, press ```<enter>```, then press ```.``` then press ```<esc>``` to return to ```normal``` as you are still in ```insert``` mode after the edit.
---
###  As we can see, in the method FileHelpers, all ```start``` entries have been successfully changed to ```base```.

![screenshot6](Screenshots\Step6Lab4.png)


### The list of steps. 
### 1. Start the search query 
### 2. Press ```<enter>```
### 3. ```ce``` the first edit
### 4. Press ```<esc>``` 
### 5. Start the search again 
### 6. Press ```enter``` on the next entry
### 7. Press ```.``` to replace 
### 8. Press ```<esc>```
### 9. Repeat steps 5 - 8 until done.
### 10. In ```normal mode``` type ```:wq``` to save and exit.

<br>

### As we can see, this is a simple process that has steps that can be repeated very simply.


<br>

## Lab Report Part 2
---

### It took me 3 minutes editing on local and using ```scp``` while it took me 1 minute to edit on remote with Vim. The main difficulty was sending files in to the right directory in a reasonable amount of time as my computer has been faltering lately. However in a remote environment this largely does not matter. 

<br>

### I would prefer to use Vim on remote servers to make small changes in files rather than cloning files, opening them up in an environment, editing, and then re-sending the files back to the remote server  with ```scp``` as depedning on the level of edits this may take a long time just sending the files over. 

<br>

### Through Vim I am able to view and edit code through the terminal as well as save. By using Vim the only process I need to worry about is editing the code.

<br>


### However, this is not true for all cases. If I am in a situation where multiple files affect each other I need to be able to see error messages occur immediately. It really depends on the level of editing I would need to do. Singular changes such as the one demonstrated above would only need Vim. However any large scale changes should be made on a local environment and IDE. 