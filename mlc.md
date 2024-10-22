### 1. Write a program in C++ for Function Overloading. ( Polymorphism)

```C++
#include<iostream.h>
#include<conio.h>
void add (int a, int b) {
    cout << "Sum of a = " << a << " & b = " << b << "is: " << a+b << endl;
}

void add (double a, double b) {
    cout << "Sum of a = " << a << " & b = " << b << "is: " << a+b << endl;
}

int main() {
    clrscr();
    add(5,10);
    add(1.6, 2.2);
    getch();
    return 0;
}
```

### 2. Write a program in C++ for Inline Functions and Default argument functions. 

```C++
#include<iostream.h>
#include<conio.h>

inline int multiply(int a, int b = 2) {
    return a * b;
}

int main() {
   clrscr();
    cout << "Multiply by 2: " << multiply(5) << endl;
    cout << "Multiply: " << multiply(5, 3) << endl;
    getch();
    return 0;
}
```

### 3. Write a program in C++ for call by reference and return by reference.
```C++
#include <iostream.h>
#include<conio.h>
void swap(int *x, int *y) {
	int swap;
	swap=*x;
	*x=*y;
	*y=swap;
}
int main() {
	clrscr();
	int x=500, y=100;
	swap(&x, &y);
	cout<<"Value of x is: "<<x<<endl;
	cout<<"Value of y is: "<<y<<endl;
	getch();
	return 0;
}
```
```C++
#include <iostream.h>
#include<conio.h>

int& returnValue(int& x)
{
 cout << "x = " << x << " The address of x is " << &x << endl;
 return x;
}
int main()
{
    clrscr();
 int a = 20;
 int& b = returnValue(a);
 // Print a and its address
 cout << "a = " << a
 << " The address of a is "
 << &a << endl;
 // Print b and its address
 cout << "b = " << b
 << " The address of b is "
 << &b << endl;
 // We can also change the value of 'a' by using the address returned by returnValue function
// Since the function returns an alias of x, which is itself an alias of a, we canupdate the value of a
 returnValue(a) = 13;
 // The above expression assigns the value to the returned alias as 3.
 cout << "a = " << a << " The address of a is " << &a << endl;
 getch();
 return 0;
} 
```

### 4. Write a program in C++ where you use different datatypes as data member’s rollno, name & percentage of student class. (Encapsulation).
```C++
#include<iostream.h> 
#include<conio.h>    

class Student {
    private:
        int rollno;          
        char name[50];       
        float percentage;    
    public:
        
        void inputDetails() {
            cout << "Enter Roll Number: ";
            cin >> rollno;
            cout << "Enter Name: ";
            cin >> name;
            cout << "Enter Percentage: ";
            cin >> percentage;
        }

        void displayDetails() {
            cout << "\nStudent Details: " << endl;
            cout << "Roll Number: " << rollno << endl;
            cout << "Name: " << name << endl;
            cout << "Percentage: " << percentage << "%" << endl;
        }
};

int main() {
    clrscr(); 
    Student s1;  
    s1.inputDetails();   
    s1.displayDetails(); 
    getch(); 
    return 0;
}
```

5. Write a program in C++ to use public, private, protected access specifiers. Of class employee member function getdata & putdata (Data Hiding)
```C++
#include<iostream.h>  
#include<conio.h>    

class Employee {
    private:
        int empID;             
        char name[50];         
        float salary;         

    protected:
        char department[30];   

    public:
        
        void getdata() {
            cout << "Enter Employee ID: ";
            cin >> empID;
            cout << "Enter Employee Name: ";
            cin >> name;
            cout << "Enter Employee Salary: ";
            cin >> salary;
            cout << "Enter Department: ";
            cin >> department;
        }

        
        void putdata() {
            cout << "\nEmployee Details: " << endl;
            cout << "Employee ID: " << empID << endl;
            cout << "Employee Name: " << name << endl;
            cout << "Employee Salary: " << salary << endl;
            cout << "Department: " << department << endl;
        }
};

int main() {
    clrscr();  
    Employee e1;  
    e1.getdata(); 
    e1.putdata(); 
    getch();
    return 0;
}
```
### 6. Write a program in C++ to demonstrate an array of objects of three faculty use faculty as a class and eid, ename & salary as a data member. 
```C++
#include<iostream.h>
#include<conio.h>

class faculty {
    int eid;          
    char ename[50];   
    float salary;    

    public:
    void getdata() {
        cout << "Enter Employee ID: ";
        cin >> eid;
        cout << "Enter Employee Name: ";
        cin >> ename;
        cout << "Enter Employee Salary: ";
        cin >> salary;
    }

    void showdata() const {
        cout << "\nEmployee ID: " << eid;
        cout << "\nEmployee Name: " << ename;
        cout << "\nEmployee Salary: " << salary << endl;
    }
};

int main() {
    clrscr();

    faculty f[3];  
    int i;
    for (i = 0; i < 3; i++) {
        cout << "\nEnter details for Faculty " << i + 1 << ":" << endl;
        f[i].getdata();
    }

    cout << "\nDisplaying Faculty Information:" << endl;
    for (i = 0; i < 3; i++) {
        cout << "\nFaculty " << i + 1 << " Information:";
        f[i].showdata();
    }

    getch();
    return 0;
}
```

### 7. Write a program in C++ to design two different classes - student and College, make college class as a friend of student and access private data of class
```C++
#include<iostream.h>
#include<conio.h>

class College;  

class Student {
    private:
        int rollno;
        char name[50];
        float percentage;

    public:
        void getData() {
            cout << "Enter Student ID: ";
            cin >> rollno;
            cout << "Enter Student Name: ";
            cin >> name;
            cout << "Enter Percentage: ";
            cin >> percentage;
        }

        friend class College;  
};

class College {
    public:
        
        void display(Student &s) {
            cout << "\nStudent Details:" << endl;
            cout << "Student ID: " << s.rollno << endl;
            cout << "Name: " << s.name << endl;
            cout << "Percentage: " << s.percentage << endl;
        }
};

int main() {
    clrscr();

    Student student1;  
    College college;    

    student1.getData(); 
    college.display(student1); 

    getch();
    return 0;
}
```

### 8. Write a program in C++ for static data members. 
```C++
#include <iostream.h>
#include<conio.h>
class item
{
	static int count;
	int number;
public:
	void getdata (int a)
	{
		number=a;
		count++;
	}
	void getcount (void)
	{
		cout << "count";
		cout << count << "\n";
	}
};
int item::count;
int main()
{
	clrscr();
	item a, b, c;
	a.getcount();
	b.getcount();
	c.getcount();

	a.getdata(100);
	b.getdata (200);
	c.getdata (300);
	cout << "After reading data" << "\n";

	a.getcount();
	b.getcount();
	c.getcount();
	getch();
	return 0;
}
```

### 9. Write a program in C++ for static member function
```C++
#include <iostream.h>
#include<conio.h>

class test
{
	int code;
	static int count;
public:
	void setcode(void)
	{
		code=++count;
	}
	void showcode(void)
	{
		cout<<"object number: "<<code<<"\n";
	}
	static void showcount(void)
	{
		cout<<"count: "<<count<<"\n";
	}
};
int test::count;
int main()
{
    clrscr();
	test t1,t2;
	t1.setcode();
	t2.setcode();

	test::showcount();

	test t3;
	t3.setcode();

	test::showcount();

	t1.showcode();
	t2.showcode();
	t3.showcode();

	return 0;
}
```

### 10. Write a program in C++ to design a class to overload +,-,* operator. (Polymorphism)
```C++
#include<iostream.h>
#include<conio.h>
class complex {
	float r;
	float i;
public:
	complex() {}
	complex(float real, float imag) {
		r = real;
		i = imag;
	}
	complex operator+(const complex& c) {
		complex temp;
		temp.r = r+c.r;
		temp.i = i+c.i;
		return temp;
	}
	complex operator-(const complex& c) {
		complex temp;
		temp.r = r-c.r;
		temp.i = i-c.i;
		return temp;
	}
	complex operator*(const complex& c) {
		complex temp;
		temp.r = (r*c.r) - (i*c.i);
		temp.i = (r*c.i) - (i*c.r);
		return temp;
	}

	void display() const {
		cout << r << " + " << i << "i" << endl;
	}

};

int main() {
	clrscr();
	complex C1, C2, C3, C4, C5;
	C1 = complex(9, 7);
	C2 = complex(1, 6);
	C3 = C1+C2;
	C4 = C1-C2;
	C5 = C1*C2;
	cout << "C1 = ";
	C1.display();
	cout << "C2 = ";
	C2.display();
	cout << "C1 + C2 = ";
	C3.display();
	cout << "C1 - C2 = ";
	C4.display();
	cout << "C1 * C2 = ";
	C5.display();

	getch();
	return 0;
}
```

### 11. Write a program to design a class in C++ for single level Inheritance. Class student is a base class having all the basic attributes and functionality. Derive new class GeneralSecreatary, add some more attributes and operations to the class (Inheritance).
```C++
#include<iostream.h>
#include<conio.h>
class student{
    int rollno;
    public:
    int per;
    char name[20];
    void getdata();
    void showdata();
};
class gsec:public student{
  int gsroll;
  int gsper;
  public:
  void gsgetdata();
  void gsshowdata();
};
void student::getdata() {
    cout << "Enter Student Name, Roll no, Percentage: ";
    cin >> name;
    cin >> rollno;
    cin >> per;
}
void student :: showdata() {
    cout << "Student Information: " << endl;
    cout << "Student Roll No.: " << rollno << endl;
    cout << "Student Name: " << name << endl;
    cout << "Student Percentage: " <<  per << endl;
}
void gsec :: gsgetdata() {
  cout << "Enter General Secretary Roll no.: ";
    cin >> gsroll;
    cout << "Enter General Secretary Percentage: ";
    cin >> gsper;
}
void gsec :: gsshowdata() {
    cout << "General Secretary Information" << endl;
    cout << "General Secretary Roll No.: " << gsroll << endl;
    cout << "General Secretary Percentage: " << gsper <<endl;
}

int main() {
    clrscr();
    gsec g1;
    g1.getdata();
    g1.showdata();
    cout << endl;
    g1.gsgetdata();
    g1.gsshowdata();
    getch();
    return 0;
}
```

### 12. Write a program in C++ for Multi-Level Inheritance
```C++
#include<iostream.h>
#include<conio.h>

class student {
    int rollno;
    public:
    int per;
    char name[20];
    void getdata() {
        cout << "Enter name of student: ";
        cin >> name;
        cout << "Enter Roll No: ";
        cin >> rollno;
        cout << "Enter Percentage: ";
        cin >> per;
    }
    void showdata() {
        cout << "Student Information: " << endl;
        cout << "Roll No.: " << rollno << endl;
        cout << "Name: " << name << endl;
        cout << "Percentage: " << per << endl;
    }
};

class leader : public student {
    public:
    char position[20];
    void getLeaderData() {
        cout << "Enter leadership position: ";
        cin >> position;
    }
    void showLeaderData() {
        cout << "Leadership Position: " << position << endl;
    }
};

class gsec : public leader {
    int gsrollno;
    int gsper;
    public:
    void gsgetdata() {
        cout << "Enter General Secretary Roll No.: ";
        cin >> gsrollno;
        cout << "Enter General Secretary Percentage: ";
        cin >> gsper;
    }
    void gsshowdata() {
        cout << "General Secretary Information" << endl;
        cout << "General Secretary Roll No.: " << gsrollno << endl;
        cout << "General Secretary Percentage: " << gsper << endl;
    }
};

int main() {
    clrscr();
    
    gsec g;
    g.getdata();
    g.showdata();
    cout << endl;
    g.getLeaderData();
    g.showLeaderData();
    cout << endl;
    g.gsgetdata();
    g.gsshowdata();
    cout << endl;
    getch();
    return 0;
}
```

### 13. Write a program in C++ for Multiple Inheritance.
```C++
#include<iostream.h>
#include<conio.h>

class student {
    int rollno;
    public:
    int per;
    char name[20];
    void getdata() {
        cout << "Enter name of student: ";
        cin >> name;
        cout << "Enter Roll No: ";
        cin >> rollno;
        cout << "Enter Percentage: ";
        cin >> per;
    }
    void showdata() {
        cout << "Student Information: " << endl;
        cout << "Roll No.: " << rollno << endl;
        cout << "Name: " << name << endl;
        cout << "Percentage: " << per << endl;
    }
};

class position {
    public:
    char position[30];
    char council[30];
    void getPosition() {
        cout << "Council Name: ";
        cin >> council;
        cout << "Enter the position: ";
        cin >> position;
    }
    void showPosition() {
        cout << "Council: " << council << endl;
        cout << "Activity: " << position << endl;
    }
};

class gsec : public student, public position {
    int gsrollno;
    int gsper;
    public:
    void gsgetdata() {
        cout << "Enter General Secretary Roll No.: ";
        cin >> gsrollno;
        cout << "Enter General Secretary Percentage: ";
        cin >> gsper;
    }
    void display() {
        cout << "General Secretary Information" << endl;
        cout << "General Secretary Roll No.: " << gsrollno << endl;
        cout << "General Secretary Percentage: " << gsper << endl;
    }
};

int main() {
    clrscr();
    
    gsec g;
    g.getdata();
    g.gsgetdata();
    g.getPosition();
    cout << endl;
    g.showdata();
    g.showPosition();
    g.display();

    getch();
    return 0;
}
```

### 15. Write a program in C++ for Parameterised Constructor.
```C++
#include<iostream.h>
#include<conio.h>
class Point{
  int x, y;
  public:
  Point(int a, int b) {
    x = a; y = b;
  }
  void display() {
      cout << x << ", " << y << endl;
  }
};
int main() {
    clrscr();
    Point P1 (3,4);
    Point P2 (6,7);
    cout << "P1 = ";
    P1.display();
    cout << "P2 = ";
    P2.display();
    getch();
    return 0;
}
```

### 16. Write a program in C++ for Copy Constructor
```C++
#include<iostream.h>
#include<conio.h>
class Point{
    int a;
    public:
    Point() {}
    Point (int x) {
        a = x;
    }
    Point(Point& c) {
        a = c.a;
    }
    void display() {
        cout << a << endl;
    }
};
int main() {
    clrscr();
    
    Point A (100);
    Point B(A);
    Point C = A;
    Point D;
    D=A;
    
    cout << "ID of A: ";
    A.display();
    cout << "ID of B: ";
    B.display();
    cout << "ID of C: ";
    C.display();
    cout << "ID of D: ";
    D.display();
    
    getch();
    return 0;
}
```

### 17. Write a program in C++ for Destructor.
```C++
#include<iostream.h>
#include<conio.h>
int count = 0;
class test{
    public:
    test() {
        count++;
        cout << "\n\nConstructor Msg: Object No. " << count << " Created" << endl;
    }
    ~test() {
        cout << "\n\nConstructor Msg: Object No. " << count << " Destroyed" << endl;
        count--;
    }
};

int main() {
    clrscr();
    
    cout << "Inside the Main Block..." << endl;
    cout << "Creating First Object...";
    test T1;
    {
        cout << "Inside the Block 1..." << endl;
        cout << "Creating Two More Blocks...";
        test T2, T3;
        cout << "Leaving Block 1..." << endl;
    }
    cout << "Leaving Main Block..." << endl;
    getch();
    return 0;
}
```
