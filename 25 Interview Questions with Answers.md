### 🔹 Basic Conceptual Questions

1. **What is OOP?**
    
    > OOP (Object-Oriented Programming) is a programming paradigm that organizes code into classes and objects for better modularity, reusability, and abstraction.
  
2. **What are the 4 pillars of OOP?**
    
    > Abstraction, Encapsulation, Inheritance, Polymorphism
    
3. **What is a class and an object?**
    
    > A class is a blueprint. An object is an instance of a class.
    
4. **What is encapsulation?**
    
    > Wrapping data and related functions together in a class and restricting direct access using access specifiers.
    
5. **What is abstraction?**
    
    > Hiding internal implementation and exposing only necessary functionality.
    
6. **What is inheritance?**
    
    > Acquiring properties and behavior from another class.
    
7. **What is polymorphism?**
    
    > The ability to take many forms. Same function behaves differently based on context (compile-time and run-time).
    
8. **What is function overloading?**
    
    > Defining multiple functions with the same name but different parameters in the same scope.
    
9. **What is function overriding?**
    
    > Redefining a base class function in a derived class with the same signature.
    
10. **What is a constructor?**
    
    > A special function that initializes an object when it is created.
    

---

### 🔹 Deeper Conceptual/Technical Questions

11. **What is a copy constructor?**
    
    > A constructor that initializes a new object using an existing object.
    
12. **Can constructors be virtual?**
    
    > ❌ No.
    
13. **Can destructors be virtual?**
    
    > ✅ Yes — they **should be virtual** when using inheritance to avoid memory leaks.
    
14. **What is the use of the `this` pointer?**
    
    > It points to the current object and is used to distinguish between member and parameter variables.
    
15. **What is a virtual function?**
    
    > A function declared with the `virtual` keyword that allows run-time binding for overridden functions.
    
16. **What is a pure virtual function?**
    
    > A virtual function with no body (`= 0`) that must be overridden in derived classes.
    
17. **What is an abstract class?**
    
    > A class with at least one pure virtual function.
    
18. **What is object slicing?**
    
    > When a derived object is assigned to a base object, only base members are copied — derived-specific info is lost.
    
19. **What is a static member?**
    
    > A member shared across all objects of a class.
    
20. **Can we access private members using friend functions?**
    
    > ✅ Yes.
    

---

### 🔹 Miscellaneous & Trick Questions

21. **What happens if a class has a pure virtual destructor?**
    
    > It must have a definition too, even if pure.
    
22. **What is the difference between interface and abstract class?**
    
    > Interface = all functions pure virtual; Abstract class = may have some implementation.
    
23. **How is memory allocated for static members?**
    
    > Outside the class using `ClassName::member = value;`
    
24. **Can we overload a destructor?**
    
    > ❌ No — only one destructor allowed per class.
    
25. **What is the difference between early binding and late binding?**
    
    > Early (compile-time): Function call decided at compile time (e.g., overloading)  
    > Late (run-time): Function call decided during execution using virtual functions.