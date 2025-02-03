[[switch article]]
# **Switch Statement in C++**

The `switch` statement is a control structure used to handle multiple conditions efficiently. It is an alternative to using multiple `if-else if` statements when checking for a single variable with discrete values.

## **1. Syntax of Switch Statement**

```cpp
switch(expression) {
    case constant1:
        // Code to execute if expression == constant1
        break;
    case constant2:
        // Code to execute if expression == constant2
        break;
    ...
    default:
        // Code to execute if no cases match
}
```

- The **expression** inside `switch` must be an **integer**, **character**, or an **enumerated type**.
- Each `case` contains a **constant** value.
- The `break` statement is used to exit the `switch` block; otherwise, execution will continue into the next case (known as **fall-through** behavior).
- The `default` case executes if no `case` matches the expression.

---

## **2. Example of Switch Statement**

```cpp
#include <iostream>
using namespace std;

int main() {
    int day;
    cout << "Enter a number (1-7) for the day of the week: ";
    cin >> day;

    switch (day) {
        case 1:
            cout << "Monday";
            break;
        case 2:
            cout << "Tuesday";
            break;
        case 3:
            cout << "Wednesday";
            break;
        case 4:
            cout << "Thursday";
            break;
        case 5:
            cout << "Friday";
            break;
        case 6:
            cout << "Saturday";
            break;
        case 7:
            cout << "Sunday";
            break;
        default:
            cout << "Invalid input! Please enter a number between 1 and 7.";
    }
    cout << endl;
    return 0;
}
```

### **Output Examples**

```
Enter a number (1-7) for the day of the week: 3
Wednesday
```

```
Enter a number (1-7) for the day of the week: 8
Invalid input! Please enter a number between 1 and 7.
```

---

## **3. What Can Be Used in the Switch Expression?**

The expression inside `switch(expression)` must be one of the following:

- **An integer (`int`)** (e.g., `5`, `-3`, `10`)
- **A character (`char`)** (e.g., `'A'`, `'b'`, `'1'`)
- **An enumeration (`enum`)** (e.g., `enum Color { RED, GREEN, BLUE };`)

### **Example of Using `char` in Switch**

```cpp
char grade;
cout << "Enter your grade (A, B, C, D, F): ";
cin >> grade;

switch (grade) {
    case 'A':
        cout << "Excellent!";
        break;
    case 'B':
        cout << "Good!";
        break;
    case 'C':
        cout << "Fair!";
        break;
    case 'D':
        cout << "Pass!";
        break;
    case 'F':
        cout << "Fail!";
        break;
    default:
        cout << "Invalid grade!";
}
```

### **Valid and Invalid Expressions in Switch**

|**Expression Type**|**Valid/Invalid**|**Example**|
|---|---|---|
|Integer (`int`)|✅ Valid|`switch(5)`|
|Character (`char`)|✅ Valid|`switch('A')`|
|Enumerated (`enum`)|✅ Valid|`switch(RED)`|
|String (`string`)|❌ Invalid|`switch("Hello")`|
|Floating-point (`float`, `double`)|❌ Invalid|`switch(3.14)`|
|Boolean (`bool`)|❌ Invalid|`switch(true)`|

---

## **4. What Can Be Used in Case Constants?**

Each `case` must have a **constant expression** that evaluates to an **integer or character**.

### **Valid Case Constants**

```cpp
switch (x) {
    case 1:   // Integer constant ✅
    case 'A': // Character constant ✅
    case 10 + 5: // Constant expression ✅
}
```

### **Invalid Case Constants**

```cpp
int y = 10;
switch (x) {
    case y:  // ❌ Error! Variables are not allowed
    case 3.5: // ❌ Error! Floating-point values are not allowed
    case "hello": // ❌ Error! Strings are not allowed
}
```

- **Case labels must be constant and unique**.
- **Variables and floating-point numbers are not allowed** in `case`.

---

## **5. `break` Statement in Switch**

- The `break` statement **stops execution** and exits the `switch` block.
- Without `break`, execution **falls through** into the next case.

### **Example of Fall-Through Behavior**

```cpp
int x = 2;
switch (x) {
    case 1:
        cout << "One";
    case 2:
        cout << "Two";  // Will execute
    case 3:
        cout << "Three"; // Will also execute!
}
```

**Output:**

```
TwoThree
```

- Since there is **no `break`** after `case 2`, `case 3` also executes.
- To avoid this, always use `break` unless fall-through behavior is intentional.

---

## **6. Using `default` Case**

The `default` case is executed **when none of the `case` labels match**.

Example:

```cpp
int number;
cout << "Enter a number (1-3): ";
cin >> number;

switch (number) {
    case 1:
        cout << "You chose 1";
        break;
    case 2:
        cout << "You chose 2";
        break;
    case 3:
        cout << "You chose 3";
        break;
    default:
        cout << "Invalid choice!";
}
```

If the user enters `4`, the output will be:

```
Invalid choice!
```

- `default` is **optional** but recommended for handling unexpected inputs.

---
### **Using `enum` in a Switch Statement**

```cpp
#include <iostream>
using namespace std;

// Defining an enumeration for days of the week
enum Day { Monday = 1, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday };

int main() {
    Day today;
    int dayNumber;

    cout << "Enter a number (1-7) for the day of the week: ";
    cin >> dayNumber;

    today = static_cast<Day>(dayNumber); // Convert integer to enum

    switch (today) {
        case Monday:
            cout << "It's Monday!";
            break;
        case Tuesday:
            cout << "It's Tuesday!";
            break;
        case Wednesday:
            cout << "It's Wednesday!";
            break;
        case Thursday:
            cout << "It's Thursday!";
            break;
        case Friday:
            cout << "It's Friday!";
            break;
        case Saturday:
            cout << "It's Saturday!";
            break;
        case Sunday:
            cout << "It's Sunday!";
            break;
        default:
            cout << "Invalid input! Please enter a number between 1 and 7.";
    }

    cout << endl;
    return 0;
}
```

### **Explanation:**

- We define an **enumeration (`enum`)** `Day`, assigning values from `1` to `7` for each day.
- The user inputs a number, and we **cast it to an enum** using `static_cast<Day>(dayNumber)`.
- The `switch` statement matches the **enum constants** instead of plain integers.

---

### **Example Output**

```
Enter a number (1-7) for the day of the week: 5
It's Friday!
```

## **7. Nested Switch Statements**

A `switch` statement can be **nested inside another switch**.

Example:

```cpp
int main() {
    int mainChoice = 1, subChoice = 2;

    switch(mainChoice) {
        case 1:
            cout << "Main choice 1 selected" << endl;
            switch(subChoice) {
                case 1:
                    cout << "Sub choice 1 selected";
                    break;
                case 2:
                    cout << "Sub choice 2 selected";
                    break;
            }
            break;
        default:
            cout << "Invalid main choice";
    }
}
```

**Output:**

```
Main choice 1 selected
Sub choice 2 selected
```

---

## **8. Advantages and Disadvantages of Switch**

### **✅ Advantages**

✔ **More readable** than multiple `if-else if` statements.  
✔ **Faster execution** in some cases (uses jump tables).  
✔ **Efficient for menu-driven programs** and state-based logic.

### **❌ Disadvantages**

❌ **Only works with discrete values** (`int`, `char`, `enum`).  
❌ **Cannot handle ranges** (e.g., `case x > 10:` is invalid).  
❌ **Only allows constants**; variables are not allowed in `case`.

---

## **9. When to Use Switch vs. If-Else?**

|**Scenario**|**Use `switch`**|**Use `if-else`**|
|---|---|---|
|Checking a **single variable** for specific values|✅ Yes|❌ No|
|Handling **ranges of values** (e.g., `x > 10 && x < 20`)|❌ No|✅ Yes|
|Values are **integers or characters**|✅ Yes|✅ Yes|
|Values are **floating-point numbers or strings**|❌ No|✅ Yes|
|Complex conditions (e.g., `x > y && y < z`)|❌ No|✅ Yes|

---

