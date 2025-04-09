### 📘 Overview:

The 4 main pillars (or principles) of OOP are:

|Pillar|One-Liner|
|---|---|
|**Abstraction**|Hiding unnecessary implementation details|
|**Encapsulation**|Bundling data and functions together|
|**Inheritance**|Acquiring properties from another class|
|**Polymorphism**|One name, many forms (function behavior changes based on context)|

---

## 🔸 A. Abstraction

### 🧠 Definition:

Abstraction means **hiding complex implementation details** and **showing only the essential features**.

> 🔧 *"What it does" without worrying about _"how it does it."_

---

### 🧪 Example:

```cpp
class Car{
public:
	void startEngine(){
		// You don't need to know how it starts, just use it
		cout<<"Engine Started!"<<endl;
	}
};
```

As a user, you just call `startEngine()` — you don’t care **how** it works internally.

---

### ✅ Interview Tip:

> Be ready to explain **real-life examples** like ATM, car interface, or mobile apps.

---

## 🔸 B. Encapsulation

### 🧠 Definition:

Encapsulation means **binding data and methods that operate on that data into a single unit (class)** and **restricting direct access** using **access specifiers**.

---

### 🧪 Example:

```cpp
class Account{
private:
	int balance;
public:
	void deposit(int amount){
		balance += amount;
	}
	int getBalance(){
		return balance;
	}
};
```
Here, `balance` is protected from outside access. It can be changed only via `deposit()` or `getBalance()` methods.

---

### 🔐 Access Specifiers:

|Keyword|Scope Description|
|---|---|
|`private`|Accessible only within the same class|
|`public`|Accessible from anywhere|
|`protected`|Accessible in the same class & derived classes|

---

### ✅ Interview Tip:

> If asked “How is encapsulation achieved in C++?”, say:  
> “Using classes + access specifiers (`private`, `public`, etc.)”

---

## 🔸 C. Inheritance

### 🧠 Definition:

Inheritance allows a class (child/derived) to **reuse and extend** the properties and behaviors of another class (parent/base).

---

### 🧪 Example:
```cpp
class Animal{
public:
	void speak(){
		cout<< "Animal Speaks"<<endl;
	}
};
class Dog : public Animal{
public:
	// Inherits speak()
	void speak(){
		cout<<"Dog barks"<<endl;
	}
};
```

`Dog` can call `speak()` from `Animal`.

---

### 📂 Types of Inheritance:

|Type|Structure|
|---|---|
|Single|One parent → one child|
|Multilevel|Grandparent → Parent → Child|
|Multiple|One child inherits from multiple parents|
|Hierarchical|One parent → multiple children|
|Hybrid|Combination of above types|

---

### ✅ Interview Tip:

> They may ask: “What is the difference between multilevel and multiple inheritance?”  
> Know the examples of each with diagrams.

---

## 🔸 D. Polymorphism

### 🧠 Definition:

Polymorphism means **“many forms”** — same function name behaves differently depending on the context.

---

### 📑 Types:

|Type|Example|
|---|---|
|Compile-Time|Function Overloading / Operator Overloading|
|Run-Time|Function Overriding with Virtual Functions|

---

### 🔁 Function Overloading (Compile-Time):
```cpp
class Print{
public:
	void show(int x) {cout<<"Int: "<<x<<endl; }
	void show(string s) { cout<<"String : "}<<s<<endl;}
};
```

Same function name `show()` works with both `int` and `string`.

---

### 🎭 Function Overriding (Run-Time):
```cpp
class Animal{
public:
	virtual void speak(){
		cout << "Animal speaks"<<endl;
	}
};
class Dog : public Animal{
public:
	void speak() override{
		cout<<"Dog barks"<<endl;
	}
};
```

If you call `speak()` through a `Animal*` pointer pointing to `Dog`, it will call `Dog`'s version.

---

### ✅ Interview Tip:

> Explain:  
 “Polymorphism allows code reusability and flexibility — especially with base class pointers referring to derived objects.”

---

## ✅ Summary Table

|Pillar|Core Idea|
|---|---|
|Abstraction|Hides internal details|
|Encapsulation|Protects data inside class|
|Inheritance|Reuse code from base class|
|Polymorphism|Same name, different behavior|