
# Exp No - 4

## TITLE : Design Patterns - I

### AIM : To demonstrate the Prototype Design Pattern by cloning an object.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Define Prototype interface with clone() method

STEP 3 : Create Document class implementing Prototype

STEP 4 : Initialize original object with title and content

STEP 5 : Clone the object using clone() method

STEP 6 : Display both original and cloned objects

STEP 7 : End

### PROGRAM :
```
import java.util.*;

interface Prototype 
{
    Prototype clone();
}

class Document implements Prototype 
{
    private String title;
    private String content;

    public Document(String title, String content) 
    {
        this.title = title;
        this.content = content;
    }

    public void display(String type) 
    {
        System.out.println(type + ": " + title + " - " + content);
    }

    @Override
    public Prototype clone() 
    {
        return new Document(this.title, this.content);
    }
}

public class Main 
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);

        String title = sc.nextLine();
        String content = sc.nextLine();

        Document original = new Document(title, content);
        Document cloned = (Document) original.clone();

        original.display("Original Robot");
        cloned.display("Cloned Robot");
    }
}
```

### OUTPUT :

<img width="584" height="310" alt="image" src="https://github.com/user-attachments/assets/919b2a71-f635-4188-ae15-01a6522167fa" />

### RESULT :

Thus to demonstrate the Prototype Design Pattern by cloning an object was successfully created.
