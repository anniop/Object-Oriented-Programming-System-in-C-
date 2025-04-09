## 📘 What are Access Specifiers?
**Access specifiers** define **who can access** the members (variables and functions) of a class.

They control the **visibility and scope** of class members.

---

### 🔐 Types of Access Specifiers:

|Specifier|Accessible Within Class|Accessible in Derived Class|Accessible Outside Class|
|---|---|---|---|
|`private`|✅ Yes|❌ No|❌ No|
|`protected`|✅ Yes|✅ Yes|❌ No|
|`public`|✅ Yes|✅ Yes|✅ Yes|

---

### 🧪 Example:

```cpp
class MyClass { 
private:     
	int a;  // accessible only inside MyClass  
protected:     
	int b;  // accessible inside MyClass & derived classes  
public:     
	int c;  // accessible from anywhere 
};
```

---

### ✅ Interview Tip:

Be prepared for questions like:

- "What is the difference between private, public, and protected?"
- "Can protected members be accessed outside the class?"
- "How does access specifier affect inheritance?"

---

### 🧠 Use Cases

|Specifier|Use For|
|---|---|
|`private`|Hiding internal variables (Encapsulation)|
|`protected`|Keeping data hidden from outside, but open to inherited classes|
|`public`|Open functions to user/program (like `print()`, `input()`)|

---

### 🚧 Bonus: Access Specifiers in Inheritance

|Base → Derived|public inheritance|protected inheritance|private inheritance|
|---|---|---|---|
|`public`|public|protected|private|
|`protected`|protected|protected|private|
|`private`|❌ inaccessible|❌ inaccessible|❌ inaccessible|

🧠 Meaning: Access level can only **reduce**, never increase in inheritance.

---

### ✅ Summary in Simple Words:

- Use `private` for **sensitive data**
- Use `protected` if **child classes need access**
- Use `public` for **interface functions** or user-facing methods

---

