## 📘 Overview

|Concept|Function Overloading|Function Overriding|
|---|---|---|
|Type|Compile-time Polymorphism|Run-time Polymorphism|
|Inheritance Needed?|❌ No|✅ Yes|
|Function Name|Same|Same|
|Parameter List|Must be different|Must be same|
|Virtual Keyword|❌ Not used|✅ Required in base class|

---

## ✅ A. Function Overloading

### 🧠 Definition:

Function Overloading means having **multiple functions with the same name**, but **different parameters** (type or count) in the **same class**.

👉 Happens during **compile time**

---

### 🧪 Example:

```cpp
class Print {
public:
    void show(int x) {
        cout << "Integer: " << x << endl;
    }

    void show(string s) {
        cout << "String: " << s << endl;
    }

    void show(int x, float y) {
        cout << "Integer and Float: " << x << ", " << y << endl;
    }
};

```

📌 The compiler chooses the correct `show()` based on the arguments — this is called **function signature matching**.

---

### 📌 Key Points:

- Done in **same class**
- Different **parameter type**, **order**, or **count**
- No inheritance required.
---

## ✅ B. Function Overriding

### 🧠 Definition:

Function Overriding means **redefining a base class function in the derived class** with the **same name, parameters, and return type**.

👉 Happens during **runtime**

---

### 🧪 Example:

```cpp
class Animal {
public:
    virtual void speak() {
        cout << "Animal speaks" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "Dog barks" << endl;
    }
};

```

📌 If you call `speak()` using a **base class pointer**, the **derived class version** is executed — thanks to the `virtual` keyword.

---

### ⚠️ Without `virtual`:

If you remove `virtual`, the **base class version** is always called, even if the pointer is pointing to a derived object — this is **early binding**.

---

## ✅ Real-Life Analogy

|Concept|Analogy|
|---|---|
|Overloading|A Swiss knife has many blades (functions with different uses)|
|Overriding|A child overrides the behavior of a parent (e.g., `speak()` changes)|

---

## 🧠 Summary Table

|Feature|Overloading|Overriding|
|---|---|---|
|Type|Compile-time polymorphism|Run-time polymorphism|
|Inheritance|❌ Not required|✅ Required|
|Parameter List|Must be different|Must be same|
|Virtual Keyword|❌ Not needed|✅ Needed in base class|
|Number of Functions|Multiple in same class|One redefined in derived class|

---

## ✅ Interview Tip:

Common questions:
- Can you overload a constructor? (**Yes**)
- Can you override a private method? (**No**)
- Can return type differ in overriding? (**No**)
- Is overriding possible without inheritance? (**No**)