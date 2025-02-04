Switch Case Statements


In case you are learning DSA, you should definitely check out our free [A2Z DSA Course](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/) with videos and blogs.

If-else statements are like the Swiss Army knife of decision-making. They offer flexibility and can handle a wide range of conditions and branching logic. You can use them when you need to **evaluate complex conditions** or when **conditions aren't based on simple equality checks**. If-else statements are often the preferred choice for scenarios where the **conditions are not easily enumerable** or where you need to execute different blocks of code based on various conditions.  
On the other hand, **switch statements shine when you have a single variable to compare against multiple distinct values**. They are concise, making the code cleaner and more structured. So, if-else statements and switch statements can complement each other, with if-else statements handling complex conditions and switch statements simplifying cases with multiple exact matches.

**The ‘Switch’ Statement**

![](https://static.takeuforward.org/wp/uploads/2023/09/switch-case.png)

To illustrate the switch statement, let's consider a common problem: given a number between 1 and 7, print the corresponding day of the week. Here's how we can use the switch statement for this task:

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 4;

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
            cout << "Invalid";
    }

    return 0;
}
```

**Output:** Thursday

In this example, if you set the **day** variable to 4, it will print "**Thursday**" since it matches the case 4 statement. The **break statement is crucial**; it ensures that the switch statement exits after the matching case is executed, preventing the execution of subsequent cases.

**The Default Case:** The default case serves as a **safety net**. If **none of the cases match** the expression, the code inside the **default block will execute**. In our example, if you input a number outside the range of 1 to 7, it will print "Invalid."

Key Considerations for Switch Case Statements:

- **Requirement for a Constant Expression  
    **A switch statement necessitates that its expression results in a constant value. This can include constants and arithmetic operations.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    const int x = 10;
    const int y = 5;

    switch (x + y) {
        case 15:
            cout << "Result is 15." << endl;
            break;
        case 20:
            cout << "Result is 20." << endl;
            break;
        default:
            cout << "No match found." << endl;
    }

    return 0;
}
```

**Output:** Result is 15.

- **Limited to Integer or Character Types**  
    Switch statements are exclusively designed to handle integer or character values. Ensure that the expression provides values of type int or char.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    char grade = 'B';

    switch (grade) {
        case 'A':
            cout << "Excellent!" << endl;
            break;
        case 'B':
            cout << "Good!" << endl;
            break;
        default:
            cout << "Not specified." << endl;
    }

    return 0;
}
```

**Output:** Good!

- **Significance of the 'Break' Keyword  
    **The 'break' keyword holds significant importance within switch cases. It serves as an exit mechanism from the switch statement. Its omission implies the execution of all subsequent cases.  
    
- **Optional Default Case  
    **Optionally, you can include a 'default' case, which executes when none of the case values match. It's not obligatory and can be excluded if not needed.

3. **Prohibition of Duplicate Case Values**Within a switch statement in C++, duplicates of case values are disallowed. Each case value must be distinct.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 2;

    switch (day) {
        case 1:
            cout << "Monday." << endl;
            break;
        case 2:
            cout << "Tuesday." << endl;
            break;
        case 2:  // Duplicate case, not allowed
            cout << "Duplicate case." << endl;
            break;
        default:
            cout << "Invalid day." << endl;
    }
    return 0;
}
```

- **Potential for Nested Switch Statements  
    **While it's possible to nest one switch statement inside another in C++, this practice is generally discouraged due to its potential to introduce complexity and hinder code readability.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 2;
    int y = 3;

    switch (x) {
        case 1:
            cout << "x is 1." << endl;
            switch (y) {
                case 1:
                    cout << "y is 1." << endl;
                    break;
                default:
                    cout << "y is not 1." << endl;
            }
            break;
        default:
            cout << "x is not 1." << endl;
    }

    return 0;
}
```