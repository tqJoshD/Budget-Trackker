/******************************************************************************

Welcome to GDB Online.
  GDB online is an online compiler and debugger tool for C, C++, Python, PHP, Ruby,
  C#, OCaml, VB, Perl, Swift, Prolog, Javascript, Pascal, COBOL, HTML, CSS, JS
  Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>
#include <string>
using namespace std;
int TotalAllowance = 0;

int foodEX = 0;
int fairEX = 0;
int schoolEX = 0;
int funEX = 0;
int miscEX = 0;

int food();
int fair();
int school();
int fun();
int misc();

int foodExpenses[7];
int fairExpenses[7];
int schoolExpenses[7];
int funExpenses[7];
int miscExpenses[7];

string week[7] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};

int WeeklyAllowance() {
	int weeklyallowance, choicesWA, whatif;

	cout << "Enter your Weekly Allowance:";
	cin >> weeklyallowance;
	TotalAllowance += weeklyallowance;
	cout <<"Your weekly allowance is:" << weeklyallowance << endl << "Return to features? (Press 1 - Yes, 0 - No )";
	cin >> choicesWA;

	if (choicesWA == 1)
		return 1;
	else if (choicesWA == 0) {
		int choicevg;
		cout << "Do you want to add an allowance? (1 - yes, 0 - no)\n";
		cin >> choicevg;
		if (choicevg == 1) {
			cout << "Add more allowance:\n";
			cin >> whatif;
			TotalAllowance += whatif;
			cout << "Your allowance is now " << TotalAllowance << endl;
		}
		else if (choicevg == 0) {
			return 1;
		}
		else if (choicesWA != 1 && choicesWA != 0) {
			cout << "You have entered a wrong number, your laptop is now corrupted jk. \n Going back to the main interface...\n";
			return 1;
		}
		return 0;
	}
}
int InputAllowance() {
	int ChosenCategory;
	cout << "You've chosen to input your Weekly Expenses. Choose a Category to input with: \n (1) - Food \n (2) - Fair \n (3) - School Expenses \n (4) - Entertainment \n (5) - Miscellaneous \n Enter a number:";
	cin >> ChosenCategory;
	switch (ChosenCategory) {
	case 1:
		food();
		break;
	case 2:
		fair();
		break;
	case 3:
		school();
		break;
	case 4:
		fun();
		break;
	case 5:
		misc();
		break;
	default:
		cout << "Invalid choice! Please enter a number between 1 and 5.\n";
	}
	return 0;
}

int food() {
	int foodex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your food expenses in " << week[i] << ":  \n";
		cin >> foodex;
		foodExpenses[i] = foodex;
		foodEX += foodExpenses[i];
	}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 0 - no):\n";
	cin >> Choice2;
	if (Choice2 == 1) {
		InputAllowance();
	}
	else if (Choice2 == 0) {
		return 1;
	}
	else if (Choice2 != 1 && Choice2 != 0) {
		cout << "Invalid Number! Now it's lagging!";
		return 1;
	}
	return 0;
}

int fair() {
	int fairex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your fair expenses in " << week[i] << ":  \n";
		cin >> fairex;
		fairExpenses[i] = fairex;
		fairEX += fairExpenses[i];
	}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 0 - no):\n";
	cin >> Choice2;
	if (Choice2 == 1) {
		InputAllowance();
	}
	else if (Choice2 == 0) {
		return 1;
	}
	else if (Choice2 != 1 && Choice2 != 0) {
		cout << "Invalid Number! Now it's lagging!";
		return 1;
	}
	return 0;
}

int school() {
	int schoolex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your school expenses in " << week[i] << ": \n ";
		cin >> schoolex;
		schoolExpenses[i] = schoolex;
		schoolEX += schoolExpenses[i];
	}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 0 - no):\n";
	cin >> Choice2;
	if (Choice2 == 1) {
		InputAllowance();
	}
	else if (Choice2 == 0) {
		return 1;
	}
	else if (Choice2 != 1 && Choice2 != 0) {
		cout << "Invalid Number! Now it's lagging!";
		return 1;
	}
	return 0;
}

int fun() {
	int funex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your entertainment expenses in " << week[i] << ": \n ";
		cin >> funex;
		funExpenses[i] = funex;
		funEX += funExpenses[i];
	}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 0 - no):\n";
	cin >> Choice2;
	if (Choice2 == 1) {
		InputAllowance();
	}
	else if (Choice2 == 0) {
		return 1;
	}
	else if (Choice2 != 1 && Choice2 != 0) {
		cout << "Invalid Number! Now it's lagging!";
		return 1;
	}
	return 0;
}
int misc() {
	int miscex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your miscellaneous expenses in " << week[i] << ":  "<< endl;
		cin >> miscex;
		miscExpenses[i] = miscex;
		miscEX += miscExpenses[i];
	}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 0 - no):" << endl;
	cin >> Choice2;
	if (Choice2 == 1) {
		InputAllowance();
	}
	else if (Choice2 == 0) {
		return 1;
	}
	else if (Choice2 != 1 && Choice2 != 0) {
		cout << "Invalid Number! Now it's lagging!";
		return 1;
	}
	return 0;
}


int Vfood() {
	for (int i = 0; i < 7; i++) {
		cout << "Your food expenses in " << week[i] << "is " << foodExpenses[i] << endl;

	}
	cout << "Your total food expenses is " << foodEX;
	return 0;
}

int Vfair() {
	for (int i = 0; i < 7; i++) {
		cout << "Your fair expenses in " << week[i] << "is " << fairExpenses[i] << endl;

	}
	cout << "Your total fair expenses is " << fairEX;
	return 0;
}

int VSchool() {
	for (int i = 0; i < 7; i++) {
		cout << "Your school expenses in " << week[i] << "is " << schoolExpenses[i] << endl;

	}
	cout << "Your total school expenses is " << schoolEX;
	return 0;
}

int Vfun() {
	for (int i = 0; i < 7; i++) {
		cout << "Your entertainment expenses in " << week[i] << "is " << funExpenses[i] << endl;

	}
	cout << "Your total fun expenses is " << funEX;
	return 0;
}

int Vmisc() {
	for (int i = 0; i < 7; i++) {
		cout << "Your miscellaneous expenses in " << week[i] << "is " << miscExpenses[i] << endl;

	}
	cout << "Your total miscellaneous expenses is " << miscEX;
	return 0;
}
int ViewExpenses() {
	int choiceRT;
	cout << "Choose a category to see your expenses:\n (1) - Food \n (2) - Fair \n (3) - School Expenses \n (4) - Entertainment \n (5) - Miscellaneous \n Enter a number: ";
	cin >> choiceRT;
	switch (choiceRT) {
	case 1:
		Vfood();
		break;
	case 2:
		Vfair();
		break;
	case 3:
		VSchool();
		break;
	case 4:
		Vfun();
		break;
	case 5:
		Vmisc();
		break;
	default:
		cout << "Invalid choice! Please enter a number between 1 and 5.\n";
	}
	return 0;
}

int RemainingAllowance() {
	int TotalExpenses, RemainingAllowance;
	TotalExpenses = foodEX + fairEX + schoolEX + funEX + miscEX;
	cout << "The total expenses you spent this week is:" << TotalExpenses << endl;
	RemainingAllowance = TotalAllowance - TotalExpenses;
	if (RemainingAllowance > 0) {
		cout << "You have " << RemainingAllowance << "pesos remaining."<< endl;
	}
	else {
		cout << "You have a debt of " << abs(RemainingAllowance) << ". PAY UP!\n";
	}
	return 0;
}


int main() {
	int num1;
	while (true) {
		cout<< "Good Day! Welcome to the Weekly Budget Tracker. (To proceed enter the number for your chosen feature!):\n (1) - Input Weekly Allowance \n (2) - Input Weekly Expenses \n (3) - View Weekly Expenses \n (4) - View Remaining Allowance \n Enter the number:";
		cin >> num1;
		switch (num1) {
		case 1:
			WeeklyAllowance();
			break;
		case 2:
			InputAllowance();
			break;
		case 3:
			ViewExpenses();
			break;
		case 4:
			RemainingAllowance();
			break;
		case 5:
			cout << "Exiting program. Have a great day!" << endl;
			return 0;
			break;
		}
	}
	return 0;
}
