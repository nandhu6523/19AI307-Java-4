
# Exp No - 5

## TITLE : Design Patterns - II

### AIM :
To demonstrate the MVC (Model-View-Controller) design pattern using a bank account system.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Create Model (BankAccount) to store and manage balance

STEP 3 : Create View (AccountView) to display output

STEP 4 : Create Controller (AccountController) to handle operations

STEP 5 : Read initial balance

STEP 6 : Read number of operations

STEP 7 : For each operation:
       If deposit → update balance
       If withdraw → check and update balance

STEP 8 : Display results using View

STEP 9 : End

### PROGRAM :
```
import java.util.Scanner;

public class BankMVC {

    // Model
    static class BankAccount {
        private double balance;

        public BankAccount(double initialBalance) {
            this.balance = initialBalance;
        }

        public void deposit(double amount) {
            if (amount > 0) balance += amount;
        }

        public boolean withdraw(double amount) {
            if (amount > 0 && balance >= amount) {
                balance -= amount;
                return true;
            }
            return false;
        }

        public double getBalance() {
            return balance;
        }
    }

    // View
    static class AccountView {
        public void showBalance(double balance) {
            System.out.printf("Current Balance: ₹%.2f%n", balance);
        }

        public void showError(String message) {
            System.out.println(message);
        }
    }

    // Controller
    static class AccountController {
        private BankAccount account;
        private AccountView view;

        public AccountController(BankAccount account, AccountView view) {
            this.account = account;
            this.view = view;
        }

        public void deposit(double amount) {
            account.deposit(amount);
            view.showBalance(account.getBalance());
        }

        public void withdraw(double amount) {
            boolean success = account.withdraw(amount);
            if (success) {
                view.showBalance(account.getBalance());
            } else {
                view.showError("Withdrawal failed: insufficient balance.");
            }
        }

        public void showBalance() {
            view.showBalance(account.getBalance());
        }
    }

    // Main – User Input and Test Cases
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double initialBalance = sc.nextDouble();
        BankAccount model = new BankAccount(initialBalance);
        AccountView view = new AccountView();
        AccountController controller = new AccountController(model, view);

        int operations = sc.nextInt();
        for (int i = 0; i < operations; i++) {
            String op = sc.next();
            double amount = sc.nextDouble();
            if (op.equalsIgnoreCase("deposit")) {
                controller.deposit(amount);
            } else if (op.equalsIgnoreCase("withdraw")) {
                controller.withdraw(amount);
            }
        }

        sc.close();
    }
}
```

### OUTPUT :

<img width="1006" height="728" alt="image" src="https://github.com/user-attachments/assets/00bf8bbd-2200-4092-8504-5133e1063d11" />

### RESULT :

Thus to demonstrate the MVC (Model-View-Controller) design pattern using a bank account system was successfully created.
