While Loops in Programming

In case you are learning DSA, you should definitely check out our free [A2Z DSA Course](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/) with videos and blogs.

In the world of computer programming, loops are invaluable tools that allow us to execute a block of **code repeatedly** until a **certain condition is met**. One such loop is the "while" loop.

A while loop follows a simple sequence of steps:

1. **Evaluation of Test Expression:** The loop begins by evaluating a test expression.
2. **Condition Check:** If the test expression is true, the code inside the loop's body is executed.
3. **Re-evaluation:** After executing the code, the test expression is evaluated again.

**Continuation or Termination:** This process continues until the test expression becomes false, at which point the while loop terminates.

**Syntax**

while (condition) {
    // body of the loop
}

A **while loop** is a control structure in programming that **repeatedly executes a block** of code as long as a specified **condition remains true**. A "while" loop will not execute the code at all if the **initial condition** is false. It relies on the condition being true from the outset for any code execution to occur.

![](https://static.takeuforward.org/wp/uploads/2023/09/while-loop.png)

While loops can be best illustrated with the practical example of finding the **Factorial**. Factorial of a number 'n' is the product of all positive integers from 1 to 'n'. To compute this using a while loop, we initialise a **factorial variable to 1** and repeatedly **multiply it by 'n'** while **decrementing 'n' until 'n' becomes 0**. This ensures that we calculate the factorial correctly.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 5;
    int factorial = 1;

    while (n > 0) {
        factorial *= n;
        n--;
    }

    cout << "Factorial of 5 is: " << factorial << endl;

    return 0;
}
```

**Output:**

Factorial of 5 is: 120

While loops are particularly useful when you need to ensure that a block of code executes **only when the condition is satisfied** as it terminates as soon as that **condition becomes false**. This can be vital for tasks like **validating user input** or **processing data until a specific condition is met**. By checking the condition at the beginning of the loop, you can control whether the loop body is executed or not.

**Termination Conditions:**

In algorithm design, it's essential to define clear and well-defined termination conditions for while loops. The termination condition specifies when the loop should stop executing. Without proper termination conditions, a while loop can run indefinitely, leading to what's known as an "infinite loop." Infinite loops can crash programs and consume excessive system resources, making them a critical issue to avoid.

It's crucial to define clear termination conditions for while loops in algorithms to prevent infinite loops. Termination conditions ensure that the loop will eventually exit, making the algorithm correct and efficient.

**Optimisation:**

Optimising while loops involves making them more efficient by minimising unnecessary iterations. One common optimization technique is to use loop control statements like break or continue within the loop body.

**break:** It allows you to exit the loop prematurely, even before the termination condition is met. For example, if you're searching for a value in an array, once you find it, you can break out of the loop instead of continuing to search through the remaining elements.

**continue**: It skips the current iteration of the loop and moves to the next one. This can be useful when you want to skip certain elements or avoid executing some code under specific conditions.

By using these control statements judiciously, you can reduce the number of iterations, which can significantly improve the efficiency of your algorithm.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int numbers[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int target = 6;

    // Using 'break' to exit the loop early when the target is found
    for (int num : numbers) {
        if (num == target) {
            cout << "Target found: " << target << endl;
            break; // Exit the loop immediately
        }
        cout << "Checking: " << num << endl;
    }

    // Using 'continue' to skip specific elements
    for (int num : numbers) {
        if (num % 2 == 0) {
            continue; // Skip even numbers
        }
        cout << "Odd number: " << num << endl;
    }

    return 0;
}
```

**Output:**

Checking: 1  
Checking: 2  
Checking: 3  
Checking: 4  
Checking: 5  
Target found: 6  
Odd number: 1  
Odd number: 3  
Odd number: 5  
Odd number: 7  
Odd number: 9

- The first loop uses **break** to **exit the loop immediately** when the target value is found, **preventing unnecessary iterations.**
- The second loop uses **continue** to **skip even numbers**, so only odd numbers are printed, **avoiding the execution of code** for even numbers.