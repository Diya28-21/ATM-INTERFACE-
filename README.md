# ATM-INTERFACE-
import java.util.*;
class Account
{
	 Scanner sc = new Scanner(System.in);
	int p=0;
    int b=0;
    int d=0;
    int balance;
    int option;
    
    public void deposit()
    {
      System.out.println("Enter your deposit amount:-");
                int amount = sc.nextInt();
                balance = balance + amount;
                b = balance;
                System.out.println("Deposit successful");
    } 
    public void withdrew()
    {
    	System.out.println("Enter your withdraw amount:-");
                int amount = sc.nextInt();
                if (balance < amount) 
                {
                    System.out.println("Insufficient balance");
                } 
                else 
                {
                    balance = balance - amount;
                    d = balance;

                }

    }
    public void checkbal()
    {
      p = balance;
      System.out.println("Current balance = " + p);
    }
   
} 
class Atm extends Account
{
	
	void acc()
	{
    Scanner sc = new Scanner(System.in);
	
	System.out.println("Enter holder Name:-");
	String name=sc.nextLine();
    System.out.println("Enter holder Account No.:-");
    long accno=sc.nextLong();	
	 while(option != 4)
	 {
	    System.out.println("1.Deposite\n 2.withdraw\n 3.Check Balance\n 4.exit");
        System.out.println("Enter your option");
        option=sc.nextInt();
		switch(option)
		{
		case 1:
			deposit();
			break;
		case 2:
			withdrew();
			break;
		case 3:
			checkbal();
			break;
		case 4:
			int exit;
		default:
			System.out.println("invalid option");
		}
	
      }
    }
     void disp()
    {
    	System.out.println("Balance after deposit= "+b);
        System.out.println("Balance after withdraw= "+d);
        System.out.println("Current balance="+p);
    }
    
}
class Bank
{
	public static void main(String args[])
	{
      Atm a = new Atm();
      a.acc();
      a.disp();
	}
}
