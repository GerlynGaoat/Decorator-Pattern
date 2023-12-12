package SoftwareEngineering1;
public class CIMB {

	public static void main(String[] args) {
		
		System.out.println("Gerlyn Gaoat | 3BSCS-2\n");
		System.out.println("CIMB Bank Report\n");
		
		BankAccount account = new BankAccount();
        account.setAccountNumber(1234);
        account.setAccountName("Juan Dela Cruz");
        account.setBalance(10000.0);

        System.out.println(account.showInfo());
        System.out.println("Account type: " + account.showAccountType());
        System.out.println("Interest rate: " + account.getInterestRate());
        System.out.println("New balance: " + account.computeBalanceWithInterest());
        System.out.println("Benefits: " + account.showBenefits());

        System.out.println("----------------------");

        GSave gSave = new GSave(account);
        System.out.println(gSave.showInfo());
        System.out.println("Account type: " + gSave.showAccountType());
        System.out.println("Interest rate: " + gSave.getInterestRate());
        System.out.println("New balance: " + gSave.computeBalanceWithInterest());
        System.out.println("Benefits: " + gSave.showBenefits());

        System.out.println("----------------------");

        UpSave upSave = new UpSave(account);
        System.out.println(upSave.showInfo());
        System.out.println("Account type: " + upSave.showAccountType());
        System.out.println("Interest rate: " + upSave.getInterestRate());
        System.out.println("New balance: " + upSave.computeBalanceWithInterest());
        System.out.println("Benefits: " + upSave.showBenefits());
    }
}

//Interface: BankAccount
	interface BankAccount1 {
	    double getInterestRate();
	    double computeBalanceWithInterest();
	    String showInfo();
	    String showAccountType();
	    double getBalance();
	    String showBenefits();
	}
//Concrete Component: SavingsAccount	
class BankAccount implements BankAccount1 {
	    private int accountNumber;
	    private String accountName;
	    private double balance;

	    public double getInterestRate() {
	        return 0.01;
	    }

	    public double computeBalanceWithInterest() {
	        return balance * (1 + getInterestRate());
	    }

	    public String showInfo() {
	        return "Account number: " + accountNumber + "\nAccount name: " + accountName + "\nBalance: " + balance;
	    }

	    public String showAccountType() {
	        return "Savings Account";
	    }

	    public double getBalance() {
	        return balance;
	    }

	    public String showBenefits() {
	        return "Standard Savings Account";
	    }

	    // Setters for account details
	    public void setAccountNumber(int accountNumber)
	    {this.accountNumber = accountNumber;}

	    public void setAccountName(String accountName) 
	    {this.accountName = accountName;}

	    public void setBalance(double balance) 
	    {this.balance = balance;}
	}

	// Interface: BankAccountDecorator
	interface BankAccountDecorator extends BankAccount1 {
	    void setBankAccount(BankAccount bankAccount);
	}

	//Concrete Decorator: GSave
	class GSave implements BankAccountDecorator {
	 private BankAccount bankAccount;

	 public GSave(BankAccount bankAccount) 
	 {this.bankAccount = bankAccount;}

	 public void setBankAccount(BankAccount bankAccount) 
	 {this.bankAccount = bankAccount;}

	 public double getInterestRate() {
	     return 0.025;
	 }

	 public double computeBalanceWithInterest() {
	     return bankAccount.getBalance() * (1 + getInterestRate());
	 }

	 public String showInfo() {
	     return bankAccount.showInfo();
	 }

	 public String showAccountType() {
	     return "GSave";
	 }

	 public double getBalance() {
	     return computeBalanceWithInterest();
	 }

	 public String showBenefits() {
	     return bankAccount.showBenefits() + ", GCash Transfer";
	 }
	}

	//Concrete Decorator: UpSave
	class UpSave implements BankAccountDecorator {
	 private BankAccount bankAccount;

	 public UpSave(BankAccount bankAccount) 
	 {this.bankAccount = bankAccount;}


	 public void setBankAccount(BankAccount bankAccount) 
	 {this.bankAccount = bankAccount;}

	 public double getInterestRate() {
	     return 0.04;
	 }

	 public double computeBalanceWithInterest() {
	     return bankAccount.getBalance() * (1 + getInterestRate());
	 }

	 public String showInfo() {
	     return bankAccount.showInfo();
	 }

	 public String showAccountType() {
	     return "UpSave";
	 }

	 public double getBalance() {
	     return computeBalanceWithInterest();
	 }

	 public String showBenefits() {
	     return bankAccount.showBenefits() + ", With Insurance";
	 }
}
