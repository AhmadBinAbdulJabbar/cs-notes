[[For Loop - striver notes]]

# **📌 `for` Loop in C++ (Detailed Notes)**

A **`for` loop** in C++ is used when **the number of iterations is known beforehand**. It is the most commonly used loop for iterating over arrays, vectors, or performing repeated operations efficiently.

---

# **1️⃣ Syntax of `for` Loop**

```cpp
for(initialization; condition; update)
{
    // Code to execute in each iteration
}
```

- **Initialization** → Runs once before the loop starts. (e.g., `int i = 0`)
- **Condition** → Checked before every iteration; if `true`, the loop runs; if `false`, it stops.
- **Update** → Executes after each iteration to modify the loop variable (e.g., `i++`).

---

# **2️⃣ Basic Example of `for` Loop**

```cpp
#include <iostream>
using namespace std;

int main() {
    for(int i = 1; i <= 5; i++) {
        cout << "Iteration: " << i << endl;
    }
    return 0;
}
```

🔹 **Output:**

```
Iteration: 1
Iteration: 2
Iteration: 3
Iteration: 4
Iteration: 5
```

---

# **3️⃣ Flow of `for` Loop**

1. **Initialization** → `int i = 1;` (Executes once)
2. **Condition Check** → `i <= 5` (If `true`, loop runs)
3. **Execute Loop Body** → `cout << "Iteration: " << i;`
4. **Update Statement** → `i++` (Increase `i` by 1)
5. **Repeat Steps 2-4** until `i <= 5` is `false`

---

# **4️⃣ Using `for` Loop with Arrays**

### **✅ Printing an Array**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};

    for(int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}
```

🔹 **Output:**

```
10 20 30 40 50
```

### **✅ Finding Sum of Array Elements**

```cpp
int sum = 0;
for(int i = 0; i < 5; i++) {
    sum += arr[i]; // Add each element to sum
}
cout << "Sum: " << sum;
```

---

# **5️⃣ Different Variations of `for` Loop**

### **✅ `for` Loop with `break` Statement**

- **Stops loop execution when a condition is met**

```cpp
for(int i = 1; i <= 10; i++) {
    if(i == 5) break;  // Stops when i = 5
    cout << i << " ";
}
```

🔹 **Output:** `1 2 3 4`

---

### **✅ `for` Loop with `continue` Statement**

- **Skips the current iteration and moves to the next**

```cpp
for(int i = 1; i <= 5; i++) {
    if(i == 3) continue;  // Skips iteration when i = 3
    cout << i << " ";
}
```

🔹 **Output:** `1 2 4 5` (Skips 3)

---

### **✅ Reverse `for` Loop (Decrementing)**

```cpp
for(int i = 5; i >= 1; i--) {
    cout << i << " ";
}
```

🔹 **Output:** `5 4 3 2 1`

---

### **✅ `for` Loop Without Initialization (Variable Declared Outside)**

```cpp
int i = 1;
for(; i <= 5; i++) {  // No initialization inside for loop
    cout << i << " ";
}
```

🔹 **Output:** `1 2 3 4 5`

---

### **✅ `for` Loop Without Update (Update Inside Loop Body)**

```cpp
for(int i = 1; i <= 5;) {  // No update inside for loop
    cout << i << " ";
    i++;  // Manually updating inside the loop
}
```

🔹 **Output:** `1 2 3 4 5`

---

# **6️⃣ Range-Based `for` Loop (For Arrays & Vectors)**

The **range-based `for` loop** simplifies iteration through arrays, vectors, and strings.

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};

    for(int x : arr) {
        cout << x << " ";  // Directly accesses each element
    }
    return 0;
}
```

🔹 **Output:** `10 20 30 40 50`

💡 **Advantage:** No need for `arr[i]` indexing, making the code cleaner.

---

# **7️⃣ Nested `for` Loops**

A **nested loop** is a loop inside another loop.

### **✅ Example: Printing a 2D Pattern**

```cpp
for(int i = 1; i <= 3; i++) {  // Outer loop
    for(int j = 1; j <= 5; j++) {  // Inner loop
        cout << "* ";
    }
    cout << endl;  // New line after each row
}
```

🔹 **Output:**

```
* * * * *
* * * * *
* * * * *
```

### **✅ Iterating Through a 2D Array**

```cpp
int arr[2][3] = {{1, 2, 3}, {4, 5, 6}};

for(int i = 0; i < 2; i++) {
    for(int j = 0; j < 3; j++) {
        cout << arr[i][j] << " ";
    }
    cout << endl;
}
```

🔹 **Output:**

```
1 2 3
4 5 6
```

---

# **8️⃣ Infinite `for` Loop**

```cpp
for(;;) {
    cout << "This is an infinite loop!";
}
```

💡 **Explanation:**

- Since **no condition is given**, it always remains `true`, creating an **infinite loop**.

---

# **📌 Summary of `for` Loop Concepts**

|Concept|Code Example|
|---|---|
|**Basic `for` Loop**|`for(int i = 1; i <= 5; i++)`|
|**Looping Through an Array**|`for(int i = 0; i < size; i++)`|
|**Reverse Loop**|`for(int i = 5; i >= 1; i--)`|
|**Skipping Iterations (`continue`)**|`if(i == 3) continue;`|
|**Breaking Loop (`break`)**|`if(i == 5) break;`|
|**Nested Loop**|`for(int i = 0; i < rows; i++)`|
|**Range-Based Loop**|`for(int x : arr)`|

---

# **📌 Example Code for `for` Loop**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter a number: ";
    cin >> n;

    cout << "Counting from 1 to " << n << ":\n";
    for(int i = 1; i <= n; i++) {
        cout << i << " ";
    }

    cout << "\nEven numbers from 1 to " << n << ":\n";
    for(int i = 2; i <= n; i += 2) {
        cout << i << " ";
    }

    return 0;
}
```

---

# **🎯 Key Takeaways**

✔ `for` loops are best for **fixed iterations**  
✔ Use **range-based `for` loops** for arrays & vectors  
✔ `break` stops a loop, `continue` skips an iteration  
✔ Nested `for` loops are useful for **2D structures**  
✔ Infinite `for(;;)` loops run forever

---

Would you like to cover **while loops** or move to **functions** next? 🚀