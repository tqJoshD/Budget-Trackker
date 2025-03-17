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
int fareEX = 0;
int schoolEX = 0;
int funEX = 0;
int miscEX = 0;

int food();
int fare();
int school();
int fun();
int misc();

int foodExpenses[7];
int fareExpenses[7];
int schoolExpenses[7];
int funExpenses[7];
int miscExpenses[7];

string week[7] = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};

int WeeklyAllowance(){
    int weeklyallowance, choicesWA, additionalAmount;

    cout << "Enter your Weekly Allowance: ";
    cin >> weeklyallowance;
    TotalAllowance += weeklyallowance;
    cout << "Your total allowance is now: " << TotalAllowance << endl;

    cout << "Return to features? (Press 1 - Yes, 2 - No): ";
    cin >> choicesWA;

    switch (choicesWA) {
        case 1:
            return 1;  
        case 2: {
            int choicevg;
            cout << "Do you want to add more allowance? (1 - Yes, 2 - No): ";
            cin >> choicevg;

            while (choicevg != 1 && choicevg != 2) {  
                cout << "Invalid input! Please choose (1 - Yes, 2 - No): ";
                cin >> choicevg;
            }

            if (choicevg == 1) {
                cout << "Enter additional amount: ";
                cin >> additionalAmount;
                TotalAllowance += additionalAmount;
                cout << "Your total allowance is now: " << TotalAllowance << endl;
            }
            return 1;
        }
        default:
            cout << "Invalid input! Returning to menu.\n";
            return 1;
    }
}
	

int InputAllowance(){
	int ChosenCategory;
	cout << "You've chosen to input your Weekly Expenses. Choose a Category to input with: \n (1) - Food \n (2) - Fare \n (3) - School Expenses \n (4) - Entertainment \n (5) - Miscellaneous \n (6) - Exit \nEnter a number:";
	cin >> ChosenCategory;
	switch (ChosenCategory) {
	case 1:
		food();
		break;
	case 2:
		fare();
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
	case 6:
	    return 1;
	default:
		cout << "Invalid choice! Please enter a number between 1 and 5:\n";
	}
	return 0;
}

int food(){
	int foodex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your food expenses in " << week[i] << ":  \n";
		cin >> foodex;
		foodExpenses[i] = foodex;
		foodEX += foodExpenses[i]; }
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 2 - no):" << endl;
	cin >> Choice2;
	switch (Choice2){
	    case 1:
	        InputAllowance();
	        return 0;
	    case 2:
	        return 1;
	    default:
	        cout << "Invalid Number! Now it's lagging! Enter a 1 - yes, 2 - no: ";
	}
	return 0;
}

int fare(){
	int fareex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your fare expenses in " << week[i] << ":  \n";
		cin >> fareex;
		fareExpenses[i] = fareex;
		fareEX += fareExpenses[i];}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 2 - no):" << endl;
	cin >> Choice2;
	switch (Choice2){
	    case 1:
	        InputAllowance();
	        return 0;
	    case 2:
	        return 1;
	    default:
	        cout << "Invalid Number! Now it's lagging! Enter a 1 - yes, 2 - no: ";
	}
	return 0;
}

int school(){
	int schoolex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your school expenses in " << week[i] << ": \n ";
		cin >> schoolex;
		schoolExpenses[i] = schoolex;
		schoolEX += schoolExpenses[i];}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 2 - no):" << endl;
	cin >> Choice2;
	switch (Choice2){
	    case 1:
	        InputAllowance();
	        return 0;
	    case 2:
	        return 1;
	    default:
	        cout << "Invalid Number! Now it's lagging! Enter a 1 - yes, 2 - no: ";
	}
	return 0;
}

int fun(){
	int funex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your entertainment expenses in " << week[i] << ": \n ";
		cin >> funex;
		funExpenses[i] = funex;
		funEX += funExpenses[i];}
    int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 2 - no):" << endl;
	cin >> Choice2;
	switch (Choice2){
	    case 1:
	        InputAllowance();
	        return 0;
	    case 2:
	        return 1;
	    default:
	        cout << "Invalid Number! Now it's lagging! Enter a 1 - yes, 2 - no: ";
	}
	return 0;
}
int misc(){
	int miscex;
	for (int i = 0; i < 7; i++) {
		cout << "Enter your miscellaneous expenses in " << week[i] << ":  "<< endl;
		cin >> miscex;
		miscExpenses[i] = miscex;
		miscEX += miscExpenses[i];}
	int Choice2;
	cout << "Enter expenses for another category? (1 - yes, 2 - no):" << endl;
	cin >> Choice2;
	switch (Choice2){
	    case 1:
	        InputAllowance();
	        return 0;
	    case 2:
	        return 1;
	    default:
	        cout << "Invalid Number! Now it's lagging! Enter a 1 - yes, 2 - no: ";
	}
	return 0;
}


int Vfood(){
	for (int i = 0; i < 7; i++) {
		cout << "Your food expenses in " << week[i] << " is: " << foodExpenses[i] << endl;}
	cout << "\nYour total food expenses is: " << foodEX << endl;
	return 0;
}

int Vfare(){
	for (int i = 0; i < 7; i++) {
		cout << "Your fare expenses in " << week[i] << " is: " << fareExpenses[i] << endl;}
	cout << "\nYour total fare expenses is: " << fareEX << endl;
	return 0;
}

int VSchool(){
	for (int i = 0; i < 7; i++) {
		cout << "Your school expenses in " << week[i] << " is: " << schoolExpenses[i] << endl;}
	cout << "\nYour total school expenses is: " << schoolEX << endl;
	return 0;
}

int Vfun(){
	for (int i = 0; i < 7; i++) {
		cout << "Your entertainment expenses in " << week[i] << " is: " << funExpenses[i] << endl;}
	cout << "\nYour total fun expenses is: " << funEX << endl;
	return 0;
}

int Vmisc(){
	for (int i = 0; i < 7; i++) {
		cout << "Your miscellaneous expenses in " << week[i] << " is: " << miscExpenses[i] << endl;}
	cout << "\nYour total miscellaneous expenses is: " << miscEX << endl;
	return 0;
}
int ViewExpenses(){
	int choiceRT;
	cout << "Choose a category to see your expenses:\n (1) - Food \n (2) - Fare \n (3) - School Expenses \n (4) - Entertainment \n (5) - Miscellaneous \n (6) - Exit \n Enter a number: ";
	cin >> choiceRT;
	switch (choiceRT) {
	case 1:
		Vfood();
		break;
	case 2:
		Vfare();
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
	case 6:
	    return 1;
	default:
		cout << "Invalid choice! Please enter a number between 1 and 5.\n";
	}
	return 0;
}

int RemainingAllowance(){
	int TotalExpenses, RemainingAllowance;
	TotalExpenses = foodEX + fareEX + schoolEX + funEX + miscEX;
	cout << "The total expenses you spent this week is:" << TotalExpenses << endl << "Your total allowance is " <<TotalAllowance <<".\n";
	RemainingAllowance = TotalAllowance - TotalExpenses;
	
	if (RemainingAllowance > 0) {
		cout << "You have " << RemainingAllowance << " pesos remaining. You better save it!"<< endl;
	}
	else {
		cout << "You have a debt of " << abs(RemainingAllowance) << ". PAY UP!\n";
	}
	return 0;
}


int main(){
	int num1;
	while (true) {
		cout<< "\nGood Day! Welcome to the Weekly Budget Tracker. (To proceed enter the number for your chosen feature!)\n (1) - Input Weekly Allowance \n (2) - Input Weekly Expenses \n (3) - View Weekly Expenses \n (4) - View Remaining Allowance\n (5) - Exit \nEnter the number:";
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
			cout << "Exiting program. Have a great day!\n" << endl;
			return 0;
			break;
		default:
		    cout << "Invalid choice! Please enter a number between 1 and 5.\n";
		}
	}
	return 0;
}
