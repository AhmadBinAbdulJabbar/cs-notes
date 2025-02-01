Striver Notes [[Basic Input output]]
## 📝 **C++ Basics: Input & Output, Libraries, and `std` Namespace**

### 📌 **1. Libraries in C++**

Libraries contain pre-written functions that help perform various tasks. To use them, we include them at the beginning of the program with `#include`.

#### **Common Libraries**

```cpp
#include <iostream>  // For input and output operations (cin, cout)
#include <math.h>    // For mathematical functions (sqrt, pow, etc.)
#include <string>    // For working with strings
```

Instead of including multiple libraries separately, we can use **one header file**:

```cpp
#include <bits/stdc++.h> // Includes all standard C++ libraries (Only works in GCC compilers)
```

🔹 `#include <bits/stdc++.h>` is **not standard** in competitive programming but useful for quick coding.

---

### 📌 **2. The `std` Namespace**

The **`std` (Standard) namespace** contains built-in functions and classes from C++ standard libraries.  
Example:

```cpp
std::cout << "Hello, World!" << std::endl;
std::cin >> x;
```

👉 Instead of writing `std::cout` and `std::cin` repeatedly, we use:

```cpp
using namespace std;
```

Now, we can write:

```cpp
cout << "Hello, World!" << endl;
cin >> x;
```

🔹 **Best practice**: Avoid `using namespace std;` in large projects to prevent conflicts.

---

### 📌 **3. Basic Input & Output in C++**

#### ✅ **Output (`cout`)**

To print text or variables:

```cpp
cout << "Hello, World!\n";  // Using \n for a new line
cout << "Hello Ahmad" << endl;  // Using endl for a new line
```

🔹 `\n` is **faster** than `endl` because `endl` also flushes the output buffer.

#### ✅ **Input (`cin`)**

To take input from the user:

```cpp
int x, y;
cin >> x >> y;
cout << "Value of X: " << x << " and Y: " << y << endl;
```

🔹 **Multiple inputs**: `cin` automatically separates inputs by spaces.

---

### 📌 **4. Full Code Example**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    cout << "Hello World\n";  
    cout << "Hello Ahmad" << endl;

    int x, y;
    cin >> x >> y;
    cout << "Value of X: " << x << " and Y: " << y << endl;

    return 0;
}
```

---

This should be a good structure for your notes! Let me know the next topic, and I'll format it for you. 🚀