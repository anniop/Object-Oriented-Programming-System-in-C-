## 📘 What is a Class?
A **class** is a **user-defined data type** that groups together **data(variables)** and **functions(methods)** in one unit.
It acts like a **blueprint** for creating objects.

## 🔨 Syntax:
```cpp
class ClassName{
//Access Specifier
// Data Members
// Member Functions
};
```
## 🧪 Example:
```cpp
class Student{
public:
	string name;
	int age;

	void introduce(){
		cout<<"Hi, I'm "<<name<<" and I'm" << age << " years old."<<endl;
	}
};
```
## 👤 What is an Object?
An **object** is an **instance** of a class — it holds actual values and can use the functions defined in the class.
## 🧪 Object Creation:
```cpp
int main() {
    Student s1;           // Creating object of Student class
    s1.name = "Rahul";    // Setting values
    s1.age = 21;
    s1.introduce();       // Calling function
    return 0;
}
```
## 💡 Memory:
- Memory is allocated to a class only when an **object is created**.
- Each object has its **own copy** of data members.
## 📌 Key Points:
|   Term    |      Description      |
| :-------: | :-------------------: |
|   Class   | Blueprint or template |
|  Object   | Instance of the class |
|  Method   | Function inside class |
| Attribute | Variable inside class |
## 🧠 Real-Life Analogy
| Concept          | Real World                                    |
| ---------------- | --------------------------------------------- |
| Class            | Blueprint of a car                            |
| Object           | Actual car (Car1, Car2) built using blueprint |
| Data Members     | Properties like color, brand                  |
| Member Functions | Actions like drive(), brake()                 |
## ✅ Interview Tip:
Be prepared to explain with code:  
**“What is a class?”, “What is an object?”, and “When is memory allocated?”**  
Also:  
“What is the difference between Class and Object?”
## ❓Common Interview Question:
**Q:** What is the difference between a class and an object?

| Class                | Object              |
| -------------------- | ------------------- |
| Blueprint            | Real Instance       |
| No memory allocation | Allocated Memory    |
| Declared once        | Can create multiple |
