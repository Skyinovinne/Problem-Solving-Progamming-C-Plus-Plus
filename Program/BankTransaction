#include <iostream>
#include <cmath>
#include <iomanip>
using namespace std;

// Precondition: <Length> is greater than 0
// Postcondition: Prints <length> dashes
void drawSeparator(int length)
{
	for (int i = 0; i != length; i++)
	{
		cout << "-";
	}
}

// Precondition: Min is less than max
// Postcondition: Validates the user's input and return if between min and max
int readInt(int min, int max)
{
	while (true) {
		int result;
		cout << ">> ";
		cin >> result;
		cout << endl;

		if (cin.fail() || cin.peek() >= ' ')
		{
			cin.clear();
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			cout << "Enter a valid number" << endl;
		}
		else if (result < min || result > max)
		{
			cout << "Enter a number between " << min << " and " << max << endl;
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
		}
		else
		{
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			return result;
		}
	}
}
// Precondition: Min is less than max
// Postcondition: Validates the user's input and return if between min and max
double readDouble(double min, double max)
{
	while (true) {
		double result;
		cout << ">> ";
		cin >> result;
		cout << endl;

		if (cin.fail() || cin.peek() >= ' ')
		{
			cin.clear();
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			cout << "Enter a valid number" << endl;
		}
		else if (result < min)
		{
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			cout.unsetf(ios_base::floatfield);
			cout << "Enter a number greater than " << min << fixed << endl;
		}
		else if (result > max)
		{
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			cout << "Enter a number less than " << fixed << max << endl;
		}
		else
		{
			cin.ignore(numeric_limits<streamsize>::max(), '\n');
			return result;
		}
	}
}

// Precondition: Balance is greater than or equal to 0
// Postcondition: Returns the balance after the withdrawal
double withdrawal(double balance)
{
	cout << "How much do you want to withdraw?" << endl;
	double withdrawal = readDouble(0, balance);

	balance -= withdrawal;
	cout << "Amount Withdrawn: $" << withdrawal << endl;
	cout << "New Balance: $" << balance << endl << endl;
	return balance;
}

// Precondition: None
// Postcondition: Returns the balance after the deposit
double deposit(double balance)
{
	cout << "How much do you want to deposit?" << endl;
	double deposit = readDouble(0, numeric_limits<double>::max());

	balance += deposit;
	cout << "Amount Deposited: $" << deposit << endl;
	cout << "New Balance: $" << balance << endl << endl;
	return balance;
}

// Precondition: None
// Postcondition:
// Ask the user for loan amount, months, and credit score.
// Calculate and display monthly payment according to user's input
// payment = ((loan * (1 + interest rate ) to the power of ( month / 12)) divided by the number of months
void loan()
{
	cout << "How much do you want to borrow?" << endl;
	double principal = readDouble(0, numeric_limits<double>::max());

	cout << "How many months will you take to pay off the loan?" << endl;
	int months = readInt(1, 1200);

	// Credit score only range from 300 to 850 (FIPS)
	cout << "What is your credit score?" << endl;
	int creditScore = readInt(300, 850);

	double interest;
	if (creditScore >= 701)
	{
		interest = 0.01;
	}
	else if (creditScore <= 700 && creditScore >= 501)
	{
		interest = 0.02;
	}
	else
	{
		interest = 0.05;
	}
	double payment = principal*(pow(1 + interest, months / 12.0)) / months;

	drawSeparator(40);
	cout << endl << "Your interest rate is " << setprecision(0) << interest * 100 << "%" << endl;
	cout << "Your monthly payment is $" << setprecision(2) << fixed << payment << endl;
}

int main()
{
	double balance = 10000;
	cout << "Welcome to the bank!" << endl;

	while (true) {
		drawSeparator(40);

		// Display a menu to the user
		cout << endl << "Balance: $" << setprecision(2) << fixed << balance << endl;
		cout << "1. Withdrawal" << endl;
		cout << "2. Deposit" << endl;
		cout << "3. Loan" << endl;
		// Gives the option for user to exit if they're done
		cout << "4. Exit" << endl;

		// Performs the menu action
		switch (readInt(1, 4))
		{
		case 1: 
			balance = withdrawal(balance);
			break;
		case 2:
			balance = deposit(balance);
			break;
		case 3:
			loan();
			break;
		case 4:
			return 0;
		default:
			break;
		}
	}
}
