import java.util.Scanner;

class BankAccount
{
    private double balance;

    public BankAccount(double initialBalance)
    {
        balance = initialBalance;
    }

    public double getBalance() 
    {
        return balance;
    }

    public void deposit(double amount)
    {
        if (amount > 0) 
        {
            balance += amount;
            System.out.println("Deposit successful. Your new balance is: $" + balance);
        } 
        else
        {
            System.out.println("Invalid deposit amount.");
        }
    }

    public boolean withdraw(double amount)
    {
        if (amount > 0 && amount <= balance)
        {
            balance -= amount;
            System.out.println("Withdrawal successful. Your new balance is: $" + balance);
            return true;
        } 
        else 
        {
            System.out.println("Invalid withdrawal amount or insufficient funds.");
            return false;
        }
    }
}

public class ATMinterface 
{
    private BankAccount account;

    public ATMinterface(BankAccount account)
    {
        this.account = account;
    }

    public void displayMenu()
    {
        System.out.println("\n\nWe welcome you at 'BANKRUPT BANK' ATM\nWith you, always...");
        System.out.println("1. Check your Balance");
        System.out.println("2. Deposit Money");
        System.out.println("3. Withdraw Money");
        System.out.println("4. Exit");
    }

    public void processChoice(int choice, Scanner sc)
    {
        switch (choice)
        {
            case 1:
                System.out.println("Your balance is: $" + account.getBalance());
                break;

            case 2:
                System.out.print("Enter the amount to deposit: $");
                double depositAmount = sc.nextDouble();
                account.deposit(depositAmount);
                break;

            case 3:
                System.out.print("Enter the amount to withdraw: $");
                double withdrawAmount = sc.nextDouble();
                account.withdraw(withdrawAmount);
                break;

            case 4:
                System.out.println("Thank you!\nYour money is safe with 'BANKRUPT BANK'");
                System.exit(0);
                break;

            default:
                System.out.println("Invalid choice!");
        }
    }

    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter your initial account balance: $");
        double initialBalance = sc.nextDouble();

        BankAccount userAccount = new BankAccount(initialBalance);
        ATMinterface atm = new ATMinterface(userAccount);

        while (true)
        {
            atm.displayMenu();
            System.out.print("Please select an option : ");
            int choice = sc.nextInt();
            atm.processChoice(choice, sc);
        }
    }
}
