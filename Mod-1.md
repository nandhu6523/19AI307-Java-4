# Exp No - 1

## TITLE : Exception Handling

### AIM : 
To demonstrate exception handling by handling division by zero.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Read two integers num1 and num2

STEP 3 : Try to divide num1 / num2

STEP 4 : If division is successful → print result

STEP 5 : If error occurs (division by zero) → catch exception and print error message

STEP 6 : End

### PROGRAM :
```
import java.util.Scanner;

public class DivisionExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num1 = sc.nextInt();
        int num2 = sc.nextInt();

        try {
            int result = num1 / num2;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero");
        }

        sc.close();
    }
}
```

### OUTPUT :

<img width="691" height="313" alt="image" src="https://github.com/user-attachments/assets/bd8c6b21-3fb9-444c-b74e-ba66b157905c" />

### RESULT :

Thus to demonstrate exception handling by handling division by zero was successfully created.

