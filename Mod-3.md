
# Exp No - 3

## TITLE : UML and Class Diagrams

### AIM : 
To demonstrate composition by creating a Library class that contains Book objects.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Define Book class with title and author

STEP 3 : Define Library class with a list of books

STEP 4 : Read number of books n

STEP 5 : For each book:

STEP 6 : Read title and author

STEP 7 : Add book to library

STEP 8 : Display all books in library

STEP 9 : End

### PROGRAM :
```
import java.util.*;

public class CompositionExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Library library = new Library();

        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String title = sc.nextLine();
            String author = sc.nextLine();
            library.addBook(title, author);
        }

        library.showBooks();
        sc.close();
    }
}

class Book {
    private String title;
    private String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }

    public String getDetails() {
        return title + " by " + author;
    }
}

class Library {
    // Composition: Library owns the Book objects
    private List<Book> books;

    public Library() {
        books = new ArrayList<>();
    }

    public void addBook(String title, String author) {
        Book book = new Book(title, author); // Book created inside Library
        books.add(book);
    }

    public void showBooks() {
        System.out.println("Books in Library:");
        for (Book book : books) {
            System.out.println("- " + book.getDetails());
        }
    }
}

```

### OUTPUT :

<img width="882" height="545" alt="image" src="https://github.com/user-attachments/assets/1f3c9b5b-300c-410c-bebc-357ea9d90122" />

### RESULT :

Thus to demonstrate composition by creating a Library class that contains Book objects was successfully created.
