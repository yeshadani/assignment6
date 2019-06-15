# assignment6








#include <iostream>
#include <iomanip>
using namespace std;

int main() {
	//variables
	float annualRate, monthlyRate, loanAmount, monthlyPay, totalPay, totalInterest;
	int numberOfPayments;

	//getting user inputs
	cout << "Enter the loan amount: ";
	cin >> loanAmount;
	if (loanAmount <= 0)
		cout << "ERROR! The loan amount should be a non-zero positive number!" << endl;
	else {
		cout << "Enter the annual interest rate: ";
		cin >> annualRate;
		if (annualRate <= 0)
			cout << "ERROR! The annual interest rate should be a non-zero positive number!" << endl;
		else {
			cout << "Enter the number of payments: ";
			cin >> numberOfPayments;
			if (numberOfPayments <= 0)
				cout << "ERROR! The number of payments should be a non-zero positive number!" << endl;
			else {
				
				//calculations
				monthlyRate = annualRate / 12;
				monthlyPay = ((monthlyRate/100) * pow(1 + (monthlyRate/100), numberOfPayments)) / (pow(1 + (monthlyRate/100), numberOfPayments) - 1) * loanAmount;
				totalPay = monthlyPay * numberOfPayments;
				totalInterest = totalPay - loanAmount;

				//setup output formatting
				cout << fixed << setprecision(2);

				//output
				cout << setw(25) << left << "Loan Amount: " << "$" << setw(10) << right << loanAmount << endl;
				cout << setw(25) << left << "Monthly Interest Rate: " << setw(10) << right << monthlyRate << "%" << endl;
				cout << setw(25) << left << "Number of Payments: " << setw(11) << right << numberOfPayments << endl;
				cout << setw(25) << left << "Monthly Payments: " << "$" << setw(10) << right << monthlyPay << endl;
				cout << setw(25) << left << "Amount Paid Back: " << "$" << setw(10) << right << totalPay << endl;
				cout << setw(25) << left << "Interest Paid: " << "$" << setw(10) << right << totalInterest << endl;
			}
		}
	}

	
	return 0;
}
