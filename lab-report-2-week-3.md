# Lab Report 2 #
## **Simplest Search Engine Code**

```

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> groceries = new ArrayList<String>();
    int num = 0;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("List: %s", groceries);
        } else if (url.getPath().equals("/search")) {
            String[] parameters1 = url.getQuery().split("=");
            if(parameters1[0].equals("s")){
                for(int i = 0; i<groceries.size(); i++){
                    if(groceries.get(i).contains(parameters1[1])){
                        return String.format("Result: %s", groceries.get(i));
                    }
                    else{
                        return String.format("Not found");
                    }
                }
                }
            
            //num += 1;
            //return String.format("Searched");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters2 = url.getQuery().split("=");
                if (parameters2[0].equals("s")) {
                    groceries.add(parameters2[1]);
                    return String.format("%s has been added", parameters2[1]);
        
                }
            }
            //return "404 Not Found!";
        }
        return "404 Not Found!";
    }
    
```
---
## Search Engine Demonstration 
---
![addpic](Screenshots\week3pic1.PNG)

### **The method add is called and the parameter in the url is attributed to the letter s. The object after it is the string that will be added to the Array List.** 
#
### **The Path is delineated by the / symbol. This allows us to create multiple paths that essentially allow us to create method calls that take in parameters and return results**
#
![searchpic](Screenshots\week3pic2.PNG)
### **As we can see with the search function we do not need to type out an entire item as all the method checks for is whether the letter "b" is contained in the string.** 
#
![listpic](Screenshots\week3pic.PNG)
### **The current list with only one addition**
---
<br>
<br>
<br>
<br>
<br>

# Lab Report 2 Part Two #

![codeProblem](Screenshots\testfail1.PNG)

### The test array is 7, 6, 5, 4, 3, 2, 1. 
### The expected return is 1, 2, 3, 4, 5, 6, 7. 
### However, at the position of element 4, it expected an element that was two indicies off. In an array such as 1,2,3,4,5,6 it would return 6, 5, 4, 4, 5, 6.
<br>

![codeProblemcode](Screenshots\testfail1code.PNG)

<br>

### This occured due to the array element being set to itself with the middle index also being changed. Intuitively it would make sense in a sequence such as 3, 2, 1 to swap the numbers 1 and 3. 

![codeProblemFixed](Screenshots\testfail1codefixed.PNG)

<br>

### The solution is to decrease the iterator by half and set a placeholder variable that holds each value which is then set to the array at the next position in the iteration. The last value is the first one to be placed in the beginning of the array.

<br>

## **Symptoms and Bugs**

### It is important to understand that arrays start indexing from the number 0 when measured from left to right. In an array with 5 elements there would be 5 indices however since 0 is its own index we would first subtract 1 from it as there would technically be no [5] element to access and would result in an out of bounds error. 
<br>

### This means that in order to avoid confusion we must not think of array manipulation in matters of pure math but rather keeping in mind how indicies are counted. This is why it would make sense to take half of the length of the array to sort. 