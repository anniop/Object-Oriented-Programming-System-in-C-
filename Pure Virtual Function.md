### 📘 What is a Pure Virtual Function?

A **pure virtual function** is a function that has **no body** in the base class and **must be overridden** in any derived class.

---
### 🔸 Syntax:

```cpp
virtual void functionName() = 0;
```

The `= 0` makes it a **pure virtual function**.

---

### 🧠 Why Do We Use Pure Virtual Functions?

- To **enforce overriding** in derived classes.
- To create a **base class interface** — without any actual implementation.
- To make a class **abstract** (so it can’t be instantiated).
---

### 🧪 Example:

```cpp
class Shape {
public:    
	virtual void area() = 0;  // Pure virtual function 
};  

class Circle : public Shape { 
public:     
	void area() override {        
		 cout << "Area of Circle: πr²" << endl;    
	} 
};
```

📌 Here, `Shape` is an abstract class.  
📌 `Circle` must override the `area()` function — or else it too becomes abstract.

---

### ⚠️ Key Rules:

|Rule|Explanation|
|---|---|
|Pure virtual = abstract class|Even one pure virtual → abstract|
|Cannot instantiate|You can't create objects of abstract class|
|Must override|All pure virtual functions in child|
|No function body in base|Only declaration is allowed|

---

### 📌 Real-Life Analogy:

Think of a pure virtual function as a **rule or a contract**:
- A parent says: “Every child class **must** implement this behavior.”
Example:
- `Drawable` interface with `draw()` method — any shape that is drawable **must implement draw()**.
---

## ✅ Interview Tip:

**Q:** Why use a pure virtual function instead of a regular one?  
**A:** To force every derived class to have its own version of the function (i.e., enforce customization).
**Q:** Can we have some regular and some pure virtual functions in one class?  
**A:** Yes — that’s what makes it an **abstract class** with shared and enforceable behavior.

---

### 🔁 Summary Table

|Feature|Pure Virtual Function|
|---|---|
|Ends with `= 0`|✅ Yes|
|Body in base class?|❌ No|
|Must be overridden?|✅ Yes|
|Makes class abstract?|✅ Yes|
