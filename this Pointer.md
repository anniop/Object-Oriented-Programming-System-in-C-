### 📘 What is the `this` Pointer?

The `this` pointer is an **implicit pointer** available inside **non-static member functions** of a class.

> It points to the **current object** that is calling the function.

---

### 🧠 Why is it useful?

- To **differentiate between class variables and parameters** when they have the same name
- To **return the object** from a function
- To **chain function calls**

---

### 🧪 Basic Example:
```cpp
class Student { 
private:    
	int id; 
public:     
	void setId(int id) {
	    this->id = id; // 'this->id' refers to the class variable, 'id' refers to the parameter     
	    }     
	void print() {        
		cout << "ID is: " << this->id << endl;    
	} 
};
```

---

### 📌 When is `this` needed?

If local variable and class member have **same names**, `this->` clarifies you're referring to the class member.

---

### 🔁 Use Case: Return the object using `this`
```cpp
class Person {
public:
    int age;

    Person& setAge(int age) {
        this->age = age;
        return *this; // return current object
    }
};
```
👉 This enables **method chaining**:

```cpp
Person p; 
p.setAge(21).setAge(22);  // Chained calls
```

---

## ❌ Not Allowed with Static

> Static functions do **not have a `this` pointer**  
> Because static functions **don’t belong to an object** — they belong to the class.

---

## ✅ Summary Table

|Feature|Value|
|---|---|
|What is it?|Pointer to current object|
|Belongs to?|Non-static functions only|
|Purpose|Access class members, disambiguation|
|Syntax|`this->member`|

---

### ✅ Interview Tip:

> Common question:  
> **"Why do we use `this` pointer in constructors?"**  
> Answer: _To differentiate between data members and constructor parameters having the same name._