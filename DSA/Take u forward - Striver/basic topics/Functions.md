# **📌 Functions in C++ (Detailed Notes)**

A **function** in C++ is a block of code that performs a specific task and can be called multiple times, making code more **organized, reusable, and manageable**.

---

## **1️⃣ Why Use Functions?**

✔ **Code Reusability** – Avoid writing the same code multiple times.  
✔ **Better Readability** – Break code into logical sections.  
✔ **Easier Debugging** – Test and fix smaller pieces of code.  
✔ **Modular Programming** – Divide complex problems into smaller functions.

---

## **2️⃣ Types of Functions in C++**

Functions in C++ are categorized into **4 types** based on parameters and return values:

|**Type**|**Parameters**|**Return Value**|
|---|---|---|
|**1. Function with No Parameters & No Return Value**|❌ No|❌ No|
|**2. Function with Parameters & No Return Value**|✅ Yes|❌ No|
|**3. Function with No Parameters & Return Value**|❌ No|✅ Yes|
|**4. Function with Parameters & Return Value**|✅ Yes|✅ Yes|

---

## **3️⃣ Syntax of a Function**

```cpp
return_type function_name(parameters) {
    // Function body (code to execute)
    return value; // (if return type is not void)
}
```

- **`return_type`** – The data type of the value the function returns (`int`, `float`, `void`, etc.).
- **`function_name`** – The name used to call the function.
- **`parameters`** – Values (arguments) passed to the function.
- **`return`** – Returns a value to the caller.

---

# **📌 4 Types of Functions (with Examples)**

## **1️⃣ Function with No Parameters & No Return Value**

- Takes **no arguments** and returns **nothing** (`void`).
- Used for **printing** or performing **actions** without needing external data.

```cpp
#include <iostream>
using namespace std;

void greet() {
    cout << "Hello, Ahmad!" << endl;
}

int main() {
    greet();  // Calling the function
    return 0;
}
```

🔹 **Output:**

```
Hello, Ahmad!
```

---

## **2️⃣ Function with Parameters & No Return Value**

- Takes **arguments** but **does not return** a value.
- Used when we need **input values** but no result needs to be returned.

```cpp
#include <iostream>
using namespace std;

void printSum(int a, int b) {  // Function with parameters
    cout << "Sum: " << (a + b) << endl;
}

int main() {
    printSum(5, 7);  // Passing values 5 and 7
    return 0;
}
```

🔹 **Output:**

```
Sum: 12
```

---

## **3️⃣ Function with No Parameters & Return Value**

- Takes **no arguments** but **returns a value**.
- Used when **no external input** is required but **we need a result**.

```cpp
#include <iostream>
using namespace std;

int getNumber() {  // Function without parameters
    return 42;  // Returns a value
}

int main() {
    int num = getNumber();  // Storing returned value
    cout << "Number: " << num << endl;
    return 0;
}
```

🔹 **Output:**

```
Number: 42
```

---

## **4️⃣ Function with Parameters & Return Value**

- Takes **arguments** and **returns a value**.
- Used when we need **both input** and **a result**.

```cpp
#include <iostream>
using namespace std;

int multiply(int a, int b) {  // Function with parameters and return value
    return a * b;
}

int main() {
    int result = multiply(4, 3);  // Storing returned value
    cout << "Multiplication: " << result << endl;
    return 0;
}
```

🔹 **Output:**

```
Multiplication: 12
```

---

# **4️⃣ Function Declaration vs Definition vs Calling**

C++ functions have three key steps:

1. **Declaration (Prototype)** – Tells the compiler about the function before defining it.
2. **Definition (Implementation)** – Contains the actual code of the function.
3. **Calling** – Executes the function in `main()`.

```cpp
#include <iostream>
using namespace std;

// Function Declaration
int add(int, int);  

int main() {
    int sum = add(10, 5);  // Function Calling
    cout << "Sum: " << sum;
    return 0;
}

// Function Definition
int add(int x, int y) {  
    return x + y;
}
```

🔹 **Output:**

```
Sum: 15
```

💡 **Why Declare Functions?**  
✔ Helps when defining functions **after `main()`**.  
✔ Allows **modular programming**.

---

# **5️⃣ Function Overloading**

C++ allows **multiple functions with the same name** but different parameters.

```cpp
#include <iostream>
using namespace std;

void print(int a) {  // Function for int
    cout << "Integer: " << a << endl;
}

void print(double b) {  // Function for double
    cout << "Double: " << b << endl;
}

int main() {
    print(5);      // Calls print(int)
    print(3.14);   // Calls print(double)
    return 0;
}
```

🔹 **Output:**

```
Integer: 5
Double: 3.14
```

---

# **6️⃣ Default Arguments in Functions**

- **Assigns default values** to parameters if **not provided**.
- Helps **avoid passing values** every time.

```cpp
#include <iostream>
using namespace std;

void greet(string name = "Ahmad") {  // Default value
    cout << "Hello, " << name << "!" << endl;
}

int main() {
    greet();          // Uses default value
    greet("Ali");     // Uses given argument
    return 0;
}
```

🔹 **Output:**

```
Hello, Ahmad!
Hello, Ali!
```

---

# **7️⃣ Pass by Value vs Pass by Reference**

### **Pass by Value (Creates a Copy)**

```cpp
void change(int x) {
    x = 100;  // This change does NOT affect original variable
}
```

### **Pass by Reference (Modifies Original)**

```cpp
void change(int &x) {
    x = 100;  // This change affects original variable
}
```

🔹 **Use `&` to modify original values.**

---

# **8️⃣ Recursive Functions**

A **function calling itself** to solve a problem.

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    if(n == 0) return 1;  // Base case
    return n * factorial(n - 1);  // Recursive call
}

int main() {
    cout << "Factorial of 5: " << factorial(5);
    return 0;
}
```

🔹 **Output:**

```
Factorial of 5: 120
```

💡 **Use Recursion for:** Factorials, Fibonacci, Tree Traversals.

---

# **📌 Summary**

✔ **4 Types of Functions:**

- **No Parameters, No Return** → `void greet()`
- **With Parameters, No Return** → `void printSum(int, int)`
- **No Parameters, With Return** → `int getNumber()`
- **With Parameters & Return** → `int multiply(int, int)`

✔ **Concepts Covered:**

- Function **Declaration, Definition, and Calling**
- **Overloading** (Same function name, different parameters)
- **Default Arguments** (Predefined parameter values)
- **Pass by Value vs Reference** (Modify original values)
- **Recursion** (Function calling itself)
