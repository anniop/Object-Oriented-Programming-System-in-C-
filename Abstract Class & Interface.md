## 📘 What is an Abstract Class?

An **abstract class** is a class that **cannot be instantiated** (you cannot create an object of it) and **contains at least one pure virtual function**.

---
### 🔸 Pure Virtual Function

A function that is declared using:

```cpp
virtual void func() = 0;
```

> It **forces** derived classes to **override** that function.

---

### 🧪 Example of Abstract Class

```cpp
class Shape {
public:
    virtual void area() = 0;  // Pure virtual function

    void printName() {
        cout << "This is a shape.\n";
    }
};

class Circle : public Shape {
public:
    void area() override {
        cout << "Area of Circle: πr²\n";
    }
};

```

✅ `Shape` is an **abstract class** because it contains a **pure virtual function**.

---

### 📌 Key Points:

|Feature|Abstract Class|
|---|---|
|Can have data members?|✅ Yes|
|Can have constructors?|✅ Yes (but can't instantiate)|
|Can have normal functions?|✅ Yes|
|Can have pure virtual functions?|✅ Must have ≥ 1|

---

## 📘 What is an Interface in C++?

C++ doesn’t have a keyword `interface` like Java, but you can **simulate an interface** using an abstract class that has:
- Only **pure virtual functions**
- **No data members**
- **No implementation**
---

### 🧪 Interface in C++ (Simulation)

```cpp
class Printable {
public:     
	virtual void print() = 0;  // Pure virtual     
	virtual void format() = 0; // Pure virtual
};
```

Any class that inherits `Printable` **must override all functions**, or it becomes abstract too.

---

## 🔁 Abstract Class vs Interface

|Feature|Abstract Class|Interface (in C++)|
|---|---|---|
|Contains data members|✅ Yes|❌ No|
|Contains constructors|✅ Yes|❌ (usually not)|
|Normal function allowed|✅ Yes|❌ Only pure virtual allowed|
|Must override all methods?|❌ No|✅ Yes|

---

## 🧠 Real-Life Analogy:

- **Abstract Class** = A general category with some ready-to-use code.  
    _(e.g., Vehicle has engine info common to all vehicles.)_
- **Interface** = A contract; class must follow it completely.  
    _(e.g., Printable, Drivable, etc.)_

---

## ✅ Interview Tip:

Common questions:
- Can you instantiate an abstract class? (**No**)
- Can a class be both abstract and concrete? (**Yes** — if it has both pure and non-pure functions)
- Can you inherit multiple interfaces in C++? (**Yes** — multiple inheritance)

---

### ✅ Bonus: Use Case

- Use **abstract class** when:
    - You want base behavior + derived customization
- Use **interface** (pure abstract class) when:
    - You want to enforce behavior only, no shared implementation