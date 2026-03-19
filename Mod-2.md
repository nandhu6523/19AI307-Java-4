
# Exp No - 2

## TITLE :  SOLID Principles

### AIM : To demonstrate the Singleton Design Pattern by ensuring only one instance of a class is used and tracking access count.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Create a class with a private static instance

STEP 3 : Use a private constructor to restrict object creation

STEP 4 : Provide getInstance() method to return single object

STEP 5 : Read number of users n

STEP 6 : For each user:

STEP 7 : Access the same instance

STEP 8 : Increment and display access count

STEP 9 : End

### PROGRAM :
```
import java.util.*;

// Singleton class
class MasterPowerSwitch {
    private static MasterPowerSwitch instance; // single instance
    private int accessCount; // shared access counter

    // Private constructor prevents instantiation from outside
    private MasterPowerSwitch() {
        accessCount = 0;
    }

    // Public method to get the single instance
    public static MasterPowerSwitch getInstance() {
        if (instance == null) {
            instance = new MasterPowerSwitch();
        }
        return instance;
    }

    // Increment access count and return current count
    public int logAccess() {
        accessCount++;
        return accessCount;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String player = sc.nextLine();
            MasterPowerSwitch power = MasterPowerSwitch.getInstance();
            int count = power.logAccess();
            System.out.println(player + " accessed Master Power Switch. Total accesses so far: " + count);
        }

        sc.close();
    }
}

```

### OUTPUT :

<img width="1236" height="318" alt="image" src="https://github.com/user-attachments/assets/eb48e924-e8ad-488c-9b14-3aff48e95da4" />

### RESULT :

Thus to demonstrate the Singleton Design Pattern by ensuring only one instance of a class is used and tracking access count was successfully created.
