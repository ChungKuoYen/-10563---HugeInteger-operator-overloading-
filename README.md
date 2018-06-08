# -10563---HugeInteger-operator-overloading-

https://acm.cs.nthu.edu.tw/problem/10563/

Description
In your last homework, you have created a class HugeInteger that uses a 40-element array of digits to store integers as large as 40 digits each:  
 
class HugeInteger 
{
    public:                                                   
        HugeInteger();
        HugeInteger( const std::string &);
        // addition operator; HugeInteger + HugeInteger
        HugeInteger add( const HugeInteger & ) const;
        // HugeInteger + string that represents large integer value
        HugeInteger add( const std::string & ) const;
        // subtraction operator; HugeInteger - HugeInteger
        HugeInteger subtract( const HugeInteger &  ) const;
        // HugeInteger - string that represents large integer value
        HugeInteger subtract( const std::string & ) const;
 
        bool isGreaterThan( const HugeInteger &  ) const;
        void output() const;
    private:
        int integer[42];
        int noOfDigits;
};  

 
In this homework, you are asked to modify this class definition by:
l  removing the member functions add, subtract, isGreaterThan and output;
l overloading the addition operator (+), subtraction operator (-), relational operator (>) and stream insertion operator (<<);
l   additionally, overloading the multiplication operator (*) to support HugeInteger*HugeInteger and HugeInteger*string ;
l  additionally, overloading the division operator (/) to support HugeInteger/HugeInteger and HugeInteger/string ;
 
Note:
1.      This problem involves three files.
l   function.h: Class definition of HugeInteger.
l   function.cpp: Member-function definitions of HugeInteger.
l   main.cpp: A driver program to test your class implementation.
You will be provided with main.cpp, and asked to implement function.h and function.cpp.
 
function.h 

#ifndef HUGEINTEGER_H

#define HUGEINTEGER_H

#include <iostream>

#include <string>

class HugeInteger

{

public:

   HugeInteger();

 

   HugeInteger( const std::string &);

 

   /* addition operator overloading for “HugeInteger + HugeInteger”*/

   /* addition operator overloading for “HugeInteger + string that represents a large integer value”*/

   /* subtraction operator overloading for “HugeInteger – HugeInteger”*/

   /* subtraction operator overloading for “HugeInteger - string that represents a large integer value”*/

   /* multiplication operator overloading for “HugeInteger * HugeInteger”*/

   /* multiplication operator overloading for “HugeInteger * string that represents a large integer value”*/

   /* division operator overloading for “HugeInteger / HugeInteger”*/

   /* division operator overloading for “HugeInteger / string that represents a large integer value”*/

   /* relational operator overloading for “HugeInteger > HugeInteger”*/

   /* stream insertion operator “<<” overloading*/

private:

   int integer[42];

   int noOfDigits;

};
#endif
 
 
 
main.cpp

#include <iostream>

#include "function.h"

using namespace std;

 

int main() {

    char c[2], a[42], b[42];

    HugeInteger result,resultWithString;

 

    while (  cin>>c>>a>>b ) {

        HugeInteger n1(a);

        HugeInteger n2(b);

        if(c[0] == '+') {

            result = n1+n2;

            resultWithString = n1+b;

            cout<<result<<endl<<resultWithString<<endl;

        } else if(c[0] == '-') {

            result = n1-n2;

            resultWithString = n1-b;

            cout<<result<<endl<<resultWithString<<endl;

        }else if(c[0] == '*') {

            result = n1*n2;

            resultWithString = n1*b;

            cout<<result<<endl<<resultWithString<<endl;

        }else if(c[0] == '/') {

            result = n1/n2;

            resultWithString = n1/b;

            cout<<result<<endl<<resultWithString<<endl;

        } else if (c[0] == '>') {

            cout<< (n1>n2) <<endl;

        } else {

            cout<<"ERROR";

            return 0;

        }

    }

    return 0;
} // end main
 
2     For OJ submission:
       Step 1. Submit only your function.cpp into the submission block. (***Note that you don’t need to submit your function.h.)

 
       Step 2. Check the results and debug your program if necessary.
Input

There are three strings in each line: S1 S2 S3

S1 represents an operator (+, -, *, /, >).

S2 and S3 represent the two positive huge-number operands.

For subtract operation, S2 is always no less than S3.

Input terminated by EOF.

 
Output

For every given operation, your program should print the corresponding result followed by a new line character.
