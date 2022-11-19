# Lab Report Week 1 #
## **Installing Visual Studio Code**
---
### 1) Click link to Visual Studio Code download 

### [Download Link](https://code.visualstudio.com/download)

### 2) Click the download link and select the download that is appropriate for your operating system.
![screenshot2](Screenshots\codeinstall2.PNG)


## **Remotely Connecting** 
---
### Open the terminal function on VS Code 
![screenshot3](Screenshots\remoteconnect1.png)
### Type in without quotes "ssh cs15lfa22XX@ieng6.ucsd.edu"
### Replace XX with the two letters corresponding to your account as found in the account lookup tool. 
---
![screenshot4](Screenshots\remoteconnect2.PNG)
### The password option does not give any feedback however it does work. 

### On successful connection there should be a prompt that says "Hello [username], you are currently logged into ieng6-20X.ucsd.edu" 

--- 
## **Try some commands**
### Type pwd [print working directory] into the terminal press enter. 

### This should tell you the path of the directory that the remote connection is operating from.  
![screenshot5](Screenshots\trysomecommands.PNG)

--- 
## **Using scp to copy files to the remote server** 

### scp is a command that sends specific files to a specific directory to another computer or server. In this example it is used so that files can be compiled and ran using the remote server instead of the local machine [your personal PC]

### In order to send files to the remote server use the command scp followed by the filename, account, and the file path. 

### **Example** 

### WhereAmI.java is a simple program that prints out the user directory, the user name, and the operating system.

### Create a file in Visual Studio Code named WhereAmI.java and copy and paste this code: 
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

> ### scp WhereAmI.java cs15lfa22XX@ieng6.ucsd.edu:~/ 

### The symbols followed by the : indicate the parent path. The top essentially. 

> filename **:** ~/  

### Everything followed by the colon indicates the file path. 

--- 
## **Running file on local vs. remote using SCP example**

### The first picture shown below is when the WhereAmI.java program is run on the local machine. The operating system is Windows 10 and the user name is my own. 

![screenshot6](Screenshots\scp1.PNG)
### The picture shown below show is when the WhereAmI.java program is run on the remote server. 

![screenshot7](Screenshots\scp2.PNG)

--- 

## **Setting up a SSH key** 
### The ssh key is used to make logging into the remote server quicker. This is especially useful and convienient if multiple files are being transferred in one session with changes. 

### 1) Make sure you are using the local machine terminal. First type in: 
> ssh-keygen

### 2) You will then be prompted to enter a file to save the randomly generated key. Press enter without typing anything in and an automatic file path will be provided. 

### 3) Another prompt will ask for a passphrase. Leave this prompt blank and press enter. 

### 4) An image resembling a punch card will be printed with multiple symbols. This should indicate that the key creation was successful. 

### 5) The key has two files now. One must be saved on the local machine and the other on the remote server. 

### 6) On local login: 
>ssh cs15lfa22XX@ieng6.ucsd.edu
### 7) On the server: 
> mkdir .ssh
### 
> logout
### mkdir creates a directory that we can use to store the password in the local server

### 8) On the local machine type: 
> $ scp /Users/XXXX/.ssh/id_rsa.pub cs15lfa22XX@ieng6.ucsd.edu:~/.ssh/authorized_keys

### IMPORTANT: replace X's with relevant information such as user name and account name. 

![screenshot8](Screenshots\sshkey1.PNG) 

### As shown, I used scp to send over the file containing my password. Then I used my password. 

### Notice that after using ssh I do not have to input my password. 

---

## **Making Remote run more pleasant** 

### You can run multiple commands in the same line. For example:  

> cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI

### cp means copy. Javac compiles. The next java comamnd runs. 

