# **📌 `do-while` Loop in C++ (Detailed Notes)**

A **`do-while` loop** in C++ is similar to a `while` loop, but it guarantees that the loop body executes **at least once** before checking the condition.

---

# **1️⃣ Syntax of `do-while` Loop**

```cpp
do {
    // Code to execute
} while(condition);
```

- **Loop Body** → Executes **once** unconditionally.
- **Condition Check** → If `true`, the loop runs again; if `false`, it stops.

---

# **2️⃣ Basic Example of `do-while` Loop**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    
    do {
        cout << "Iteration: " << i << endl;
        i++;
    } while(i <= 5);
    
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

💡 **Difference from `while` Loop:** Even if `i` was initialized as `10`, the loop would still run **once** before stopping.

---

# **3️⃣ Flow of `do-while` Loop**

1. **Execute Loop Body** → Runs the code inside `{}` once.
2. **Condition Check** → If `true`, repeat step 1; otherwise, stop.

---

# **4️⃣ Key Difference: `while` vs `do-while`**

|Feature|`while` Loop|`do-while` Loop|
|---|---|---|
|**Condition Check**|Before execution|After first execution|
|**Executes At Least Once?**|No|Yes|
|**Usage**|When execution depends on condition|When at least one iteration is required|

### **✅ Example Comparison**

```cpp
int num = 10;

while(num < 5) {
    cout << "Inside while loop";
}

do {
    cout << "Inside do-while loop";
} while(num < 5);
```

🔹 **Output:**

```
Inside do-while loop
```

💡 Even though `num < 5` is `false`, **`do-while` runs once!**

---

# **5️⃣ Example: Taking Input Until User Enters a Valid Number**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num;
    
    do {
        cout << "Enter a number greater than 0: ";
        cin >> num;
    } while(num <= 0);

    cout << "You entered: " << num;
    return 0;
}
```

🔹 **Example Output:**

```
Enter a number greater than 0: -5
Enter a number greater than 0: 0
Enter a number greater than 0: 10
You entered: 10
```

💡 **Use Case:** Ensures at least one input attempt.

---

# **6️⃣ `do-while` Loop for Menu-Driven Programs**

```cpp
#include <iostream>
using namespace std;

int main() {
    int choice;
    
    do {
        cout << "\nMenu:\n";
        cout << "1. Option 1\n";
        cout << "2. Option 2\n";
        cout << "3. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice) {
            case 1: cout << "You selected Option 1\n"; break;
            case 2: cout << "You selected Option 2\n"; break;
            case 3: cout << "Exiting program...\n"; break;
            default: cout << "Invalid choice! Try again.\n";
        }
    } while(choice != 3);

    return 0;
}
```

🔹 **Example Output:**

```
Menu:
1. Option 1
2. Option 2
3. Exit
Enter your choice: 5
Invalid choice! Try again.

Menu:
4. Option 1
5. Option 2
6. Exit
Enter your choice: 3
Exiting program...
```

💡 **Use Case:** Keeps showing the menu **until** the user selects `Exit`.

---

# **7️⃣ `do-while` Loop with Arrays**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int i = 0;

    do {
        cout << arr[i] << " ";
        i++;
    } while(i < 5);

    return 0;
}
```

🔹 **Output:** `10 20 30 40 50`

---

# **8️⃣ Finding the Sum of Digits Using `do-while`**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num, sum = 0;
    
    cout << "Enter a number: ";
    cin >> num;

    do {
        sum += num % 10; // Extract last digit and add to sum
        num /= 10; // Remove last digit
    } while(num > 0);

    cout << "Sum of digits: " << sum;
    return 0;
}
```

🔹 **Example Output:**

```
Enter a number: 123
Sum of digits: 6
```

💡 **Why `do-while`?** Even if `num = 0`, it ensures **one** execution.

---

# **9️⃣ Infinite `do-while` Loop**

An **infinite loop** happens if the condition is **always true**.

```cpp
do {
    cout << "This is an infinite loop!";
} while(true);
```

💡 **Fix:** Ensure an **exit condition** inside the loop.

---

# **🔟 Summary: When to Use `do-while` Loop?**

|**Scenario**|**Use `do-while`?**|
|---|---|
|Menu-driven programs|✅ Yes|
|Taking input at least once|✅ Yes|
|Checking a condition before execution|❌ No (use `while`)|
|Running until the user meets a condition|✅ Yes|
|Looping through an array|❌ No (use `for` or `while`)|

---

# **🎯 Key Takeaways**

✔ `do-while` **always runs at least once**  
✔ Best for **menus, user input validation, and sum calculations**  
✔ Ensure the condition eventually turns `false` to prevent infinite loops  
✔ Use `while` when a **pre-check** is needed

---

Would you like to cover **functions** next, or do you have a different topic in mind? 🚀