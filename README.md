# OOPS Concept: Inheritance Explained with a Twist!

Welcome to an unconventional explanation of **Inheritance**, a key concept in Object-Oriented Programming (OOPS). This README introduces inheritance with a fun storyline involving characters like Chintu, Pintu, Shakalan, and Kidmada. Let's dive in and learn inheritance through humor, relatable analogies, and code snippets!

---

## What is Inheritance?

In simple terms, **inheritance** is an OOPS concept that allows a class to "borrow" or "inherit" the attributes and methods from another class. Inheritance promotes **code reusability** and simplifies complex relationships between objects.

> In this story, inheritance is humorously depicted as "chori" (theft), "dakaiti" (robbery), and other playful scenarios.

---

## Types of Inheritance

### 1. **Single Inheritance**

In **single inheritance**, one class inherits from a single base class.

**Scenario:** Chintu "steals" the properties of Pintu.

```cpp
class Pintu {
public:
    void Pintufunc() {
        std::cout << "Inherited from Pintu\n";
    }
};

class Chintu : public Pintu {
public:
    void Chintufunc() {
        std::cout << "Function from Chintu\n";
    }
};

int main() {
    Chintu c;
    c.Pintufunc();  // Chintu uses Pintu's function
    c.Chintufunc();  // Chintu uses its own function
}
```

> Here, Chintu inherits from Pintu, gaining access to Pintu's methods and attributes.

---

### 2. **Multiple Inheritance**

In **multiple inheritance**, a class inherits from more than one base class.

**Scenario:** Chintu decides to become a "dakait" and steals from both Pintu and Sonu!

```cpp
class Sonu {
public:
    void Sonufunc() {
        std::cout << "Function from Sonu\n";
    }
};

class Pintu {
public:
    void Pintufunc() {
        std::cout << "Function from Pintu\n";
    }
};

class Chintu : public Sonu, public Pintu {
public:
    void Chintufunc() {
        std::cout << "Function from Chintu\n";
    }
};

int main() {
    Chintu c;
    c.Sonufunc();  // Chintu uses Sonu's function
    c.Pintufunc();  // Chintu uses Pintu's function
    c.Chintufunc(); // Chintu uses its own function
}
```

> Chintu, being a smart "dakait," inherits from both Sonu and Pintu, gaining access to both their functions.

---

### 3. **Multilevel Inheritance**

In **multilevel inheritance**, a class inherits from a derived class, forming a chain.

**Scenario:** Shakalan "steals" the properties from Chintu, who already stole from Pintu.

```cpp
class Pintu {
public:
    void Pintufunc() {
        std::cout << "Function from Pintu\n";
    }
};

class Chintu : public Pintu {
public:
    void Chintufunc() {
        std::cout << "Function from Chintu\n";
    }
};

class Shakalan : public Chintu {
public:
    void Shakalanfunc() {
        std::cout << "Function from Shakalan\n";
    }
};

int main() {
    Shakalan s;
    s.Pintufunc();    // Accessing Pintu's function
    s.Chintufunc();   // Accessing Chintu's function
    s.Shakalanfunc(); // Accessing its own function
}
```

> Shakalan inherits from Chintu, who already inherited from Pintu. The chain continues!

---

### 4. **Hierarchical Inheritance**

In **hierarchical inheritance**, multiple classes inherit from the same base class, forming a tree-like structure.

**Scenario:** Class A acts as the base class, and multiple classes B and C inherit from it.

```cpp
class A {
public:
    void Afunc() {
        std::cout << "Function from A\n";
    }
};

class B : public A {
public:
    void Bfunc() {
        std::cout << "Function from B\n";
    }
};

class C : public A {
public:
    void Cfunc() {
        std::cout << "Function from C\n";
    }
};

int main() {
    B b;
    C c;
    b.Afunc();  // B inherits A's function
    b.Bfunc();  // B uses its own function

    c.Afunc();  // C inherits A's function
    c.Cfunc();  // C uses its own function
}
```

> This forms a tree-like structure where class B and class C both inherit from class A.

---

### 5. **Hybrid Inheritance**

In **hybrid inheritance**, a combination of more than one type of inheritance is used. However, this can lead to the **diamond problem** in C++, which is typically resolved using **virtual inheritance**.

---

## Key Takeaways

- Inheritance promotes **code reusability**.
- **Public** and **protected** members can be inherited, but **private** members cannot be directly accessed.
- Beware of potential issues like the **diamond problem** in multiple and hybrid inheritance.

---

## Characters in the Story

- **Pintu**: The base class, often the "victim" whose properties are inherited.
- **Chintu**: The "chor" (thief) who inherits from Pintu (and sometimes Sonu).
- **Sonu**: Another base class.
- **Shakalan**: The "wife" who inherits from Chintu.
- **Kidmada**: A class involved in a "twisted affair" with Shakalan (multiple inheritance case).

---

# C++ Inheritance Question

## Question:
Consider the following C++ code snippet. What is the type of inheritance used, and what will be the output of the `sizeof(B)` statement?

### Code Snippet:
```cpp
#include <iostream>  
#include <string>  
using namespace std;  

class A {  
    int a, b;  
    float d;  

public:  
    void change(int l) {  
        a = l;  
    }  

    void value_of_a() {  
        cout << a;  
    }  
};  

class B : private A {  
};  

int main(int argc, char const *argv[]) {  
    B b;  
    cout << sizeof(B);  
    return 0;  
}  
```

## Discussion Points:
- **Inheritance Type:**
  - The inheritance here is `private` inheritance, meaning class `B` inherits all the members of class `A` privately. This makes the inherited members inaccessible from outside class `B`, but they still contribute to the size of class `B`.

- **Size Calculation:**
  - In C++, private members are inherited but remain hidden in the derived class. Since class `A` contains three data members (two `int`s and one `float`), the size of class `B` will include those members.
  - Depending on padding and alignment, the exact size of class `B` might vary based on your compiler and system architecture.

## Output Example:
For many compilers on typical architectures, you might expect the size of `B` to be 12 bytes due to the presence of `int` (4 bytes) and `float` (4 bytes) and potential padding.

---

## Conclusion

This README used humor and relatable analogies to explain the concept of inheritance in C++. We hope this unconventional approach made learning OOPS more enjoyable!

---

*Happy Coding!*

---

