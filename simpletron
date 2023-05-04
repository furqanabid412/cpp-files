/*Assignment 3*/

#include <iostream>
#include <iomanip>

using namespace std;
void programme1(int arr[], int size = 100)
{
	/*Use a sentinel-controlled loop to read positive numbers and compute and print their sum.Terminate input when a negative number is entered. */

	arr[0] = +1010;//read A
	arr[1] = +2010;//load A
	arr[2] = +4109;//Branch to location#9 if accumulator is negative
	arr[3] = +1011;//read B
	arr[4] = +2011;//load B
	arr[5] = +4109;//Branch to location#9 if accumulator is negative
	arr[6] = +3010;//add A
	arr[7] = +2112;//store C
	arr[8] = +1112;//write C
	arr[9] = +4300;//close program
}

void programme2(int arr[], int size = 100)
{
	/*Use a counter-controlled loop to read seven numbers, some positive and some negative,and compute and print their average. */

	arr[14] = -0007;//B
	arr[15] = +0007;//C
	arr[16] = +0001;//D
	arr[17] = +0000;//stores the value of A
	arr[18] = +0000;//stores the sum/average


	arr[0] = +1118;//write sum
	arr[1] = +2018;//load sum
	arr[2] = +1017;//read A 
	arr[3] = +3017;//add A
	arr[4] = +2118;//store sum
	arr[5] = +2014;//load B
	arr[6] = +3016;//add D
	arr[7] = +2114;//store B
	arr[8] = +4100;//Branch to location 00 if accumulator is negative
	arr[9] = +2018;//load sum
	arr[10] = +3215;//divide C
	arr[11] = +2118;//store sum
	arr[12] = +1118;//write average
	arr[13] = +4300;//close
}

void programme3(int arr[], int size = 100)
{
	/*Read a series of numbers, and determine and print the largest number. The first number read indicates how many numbers should be processed. */
	arr[23] = +0000;//a
	arr[24] = +0001;//b
	arr[25] = +0000;//c
	arr[26] = +0000;//d
	arr[27] = -0001;//e

	arr[0] = +1023;//read a
	arr[1] = +1025;//read c
	arr[2] = +2025;//load c
	arr[3] = +3126;//subtract d
	arr[4] = +4114;//Branch to a location#15if the accumulator is negative
	arr[5] = +2025;//load c
	arr[6] = +2126;//store d
	arr[7] = +2024;//load b
	arr[8] = +3123;//subtract a
	arr[9] = +3327;//multiply e
	arr[10] = +2123;//store a
	arr[11] = +3327;//multiply e
	arr[12] = +4100;//Branch to a location#00if the accumulator is negative
	arr[13] = +1126;//write d
	arr[14] = +4300;//program closed
	arr[15] = +2024;//load b
	arr[16] = +3123;//subtract a
	arr[17] = +3327;//multiply e
	arr[18] = +2123;//store a
	arr[19] = +3327;//multiply e
	arr[20] = +4100;//Branch to a location#00if the accumulator is negative
	arr[21] = +1126;//write d
	arr[22] = +4300;//program closed
}


int main()
{
	//printing header
	cout << "\t*** Welcome to Simpletron! ***\n*** Please enter your program one instruction ***\n";
	cout << "*** (or data word) at a time. I will type the ***\n*** location number and a question mark (?).  ***\n";
	cout << "*** You then type the word for that location. ***\n*** Type the sentinel -99999 to stop entering ***\n";
	cout << "*** your program. ***\n\n";

	int memory[1000];
	int j;
	for (j = 0; j < 1000; j++)
		memory[j] = 0;

	int accumulator = 0;//to represent the accumulator register
	int instructionCounter = 0;//to keep track of the location in memory that contains the instruction being performed
	int operationCode = 0;//to indicate the operation currently being performed
	int operand = 0;//to indicate the memory location on which the current instructions operates
	int instructionRegister = 0;//transfer the next instruction to be performed from memory to this variable

	for (instructionCounter = 0; instructionCounter < 1000; instructionCounter++)
	{
		if ((instructionCounter / 10) == 0)
			cout << "0" << instructionCounter << " ? ";
		else
			cout << instructionCounter << " ? ";

		cin >> memory[instructionCounter];
		if ((memory[instructionCounter]<-9999 || memory[instructionCounter] > 9999) && memory[instructionCounter] != -99999)
		{
			cout << "Error.Please enter the word in range of -9999 to 9999" << endl;
			instructionCounter--;
		}
		if (memory[instructionCounter] == -99999)
			break;
		if (memory[instructionCounter] < 0)
			memory[instructionCounter] *= -1;
	}
	memory[instructionCounter] = 0;




	//Functions call
	/*programme1(memory, 1000);
	programme2(memory, 1000);
	programme3(memory, 1000);*/
	





	cout << "\n*** Program loading completed ***\n*** Program execution begins ***\n\n\n";

	for (instructionCounter = 0; instructionCounter <1000; instructionCounter++)
	{
		if (memory[instructionCounter] == 0)
			break;

		instructionRegister = memory[instructionCounter];
		operationCode = instructionRegister / 100;
		operand = instructionRegister % 100;

		switch (operationCode){
		case 10://Read a word from the keyboard into a specific location in memory
		{
					cout << "Enter a number(it will store in memory location #):" << operand << "== ";
					cin >> memory[operand];
					break; }

		case 11://Write a word from a specific location in memory to the screen
		{cout << "The value is " << memory[operand] << endl;
		break; }

		case 20://Load a word from a specific location in memory into the accumulator
		{accumulator = memory[operand];
		cout << "Loaded in accumulator from loacation#" << operand << "\n";
		break; }

		case 21://Store a word from the accumulator into a specific location in memory.
		{memory[operand] = accumulator;
		cout << "Stored from accumulator to loacation#" << operand << "\n";
		break; }

		case 30: //Add a word from a specific location in memory to the word in the accumulator
		{cout << "adding " << memory[operand] << " & " << accumulator << endl;
		accumulator = accumulator + memory[operand];
		; break; }

		case 31: //Subtract a word from a specific location in memory from the word in the accumulator
		{cout << "subtracting " << memory[operand] << " from " << accumulator << endl;
		accumulator = accumulator - memory[operand];
		break; }

		case 32: //Divide a word from a specific location in memory into the word in the accumulator
		{cout << "Dividing " << accumulator << " by " << memory[operand] << endl;
		if (memory[operand] != 0)
			accumulator = accumulator / (memory[operand]);
		else
			cout << "*** Attempt to divide by zero ***\n*** Simpletron execution abnormally terminated ***\n";
		instructionCounter = 100;
		break; }


		case 33: //Multiply a word from a specific location in memory by the word in the accumulator(leave result in accumulator).
		{cout << "Multiplying " << accumulator << " with " << memory[operand] << endl;
		accumulator = accumulator*memory[operand];
		break; }

		case 34: //Taking the modoulous of a word from a specific location in memory by the word in the accumulator(leave result in accumulator).
		{cout << "Taking modolous of " << accumulator << " with " << memory[operand] << endl;
		accumulator = memory[operand] % accumulator;
		break; }


		case 40: //Branch to a specific location in memory
		{
					 instructionCounter = operand;
					 break; }

		case 41: //Branch to a specific location in memory if the accumulator is negative.
		{	if (accumulator < 0)
			instructionCounter = operand;
		break; }

		case 42: //Branch to a specific location in memory if the accumulator is zero
		{	if (accumulator == 0)
			instructionCounter = operand;
		break; }

		case 43: //Halt—the program has completed its task
		{ cout << "*** Simpletron execution terminated ***\n";
		instructionCounter = 100;
		break; }
		default:
		{
				   cout << "***Error!attempts to execute invalid operation codes***\n";
		}
		}
	}


	cout << endl;
	cout << "\tREGISTER\n";
	cout << "Accumulator\t\t" << setfill('0') << setw(5) << internal << showpos << accumulator << endl;
	cout << "InstructionCounter\t" << setfill('0') << setw(5) << internal << instructionCounter << endl;
	cout << "InstructionRegister\t" << setfill('0') << setw(5) << internal << showpos << instructionRegister << endl;
	cout << "OperationCode\t\t" << setfill('0') << setw(5) << internal << operationCode << endl;
	cout << "operand\t\t\t" << setfill('0') << setw(5) << internal << operand << endl << endl;

	cout << "\tMEMORY" << endl << endl << "\t";
	for (j = 0; j<10; j++)
		cout << setfill(' ') << setw(5) << internal << noshowpos << j << "\t";

	cout << endl;

	for (int i = 0; i <1000; i++)
	{
		if (i == 0)
			cout << setfill(' ') << setw(5) << internal << noshowpos << i << "\t";
		if (i % 10 == 0 && i != 0)
		{
			cout << endl;
			cout << setfill(' ') << setw(5) << internal << noshowpos << i << "\t";
		}


		cout << setfill('0') << setw(5) << internal << showpos << memory[i] << "\t";
	}

	cout << endl;
	cin.ignore();
	cin.get();
	return 0;
}
