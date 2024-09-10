# EXPERIMENT 12
# Aim 
To study and implement Constructors and Destructors
# Software 
Visula Studio Code
# Theory
In C++, constructors and destructors are special member functions that handle object initialization and cleanup. They are essential for object-oriented programming in C++.

Constructors are special member functions that are called automatically when a class object is created. It is used to set up the object's data members. Constructors share the same name as the class and have no return type.

Types of Constructors:

Default Constructor: A constructor without any parameters. It sets up the object with default values.

Parameterized constructor: A  constructor that accepts parameters and initializes the object with specific values specified at the time of creation.

Copy Constructor: A constructor that creates an object from another object of the same class. It is useful when we require a duplicate object with identical values.


Destructors:

A destructor is a special member function that is called automatically when an object exits scope or is explicitly deleted. Its purpose is to free up resources, such as memory, that the object may have accumulated during its lifetime. Destructors have the same name as the class, prefixed with a tilde (~), and do not accept parameters or return a value.

CODES:

1. Defining constructor inside the class
```
#include<iostream>
using namespace std;
class employee
{
 int phone_no;
 char name[50];
 double salary;
 public:
 employee()
 {
 cout<<"Enter the phone no.:"<<endl;;
 cin>> phone_no;
 cout<<"Enter the Name:"<<endl;
 cin>>name;
 cout<<"Enter the salary:"<<endl; 
 cin>>salary; 
 } 
 
void display()
{
 cout<<endl<<phone_no <<"\t"<<name<<"\t"<<salary;
 }
};
int main()
{
 employee e; 
 e.display();
 return 0;
}
```
O/P:![image](https://github.com/user-attachments/assets/5825117e-6362-41c5-a9ea-6b10a995aa42)


2. Defining constructor outside the class
```
#include<iostream>
using namespace std;
class employee
{
 int phone_no;
 char name[50];
 double salary;
 public:
 employee();
 void display(); };
employee::employee()
 {
 cout<<"Enter the phone no.:";
 cin>>phone_no;
 cout<<"Enter the Name:";
 cin>>name;
 cout<<"Enter the salary:"; 
 cin>>salary;
 } 
 void employee::display()
 {
 cout<<endl<<phone_no<<"\t"<<name<<"\t"<<salary;
 }
int main()
{
 employee e;
 e.display();
 return 0;
}
```

O/P: ![image](https://github.com/user-attachments/assets/5117cb22-c748-4ea3-9c77-9f1416101055)



3. Default Constructor
```
#include<iostream>
#include<string>
using namespace std;
class Data{
string name;
int phone_no;
char dept[50];
int id;
public:
Data(){
cout<<"Name: ";
cin>>name;
cout<<"Phone Number: ";
cin>>phone_no;
cout<<"Department: ";
cin>>dept;
cout<<"ID: ";
cin>>id;
}
void display(){
cout<<endl<<"DETAILS:"<<endl<<name<<" "<<phone_no<<" "<<dept<<" "<<id<<endl;
}
};
int main(){
Data d1;
d1.display();
}
```
O/P: ![image](https://github.com/user-attachments/assets/2da062bf-c0b9-4269-92d3-9b226cdce1d0)




4. Parameterized Constructor
```
#include<iostream>
using namespace std;

class Num{

public:
Num(int a, int b){
if(a>b){
cout<<a<<" is greater";
}
else{
cout<<b<<" is greater";
}
}
};
int main(){
Num n1(22,13);
}
```
O/P: ![image](https://github.com/user-attachments/assets/bb179738-3836-4134-a93d-4d1517959902)



5. Copy Constructor 
```
#include <iostream> 
#include <string.h>
using namespace std;
class employee
{
 int phno;
 char name[50];
 double salary;
 public:
 employee(int,char[],double);
 employee(employee &t) {
 phno=t.phno;
 strcpy(name,t.name);
 salary=t.salary;
 }
 void display();
 
};
 employee::employee(int no,char n[],double s)
 {
 phno=no;
 strcpy(name,n);
salary=s;
 } 
 void employee::display()
 {
 cout<<endl<<phno<<"\t"<<name<<"\t"<<salary;
 }
 
int main()
{
 employee e(1001,"abc",10000);
 e.display();
 
 employee abc(e); 
 abc.display();
 
 return 0;
}
```
O/P:



6. Destructor
```
#include<iostream>
using namespace std;
int count=0;
class destruct{
public:
destruct()
{
count++;
cout<<"No. of objects created: "<<count<<endl;
}
~destruct()
{
count--;
cout<<"No. of objects destroyed: "<<count<<endl;
}
};
int main()
{
destruct aa,bb,cc;
{ destruct dd;
}
return 0;
}
```
O/P: ![image](https://github.com/user-attachments/assets/70997a47-0b1a-48c0-bd9a-f398de76fd27)



# Conclusion 
The provided codes demonstrate how to use various types of constructors and destructors in C++. The first two examples use default constructors defined both inside and outside the class to initialize member variables when an object is created. The third example shows a parameterized constructor that accepts arguments and performs specific operations. The copy constructor example demonstrates how to initialize a new object with the values of an existing object, which simplifies object copying. Finally, the destructor example demonstrates how destructors automatically handle source removal when objects leave scope. These ideas are essential for managing the lifecycle of objects in C++.
