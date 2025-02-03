[[While loop - striver notes]]

# **📌 `while` Loop in C++ (Detailed Notes)**

A **`while` loop** in C++ is used when **the number of iterations is unknown** beforehand and depends on a condition being met.

---

# **1️⃣ Syntax of `while` Loop**

```cpp
while(condition)
{
    // Code to execute in each iteration
}
```

- **Condition** → Checked before every iteration; if `true`, the loop runs; if `false`, it stops.
- **Loop Body** → Executes as long as the condition remains `true`.

---

# **2️⃣ Basic Example of `while` Loop**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1; // Initialization
    while(i <= 5) { // Condition
        cout << "Iteration: " << i << endl;
        i++; // Update
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

# **3️⃣ Flow of `while` Loop**

1. **Condition Check** → `i <= 5` (If `true`, loop runs)
2. **Execute Loop Body** → `cout << i`
3. **Update Statement** → `i++`
4. **Repeat Steps 1-3** until `i <= 5` is `false`

---

# **4️⃣ Example: Taking User Input Until Condition is Met**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    cout << "Enter a number (0 to stop): ";
    cin >> num;

    while(num != 0) {
        cout << "You entered: " << num << endl;
        cout << "Enter another number (0 to stop): ";
        cin >> num;
    }
    
    cout << "Loop ended.";
    return 0;
}
```

🔹 **Example Output:**

```
Enter a number (0 to stop): 5
You entered: 5
Enter another number (0 to stop): 10
You entered: 10
Enter another number (0 to stop): 0
Loop ended.
```

💡 **Use Case:** Continues asking for input until the user enters `0`.

---

# **5️⃣ Infinite `while` Loop**

A **`while` loop** can become infinite if the condition never turns `false`.

```cpp
while(true) {
    cout << "This is an infinite loop!";
}
```

💡 **Fix:** Ensure there's an **update statement** inside the loop to change the condition.

---

# **6️⃣ Using `while` Loop for Valid Input**

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    
    cout << "Enter a valid age (between 1 and 100): ";
    cin >> age;
    
    while(age < 1 || age > 100) { // If invalid, keep asking
        cout << "Invalid age! Enter again: ";
        cin >> age;
    }

    cout << "Valid age entered: " << age;
    return 0;
}
```

🔹 **Example Output:**

```
Enter a valid age (between 1 and 100): -5
Invalid age! Enter again: 105
Invalid age! Enter again: 25
Valid age entered: 25
```

💡 **Use Case:** Ensures the user enters a valid value.

---

# **7️⃣ `while` Loop with Arrays**

### **✅ Printing an Array**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int i = 0;

    while(i < 5) {
        cout << arr[i] << " ";
        i++;
    }

    return 0;
}
```

🔹 **Output:** `10 20 30 40 50`

---

# **8️⃣ Nested `while` Loop**

A **nested `while` loop** is a loop inside another loop.

### **✅ Example: Printing a Pattern**

```cpp
int i = 1;
while(i <= 3) {  // Outer loop
    int j = 1;
    while(j <= 5) {  // Inner loop
        cout << "* ";
        j++;
    }
    cout << endl;
    i++;
}
```

🔹 **Output:**

```
* * * * *
* * * * *
* * * * *
```

---

# **9️⃣ Difference Between `for` and `while` Loops**

|Feature|`for` Loop|`while` Loop|
|---|---|---|
|**Use Case**|When iterations are known|When iterations are unknown|
|**Syntax**|`for(init; condition; update)`|`while(condition)`|
|**Initialization**|Inside loop header|Before loop|
|**Update**|In loop header|Inside loop body|

### **✅ Example Comparison**

```cpp
// Using for loop
for(int i = 1; i <= 5; i++) {
    cout << i << " ";
}

// Using while loop
int i = 1;
while(i <= 5) {
    cout << i << " ";
    i++;
}
```

🔹 **Both Output:** `1 2 3 4 5`

---

# **🔟 Example Program: Finding Sum of Digits Using `while` Loop**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num, sum = 0;
    
    cout << "Enter a number: ";
    cin >> num;

    while(num > 0) {
        sum += num % 10; // Extract last digit and add to sum
        num /= 10; // Remove last digit
    }

    cout << "Sum of digits: " << sum;
    return 0;
}
```

🔹 **Example Output:**

```
Enter a number: 123
Sum of digits: 6
```

---

# **📌 Summary of `while` Loop Concepts**

|Concept|Code Example|
|---|---|
|**Basic `while` Loop**|`while(condition) { code; }`|
|**Taking User Input Until Condition is Met**|`while(num != 0) { cin >> num; }`|
|**Looping Through an Array**|`while(i < size) { cout << arr[i]; i++; }`|
|**Validating Input**|`while(age < 1|
|**Infinite Loop**|`while(true) { cout << "Looping"; }`|

---

# **🎯 Key Takeaways**

✔ `while` loops are used when the number of iterations is **unknown**  
✔ Always include an **update statement** to avoid infinite loops  
✔ `while` loops are useful for **validating user input**  
✔ Use **nested `while` loops** for **2D patterns** or **arrays**

---

Would you like to cover **do-while loops** or move to **functions** next? 🚀