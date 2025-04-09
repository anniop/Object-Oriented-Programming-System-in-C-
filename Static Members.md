## 📘 What is a Static Member?
A **static member** (variable or function) belongs to the **class itself**, not to any object.
It is **shared among all objects** of the class.
## 🔸 Types:
- `static` **data members** (variables)
- `static` **member functions`
## ✅ Static Data Member
### 🧠 Meaning:
- Only **one copy** of the variable exists for the whole class.
- All objects **share** the same variable.
- Must be **defined outside the class** (even if declared inside).
## 🧪 Example:
```cpp
class Student{
public:
	static int count;

	Student(){
		count++;
	}
};
int Student::count = 0; //Defination of static member

int main(){
	Student s1, s2, s3;
	cout<< Student::count; // Output: 3
	return 0;
}
```
### 🔸 Key Points:
- Shared by all objects
- Can be accessed using: `ClassName::variable`
- Lifetime: Program lifetime (exists even without any object)
## ✅ Static Member Functions
### 🧠 Meaning:
- Can be called **without creating an object**.
- Can only access **static members**.
## 🧪 Example:
```cpp
class Student{
public:
	static int count;

	static void showCount(){
		cout<<"Total Students: "<<count<<endl;
	}
};

int Student::count = 0;

int main(){
	Student s1, s2;
	Student::showCount(); // Output: Total Students: 2
	return 0;
}
```
## 🔁 Static vs Non-Static Members
|Feature|Static Member|Non-Static Member|
|---|---|---|
|Belongs to|Class|Object|
|Memory allocated|Once (shared)|For each object|
|Access|ClassName:: or via object|Only via object|
|Can use `this`|❌ No|✅ Yes|
## ✅ Interview Tip:
Common questions:
- What is a static variable in C++?
- Can static functions access non-static members?(❌ No)
- Where is static data member defined? (Outside the class)
## 🧠 Real-Life Analogy:
Think of:
- **Static member**: School name(same for all students)
- **Non-static member**: Student Name(unique for each)