### 📘 What is a Virtual Function?
A **virtual function** is a member function in the base class that you can **override in a derived class**.  
It allows the **function call to be resolved at runtime** (i.e., run-time polymorphism).

---

### 🧠 Why use Virtual Functions?
To make sure the **derived class version** of the function gets called **even when using a base class pointer**.

---
### 🔸 Syntax:
```cpp
class Base {
public:
    virtual void print() {
        cout << "Base Class" << endl;
    }
};

class Derived : public Base {
public:
    void print() override {
        cout << "Derived Class" << endl;
    }
};

```

```cpp
Base* b; 
Derived d; 
b = &d; b->print();  // Output: "Derived Class" (because print is virtual)
```

---

## 🔍 What Happens Internally?

Whenever a class has a virtual function, **C++ compiler creates a hidden table** called a **V-Table** (Virtual Table).

- V-Table = Table of pointers to virtual functions.
- Each class with virtual functions has its own **vtable**.
- Each object of such a class has a **vptr (virtual pointer)** that points to its class’s vtable.

---

### 🎯 Example Flow:

```cpp
Base* ptr; 
Derived obj; 
ptr = &obj; 
ptr->print();  // Calls Derived::print() because Base::print is virtual
```

➡️ Internally:
- `ptr` points to a `Derived` object
- Compiler checks the `vtable` to see if `print()` is overridden
- If yes, it calls `Derived::print()` instead of `Base::print()`

---

## 🔁 Key Rules

|Rule|Explanation|
|---|---|
|Use `virtual` in base class|To allow overriding|
|Use `override` in derived class|To make intention clear (C++11+)|
|Return type must be same|Cannot change return type in override|
|Works with pointers/references|Not with object slicing|

---

## ❌ If Not Virtual

```cpp
class A {
public:
    void show() { cout << "A" << endl; }
};

class B : public A {
public:
    void show() { cout << "B" << endl; }
};

A* ptr = new B();
ptr->show();  // Output: A (Not B!)

```

⚠️ Since `show()` is not virtual, C++ uses **early binding**, and calls the base version.

---

## ✅ Interview Tip:

Be ready for questions like:
- What is a virtual function?
- What is a vtable?
- Difference between early binding and late binding?
- What is object slicing?
- Can constructors be virtual? (**No**)
- Can destructors be virtual? (**Yes** – and should be when using inheritance**)
---

## 💡 Real-Life Analogy:

Think of a base class pointer as a **remote control**, and objects as **TV brands**.  
Virtual functions ensure that pressing "volume up" works according to the **brand-specific implementation** (derived class behavior), not just the base.