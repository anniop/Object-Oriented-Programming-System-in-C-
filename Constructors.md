## 📘 What is a Constructor?
A **constructor** is a special function in a class that **automatically runs when an object is created**.
## 🧠 Key Points:
- Same name as the class
- No return type (not even void)
- Can be **overloaded**
- Used to **initialize** object data
## 🧱 Types of Constructors:
A constructor that takes **no parameters**.
```cpp
class Student {
public:
    Student() {
        cout << "Default Constructor called!" << endl;
    }
};
```
Usage:
```cpp
Student s1; // Automatically calls default constructor
```
## 🔸 B. Parameterized Constructor
A constructor that takes **arguments** to initialize values.
```cpp
class Student{
public:
	string name;
	int age;

	Student(string n, int a){
		name = n;
		age = a;
	}	
};
```
Usage:
```cpp
Student s1("Ganesh", 21);
```
## 🔸 C. Copy Constructor
A constructor that creates a new object by copying an **existing object**.
```cpp
class Student{
public:
	string name;

	Student(string n){
		name = n;
	}

	// Copy Constructor
	Student(const Student &s){
		name = s.name;
	}
};
```
Usage:
```cpp
Student s1("Varu");
Student s2 = s1; // Copy Constructor called
```
## 🔍 When is Copy Constructor Called?
- When passing object by value
- When returning an object from a function
- When initializing one object with another
## 🧠 Important Notes:
|Concept|Default|Parameterized|Copy|
|---|---|---|---|
|Called automatically?|✅ Yes|❌ No|✅ If used like `obj2 = obj1`|
|Arguments allowed?|❌ No|✅ Yes|✅ One object as argument|
|Overloaded?|❌ Not needed|✅ Yes|✅ Custom version allowed|
## 📌 Special Cases:
- You can **overload** constructors by having different parameter lists.
- You **can’t have a constructor with a return type**.
- You can also define a **constructor outside the class** using `ClassName::ConstructorName()` syntax.
## 🧠 Real-Life Analogy
|Type of Constructor|Real-World Analogy|
|---|---|
|Default|Buying a phone with default settings|
|Parameterized|Choosing custom phone color & memory|
|Copy|Cloning the phone with same settings|
## ✅ Interview Tip:
Common questions include:
- What is a copy constructor?
- Can we overload constructors?
- What’s the difference between default and parameterized constructor?
- What is a deep copy vs shallow copy?
## ❓ Difference Between Constructor and Method

| Feature     | Constructor                      | Method                    |
| ----------- | -------------------------------- | ------------------------- |
| Name        | Same as class                    | Any Name                  |
| Return type | None                             | Has return type           |
| Called      | Automatically on object creation | Manually called by object |
