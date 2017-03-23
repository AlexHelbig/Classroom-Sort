//************************************  PROGRAM INDENTIFICATION  ************************************
//*					                                                            *
//*   	PROGRAM FILE NAME: project3.cpp	       ASSIGNMENT #: 3 		GRADE:_____________         *
//*												    *
//*     PROGRAM AUTHOR:			________________________________________		    *
//*						     Alex Helbig				    *
//*											            *
//*     COURSE #: CSC 24400			    DUE DATE: FEBRUARY 28TH, 2017	            *
//*								                                    *
//***************************************************************************************************


//**************************************  PROGRAM DESCRIPTION  **********************************************
//*										                            *
//*		PROCESS:  This program code below is designed to effectively read in a series of various    *
//*		student ID's and their corresponding grade. The program then prints the original array of   *
//*		ID's and grades then sorts them accordingly based on either ID number of score. First       *
//*             it prints the array from high to low based on grades, then low to high based on ID number   *
//*		Once the list of students are sorted, the program will then calculate the average score,    *
//* 	        the highest value test score, and the lowest value test score.                              *
//*													    *
//*		USER DEFINED									            *
//*		 MODULES: header - Prints the header for the code with all my information		    *
//*		          readArray - Reads the text file selected and stores it into an array              *
//*		          printArray - Prints out the values from the text file into two columns            *
//*                       sortHighLow - Sorts the students grades from high to low based on grade           *
//*                       sortLowHigh - Sorts the students grades from low to high based on ID              *
//*                       findLow - Goes through the array to find and return the lowest grade              *
//*                       findLowID - Goes through the array to find and ID with the lowest grade           *
//*                       findHigh - Goes through the array to find and return the highest grade            *
//*                       findHighID - Goes through the array to find and ID with the highest grade         *
//*                       findAverage - Goes through the array to find and return the average grade         *
//*		          footer - Prints a message saying the code is completely done 	                    *
//*													    *
//***********************************************************************************************************





#include <iostream>
#include <fstream>
#include <string>
#include <iomanip>

using namespace std;

//Prototypes

    //Tells the code to look for the header function below
void header ( ofstream &output);

    //Tells the code to look for the readArray function below
void readArray( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the printArray function below
void printArray( ofstream &output, int StudID[], float Scores[],  int &EU);

    //Tells the code to look for the sortArray function below
void sortHighLow( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the sortArray function below
void sortLowHigh( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the findLow function below
float findLow( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the findLowID function below
int findLowID( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the findHigh function below
float findHigh( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the findHighID function below
int findHighID( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the findAverage function below
float findAverage( ifstream &input, int StudID[], float Scores[], int &EU);

    //Tells the code to look for the footer function
void footer (ofstream &output);




int main(){
    //Establishes an array for the ID numbers
int studentID[50];
    
    //Establishes an array for the test scores
float scores[50];
    
    //Sets the maximum amount of values for the arrays
int elementsUsed = 44;
    
float max;
float min;
int maxID;
int minID;
    
 
    //The variable input is linked to the text file
ifstream input("data3.txt", ios::in);
    
    
ofstream output("output.txt", ios::out);
    
output.setf(ios::fixed);
output.precision(1);
    
    //Prints the header
header(output);
    
    //Read in the values from the text file and store them into an array
readArray( input, studentID, scores, elementsUsed);


    //Print the values that were stored into the arrays from text file
printArray( output, studentID, scores, elementsUsed);
 
    cout << endl;
    cout << "The student data sorted highest to lowest by test scores are: " << endl;
    cout << endl;
    
    //Sort the values from the arrays from highest grade to lowest grades
sortHighLow( input, studentID, scores, elementsUsed);

    
    cout << endl;
    cout << "The student data sorted lowest to highest by student IDs are: " << endl;
    cout << endl;
    
    //Sort the values from the arrays from highest grade to lowest grades
sortLowHigh( input, studentID, scores, elementsUsed);

    
    cout << endl;
    
    //Find the lowest value grade from the array values
min = findLow( input, studentID, scores, elementsUsed);

    //Find the lowest value grade from the array values and pair it with the student ID
minID = findLowID( input, studentID, scores, elementsUsed);

    
cout << "The lowest test score was " << min << " achieved by student #" << minID << endl;
cout << endl;
    
    //Find the highest value grade from the array values
max = findHigh( input, studentID, scores, elementsUsed);

    
    //Find the highest value grade from the array values and pair it with the student ID
maxID = findHighID( input, studentID, scores, elementsUsed);

    
cout << "The highest test score was " << max << " achieved by student #" << maxID << endl;
    
    //Calculate the average test score out of all the values in the array
findAverage( input, studentID, scores, elementsUsed);

    
    //Prints the footer
footer(output);
    
    return 0;
    
}

//**************************************** FUNCTION HEADER ****************************

void header ( ofstream &output)
{
    // Receives - The output file
    // Task - Prints the output preamble
    // Returns - Nothing
    cout << setw(30) << "Alex Helbig";
    cout << setw(17) << "CSC 24400";
    cout << setw(15) << "Section 11" << endl;
    cout << setw(30) << "Spring 2017";
    cout << setw(20) << "Assignment #3" << endl;
    cout << setw(35) << "----------------------------------";
    cout << setw(35) << "----------------------------------" << endl << endl;
    return;
}
//************************************ END OF FUNCTION HEADER *************************










//************************************ FUNCTION HEADER *******************************
//
//          Recieves: Data read in by the ReadData function that
//              was read in by the file
//
//          Task: Reads in the array values and properly
//                stores them into two different arrays
//                to be used later
//
//          Returns: The two arrays for the program and stores them
//                    into the two arrays
//
//*********************************** END OF FUNCTION HEADER ***************************


void readArray( ifstream &input, int StudID[], float Scores[], int &EU)
    {
        int k;
        
        for (k = 0 ;  k < EU;  k++)
        {
            //Reads in the values and store them into two parrallel arrays
            input >> StudID[k] >> Scores[k];
        }
        return;
    
    
    }

//*********************************** END OF FUNCTION *********************************





//************************************ FUNCTION HEADER ********************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Prints the array into two seperate columns
//                matching the student ID with their grade
//
//          Returns: The list of student ID's and grades
//
//*********************************** END OF FUNCTION HEADER **************************


void printArray(ofstream &output, int StudID[], float Scores[], int &EU)
    {
        cout << "The original list of test scores is: " << endl;
        cout << setw(5) << "Student ID#"
                << "        " << "Test Score" << endl;
        int k;
        
        for (k = 0 ;  k < EU;  k++)
        {
            //Prints both array in two seperate columns
            cout << setw(7) << StudID[k]
                    << "               " << Scores[k]<<fixed<<setprecision(1)  << endl ;
        }
        return;

    }

//*********************************** END OF FUNCTION ********************************





//************************************ FUNCTION HEADER *******************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the scores and sorts them from highest
//                grade to lowest grade and prints the corresponding
//                ID number with the grade
//
//          Returns: The original list given sorted from highest
//                   grade to lowest grade
//
//*********************************** END OF FUNCTION HEADER **************************

void sortHighLow( ifstream &input, int StudID[], float Scores[], int &EU)
    {
        int i;
        int j;
        float tempScore;
        float tempID;
        
        for(i = 0; i < EU; i++)
        {
            for (j=(i + 1); j < EU; j++)
            {
                if (Scores[i] < Scores[j])
                {
                    tempScore = Scores[i];
                    tempID = StudID[i];
                    
                    Scores[i] = Scores[j];
                    StudID[i] = StudID[j];
                    
                    Scores[j] = tempScore;
                    StudID[j] = tempID;
                }
            }
        }
        

        cout << "Student ID #" << "       " << "Test Scores" << endl;
        
        for (i = 0; i < EU; i++)
        {
            cout << setw(7) << StudID[i] << "               " << Scores[i] << fixed << setprecision(1) << endl;
            
        }
        

    }


//*********************************** END OF FUNCTION ********************************





//************************************ FUNCTION HEADER *******************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the scores and sorts them from lowest
//                ID number to highest ID number and prints the corresponding
//                grade for each ID
//
//          Returns: The original list given sorted from lowest
//                   grade to highest ID number
//
//*********************************** END OF FUNCTION HEADER *************************

void sortLowHigh( ifstream &input,  int StudID[], float Scores[], int &EU)
{
    int i;
    int j;
    int tempID;
    float tempScore;
    
    for(i = 0; i < EU; i++)
    {
        for (j=(i + 1); j < EU; j++)
        {
            if (StudID[i] > StudID[j])
            {
                tempScore = Scores[i];
                tempID = StudID[i];
                
                Scores[i] = Scores[j];
                StudID[i] = StudID[j];
                
                Scores[j] = tempScore;
                StudID[j] = tempID;
            }
        }
    }
    
    cout << "Student ID #" << "       " << "Test Scores" << endl;
    
    for (i = 0; i < EU; i++)
    {
        cout << setw(7) << StudID[i] << "               " << Scores[i] << fixed << setprecision(1) << endl;
        
    }
    
    
}


//*********************************** END OF FUNCTION *****************************








//************************************ FUNCTION HEADER ****************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the array of scores and determine
//                which of the values is the lowest
//
//          Returns: The lowest test score in the array of values
//
//*********************************** END OF FUNCTION HEADER **********************


float findLow( ifstream &input, int StudID[], float Scores[], int &EU)
{
    float min;
    min = Scores[0];
    
    int lowID;

    
    int h;
    
    for (h = 1 ; h < EU ; h++)
    {
        if( Scores[h] < min)
            {
                min = Scores[h];
                lowID = StudID[h];
            }
    }
    

    
    return min;


}


//*********************************** END OF FUNCTION ******************************




//************************************ FUNCTION HEADER *****************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the array of scores and ID's to determine
//                which of the values is the lowest ID number
//
//          Returns: The lowest ID number in the array of values
//
//*********************************** END OF FUNCTION HEADER ***********************

int findLowID( ifstream &input, int StudID[], float Scores[], int &EU)
{
    float min;
    min = Scores[0];
    
    int minID;
    
    
    int h;
    
    for (h = 1 ; h < EU ; h++)
    {
        if( Scores[h] < min)
        {
            min = Scores[h];
            minID = StudID[h];
        }
    }
    
    
    
    return minID;
    
    
}

//*********************************** END OF FUNCTION *******************************







//************************************ FUNCTION HEADER ******************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the array of scores and determine
//                which of the values is the lowest
//
//          Returns: The highest test score in the array of values
//
//*********************************** END OF FUNCTION HEADER *************************

float findHigh( ifstream &input, int StudID[], float Scores[], int &EU)
{
    float max;
    max = Scores[0];
    
    int maxID;
    
    
    int h;
    
    for (h = 1 ; h < EU ; h++)
    {
        if( Scores[h] > max)
            {
                max = Scores[h];
                maxID = StudID[h];
            }
    }
    
    
    
   
    return max;

}

//*********************************** END OF FUNCTION *********************************




//************************************ FUNCTION HEADER ********************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Sort through the array of scores and ID numbers to determine
//                which of the values is the highest ID
//
//          Returns: The highest ID number in the array of values
//
//*********************************** END OF FUNCTION HEADER **************************

int findHighID( ifstream &input, int StudID[], float Scores[], int &EU)
{
    float max;
    max = Scores[0];
    
    int maxID;
    
    
    int h;
    
    for (h = 1 ; h < EU ; h++)
    {
        if( Scores[h] > max)
        {
            max = Scores[h];
            maxID = StudID[h];
        }
    }
    
    
    
    
    return maxID;
    
}

//*********************************** END OF FUNCTION ********************************






//************************************ FUNCTION HEADER *******************************
//
//          Recieves: The array values from the readArray function
//
//          Task: Adds all the tests score and divides by the
//                number of total student tp calculate the average score
//
//          Returns: The average test score out of all the students
//
//*********************************** END OF FUNCTION HEADER *************************

float findAverage( ifstream &input, int StudID[], float Scores[], int &EU)
{
    float average;
    float total;
    total = Scores[0];
    
    
    int h;
    
    for (h = 1; h < EU ; h++)
        {
            total = total + Scores[h];
    
        }
    
    average = total / EU;
    
    cout << endl;
    cout << "The average test score for the group is " << average << endl;
    

    return average;
}

//*********************************** END OF FUNCTION ***********************************









//**************************************** FUNCTION FOOTER *******************************
void footer (ofstream &output)
{
    //Receives - The output file
    //Task - Prints the output salutation
    //Returns - Nothing
    cout << endl;
    cout << setw(35) << "-----------------------------------";
    cout << setw(35) << "|      END OF PROGRAM OUTPUT      |";
    cout << setw(35) << "-----------------------------------";
    return;
    
}
//************************************ END OF FUNCTION FOOTER ****************************
