# lab-5
lab 5

/*
Name: <Zech Gluckle>
Date: <2/21/2018>
Assignment: <Lab 5>
Description: <Lab 5>
*me: <fill me in>
Date: <fill me in>
Assignment: <fill me in>
Description: <fill me in>
*/


#include <iostream>
#include <string>
#include <iomanip>
#include <sstream>
#include <vector>
#include <cmath>
#include <cstdlib>
#include <ctime>

using namespace std;


bool find(int array[], int length, int value){
  int i;
  for (i = 0, i < length, i++) {
    if (array[i] == value) {
    return true;
    else {
    return false
         }
      }
   }
}

bool isSorted(int array[], int length){
  // TODO: Fill me in
}

void reverse(vector <int> &reverse_me) {
  // TODO: Fill me in
}

float mean(const vector <float> values) {
  // TODO: Fill me in
}

float stddev(const vector <float> values) {
  // TODO: Fill me in
  // Should use mean above
}

vector<int> removeDups(vector<int> array){
  // TODO: Fill me in

  // This is just to keep the compiler happy
  return vector<int>();
}

// Strings 
unsigned int countUpperCaseChars(const string &countme){
  // TODO: Fill me in
}

unsigned int numWords(const string &countme){
  // TODO: Fill me in
}

string convertToUpper(const string &to_be_converted){
  // TODO: Fill me in
}

string removeSpaces(const string &remove_from_me){
  // TODO: Fill me in
}

vector <int> characterCounts(const string &countme){
  // TODO: Fill me in
}

template<typename T>
string print(vector<T> vec);

template<typename T>
string print(T array[], int length);


int main(){
  srand(time(0));   

  cout << "find:" << endl;
  int x1[10] = {1,2,3,5,5,6,7,8,9,0};
 
  cout << "false/0 = " << find(x1, 10, 4) << endl;
  cout << "false/0 = " << find(x1, 10, 99) << endl;
  cout << "true/1 = " << find(x1, 10, 5) << endl;
  cout << "true/1 = " << find(x1, 10, 0) << endl;
  cout << "true/1 = " << find(x1, 10, 1) << endl;
  cout << "true/1 = " << find(x1, 10, 6) << endl;
  cout << endl;
  cout << endl;
  cout << "reverse:" << endl;
  vector <int> v1 = {1,2,3,4,5};
  reverse(v1);
  cout << "[5,4,3,2,1] = " << print(v1) << endl;
  reverse(v1);
  cout << "[1,2,3,4,5] = " << print(v1) << endl;
  vector <int> v2 = {5};
  cout << "[5] = " << print(v2) << endl;
  vector <int> v3 = {1,2,4,5};
  reverse(v3);
  cout << "[5,4,2,1] = " << print(v3) << endl;
  vector <int> v4(100);
  v4[0]  = 4;
  v4[1]  = 2;
  reverse(v4);
  cout << "0 = " << v4[0] << endl;
  cout << "2 = " << v4[98] << endl;
  cout << "4 = " << v4[99] << endl;
  
  cout << endl << "mean:" << endl;
  vector <float> f1 = {1.2, 2.4, 3.4};
  vector <float> f2 = {5.6, 5.6, 5.6, 5.6, 5.6, 5.6};
  cout << "2.33 = " << mean(f1) << endl;
  cout << "5.6 = " << mean(f2) << endl;
  
  cout << endl << "stddev:" << endl;
  cout << "0.899 = " << stddev(f1) << endl;
  cout << "0 = " << stddev(f2) << endl;
  
  cout << endl << "removedups:" << endl;
  vector<int> v5;
  v5.push_back(1);
  v5.push_back(2);
  v5.push_back(3);
  v5.push_back(3);
  v5.push_back(4);
  v5.push_back(5);
  v5.push_back(1);
  vector<int> v12 = removeDups(v5);
  cout << "[1,2,3,4,5] = " << print(v12) << endl;
  cout << "5 = " << v12.size() << endl;
  vector<int> v6;
  for(int i = 0; i < 100; i++){
    v6.push_back(i%17 + i %7);
  }
  vector<int> v22 = removeDups(v6);
  cout << "22 = " << v22.size() << endl;

  cout << "\nString Functions: " << endl;
  string upper_test = "aaABCdeFG"; 
  cout << "countUpperCase" << endl;
  cout << "5 = " << countUpperCaseChars(upper_test) << endl;
  cout << "5 = " << countUpperCaseChars("AAAAA") << endl;
  cout << "0 = " << countUpperCaseChars("aaaaa") << endl;
  string no_upper_case = "aaaa";
  cout << "0 = " << countUpperCaseChars(no_upper_case) << endl;

  cout << "RemoveSpaces:" << endl;
  string test1 = "aa AB Cd e FG"; 
  string test2 = "aaAB Cd e FG "; 
  string test3 = " rrAB Cd e FG"; 
  string test4 = " rrAB Cd e FG "; 
 
  cout << "aaABCdeFG = " << removeSpaces(test1) << endl;
  cout << "aaABCdeFG = " << removeSpaces(test2) << endl;
  cout << "rrABCdeFG = " << removeSpaces(test3) << endl;
  cout << "rrABCdeFG = " << removeSpaces(test4) << endl;

  return 0;
}

// A sneaky way to allow 1 function to print any typed array, as long as
// the passed array element can be sent to <<.
// The stringstream allows us to 'print' information to a fake output
// stream, and then get the result as a string.  It's a simple way of
// getting a non-string/character into a string.
// Contense of this function will not be tested in this course!

template<typename T>
string print(vector<T> vect) {
  stringstream out;
  out << '[';
  for(int i = 0; i < vect.size(); i++){
    out << vect[i];
    if(i != vect.size()-1)out << ',';
  }
  out << ']';
  return out.str();
}


template<typename T>
string print(T array[], int length){
  stringstream out;
  out << '[';
  for(int i = 0; i < length; i++){
    out << array[i];
    if(i != length-1)out << ',';
  }
  out << ']';
  return out.str();
}

