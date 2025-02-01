[[if else article]]
### 1. **If Statement**

The `if` statement checks a condition and executes the code inside the block if the condition is `true`.

**Syntax:**

```cpp
if(condition) {
    // Code to execute if condition is true
}
```

Example:

```cpp
if(age >= 18) {
    cout << "Adult";
}
```

### 2. **If-Else Statement**

The `if-else` statement allows two different blocks of code: one for when the condition is `true` and another for when it's `false`.

**Syntax:**

```cpp
if(condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

Example:

```cpp
if(age >= 18) {
    cout << "Adult";
} else {
    cout << "Not Adult";
}
```

### 3. **If-Else If Statement**

The `if-else if` statement lets you check multiple conditions in sequence. Only the first condition that evaluates to `true` will execute its corresponding block.

**Syntax:**

```cpp
if(condition1) {
    // Code to execute if condition1 is true
} else if(condition2) {
    // Code to execute if condition2 is true
} else {
    // Code to execute if no condition is true
}
```

Example:

```cpp
if(marks < 25) {
    cout << "F";
} else if(marks <= 44) {
    cout << "E";
} else if(marks <= 49) {
    cout << "D";
} else if(marks <= 59) {
    cout << "C";
} else if(marks <= 79) {
    cout << "B";
} else {
    cout << "A";
}
```

### 4. **Nested If-Else Statement**

A nested `if-else` statement is an `if` or `else if` statement inside another `if`, `else if`, or `else`. It's useful when you need to check multiple conditions in layers.

**Syntax:**

```cpp
if(condition1) {
    if(condition2) {
        // Code if both conditions are true
    } else {
        // Code if condition1 is true, but condition2 is false
    }
} else {
    // Code if condition1 is false
}
```

Example:

```cpp
if(age1 < 18) {
    cout << "not eligible for job";
} else if(age1 <= 57) {
    cout << "eligible for job";
    if(age1 >= 55) {
        cout << ", but retirement soon";
    }
} else {
    cout << "retirement time";
}
```

### 5. **Best Practices for Conditional Statements**

- **Avoid redundant checks:** For example, if an earlier condition is already checked, you don't need to check it again later in the same block. This can improve readability and performance.

Example:

```cpp
if(marks < 25) {
    cout << "F";
} else if(marks <= 44) {
    cout << "E";
} else if(marks <= 49) {
    cout << "D";
} else if(marks <= 59) {
    cout << "C";
} else if(marks <= 79) {
    cout << "B";
} else {
    cout << "A";
}
```

This is more efficient than checking `marks >= 25` again in each condition.

### 6. **Logical Operators in Conditions**

You can combine multiple conditions using logical operators:

- **AND (`&&`)**: All conditions must be true.
- **OR (`||`)**: At least one condition must be true.
- **NOT (`!`)**: Reverses the truth value of a condition.

Example:

```cpp
if(age >= 18 && age <= 57) {
    cout << "Eligible for job";
} else {
    cout << "Not eligible for job";
}
```

---

### Full Code (Including All Tasks):

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
  // Task 1: Age-based eligibility check
  int age = 0;
  cout << "Enter age: ";
  cin >> age;
  cout << age << endl;
  if(age >= 18) {
    cout << "Adult" << endl;
  } else {
    cout << "Not Adult" << endl;
  } 

  // Task 2: Grading System
  int marks;
  cout << "Enter marks: ";
  cin >> marks;
  cout << marks << endl;

  // 1st approach (not recommended as it checks all conditions)
  if(marks < 25) {
    cout << "F" << endl;
  }
  if(marks >= 25 && marks <= 44) {
    cout << "E" << endl;
  }
  if(marks >= 45 && marks <= 49) {
    cout << "D" << endl;
  }
  if(marks >= 50 && marks <= 59) {
    cout << "C" << endl;
  }
  if(marks >= 60 && marks <= 79) {
    cout << "B" << endl;
  }
  if(marks >= 80 && marks <= 100) {
    cout << "A" << endl;
  }

  // 2nd approach (using if-else if for better efficiency)
  if(marks < 25) {
    cout << "F" << endl;
  } else if(marks >= 25 && marks <= 44) {
    cout << "E" << endl;
  } else if(marks >= 45 && marks <= 49) {
    cout << "D" << endl;
  } else if(marks >= 50 && marks <= 59) {
    cout << "C" << endl;
  } else if(marks >= 60 && marks <= 79) {
    cout << "B" << endl;
  } else if(marks >= 80 && marks <= 100) {
    cout << "A" << endl;
  }

  // 3rd approach (best way)
  if(marks < 25) {
    cout << "F" << endl;
  } else if(marks <= 44) {
    cout << "E" << endl;
  } else if(marks <= 49) {
    cout << "D" << endl;
  } else if(marks <= 59) {
    cout << "C" << endl;
  } else if(marks <= 79) {
    cout << "B" << endl;
  } else if(marks <= 100) {
    cout << "A" << endl;
  }

  // Task 3: Job Eligibility Based on Age
  int age1;
  cout << "Enter age: ";
  cin >> age1;
  cout << age1 << endl;

  if(age1 < 18) {
    cout << "Not eligible for job";
  } else if(age1 <= 57) {
    cout << "Eligible for job";
    if(age1 >= 55) {
      cout << ", but retirement soon";
    }
  } else {
    cout << "Retirement time";
  }

  return 0;
}
```

Let me know if you'd like to expand or modify any section!