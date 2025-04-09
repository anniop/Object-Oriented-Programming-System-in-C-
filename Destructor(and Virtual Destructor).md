### 📘 What is a Destructor?
A **destructor** is a special member function that:
- Has the **same name as the class**, preceded by a **tilde (~)**
- Has **no return type**, not even `void`
- Is **automatically called** when an object **goes out of scope**
- Is used to **release resources** (memory, files, etc.)

---

### 🧪 Basic Example:

```cpp
class A { 
public:     
	~A() {        
		 cout << "Destructor of A called" << endl;     
	 }
};
```

```cpp
int main() {     
	A obj;  // Destructor will be called automatically at the end 
}
```

---

## ⚠️ Problem in Inheritance Without Virtual Destructor

```cpp
class Base { 
public:    
	~Base() {        
		 cout << "Base destructor\n";     
		 }
 };  
 
 class Derived : public Base { 
 public:    
	  ~Derived() {      
	     cout << "Derived destructor\n";   
	       } 
};  

int main() {    
	Base* b = new Derived();     
	delete b;  // ❌ Only Base destructor is called!
}
```

**Why is this dangerous?**  
➡️ If `Derived` allocates memory in its constructor, it **won’t get freed**, causing **memory leaks**.

---

## ✅ Solution: Use Virtual Destructors

```cpp
class Base {
public:
    virtual ~Base() {
        cout << "Base destructor\n";
    }
};

class Derived : public Base {
public:
    ~Derived() {
        cout << "Derived destructor\n";
    }
};
```

Now `delete b` will correctly call:

1. `Derived` destructor
2. `Base` destructor
---

## 🔁 Summary Table

|Feature|Destructor|Virtual Destructor|
|---|---|---|
|Purpose|Cleanup|Cleanup (especially in inheritance)|
|Inheritance-safe?|❌ No|✅ Yes|
|Can be overloaded?|❌ No|❌ No|
|Automatically called?|✅ Yes|✅ Yes|
|Can destructors be pure virtual?|✅ Yes (but must define)||

---

### 🧠 Real-Life Analogy

Think of destructors as **cleanup staff** when an object leaves a room.

- If `Base* b = new Derived()`, without a virtual destructor, the **base class cleanup crew** will be called — but the **derived class mess stays behind** 🧹❌

---

### ✅ Interview Tips:

**Q:** Should base class destructor always be virtual?  
✅ Yes — if you’re using inheritance and dynamic allocation.

**Q:** Can a destructor be virtual and pure virtual?  
✅ Yes — but still must define it in base class.

---

### 💡 Example of Pure Virtual Destructor:

```cpp
class Base {
public:    
	virtual ~Base() = 0;  // Pure virtual 
}; 

Base::~Base() {     
	 cout << "Pure Virtual Destructor Called" << endl; 
}
```