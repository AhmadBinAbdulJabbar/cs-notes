Understanding For Loop

In case you are learning DSA, you should definitely check out our free [A2Z DSA Course](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/) with videos and blogs.

**What is a For Loop and Why is it Used?**

A for loop is a **control structure** in programming that allows you to **execute a specific block of code repeatedly**. It's especially useful when you want to **perform the same task multiple times without duplicating your code**. Let's break down the essential components of a for loop:

1. **Initialization**: You declare and initialize a variable that serves as a counter. This step only happens once at the beginning.
2. **Condition**: You specify a condition that determines when the loop should stop executing.

**Increment/Decrement:** You define how the counter variable changes after each iteration.

![](https://static.takeuforward.org/wp/uploads/2023/09/for-loop1.png)

**Code:**

C++Java

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        cout << "Hey, Striver, this is the " << i << "'th iteration" << endl;
    }
    return 0;
}
```

**Output:**

Hey, Striver, this is the 1'th iteration  
Hey, Striver, this is the 2'th iteration  
Hey, Striver, this is the 3'th iteration  
Hey, Striver, this is the 4'th iteration  
Hey, Striver, this is the 5'th iteration  
Hey, Striver, this is the 6'th iteration  
Hey, Striver, this is the 7'th iteration  
Hey, Striver, this is the 8'th iteration  
Hey, Striver, this is the 9'th iteration  
Hey, Striver, this is the 10'th iteration

In this example, the loop will run ten times because it starts with i equal to 1, and the condition is met until i becomes 11 then the loop breaks. The variable i is incremented by 1 in each iteration.

![](https://static.takeuforward.org/wp/uploads/2023/09/for-loop2-1024x699.png)

![](https://static.takeuforward.org/wp/uploads/2023/09/forloop-chart-1024x774.png)

1. **Start**: The process begins at the "start" point, indicating the beginning of the loop.
2. **Initialize counter:**  In this step, the loop control variable is initialised. This typically involves assigning an initial value to the counter. Usually denoted by the variable ‘i’
3. **Condition check:** The condition for the loop is checked in this stage. If the condition is evaluated as "true," the loop continues to execute; otherwise, it terminates.
4. If the **condition is "true,"** the loop proceeds to execute the loop body and increment/decrement the counter.
5. After completing an **iteration**, the process returns to the "Condition check" step to re-evaluate the condition.
6. After executing the loop body, the **counter** is incremented or decremented. This step is crucial for **controlling the loop's termination.**
7. The loop continues to execute as long as the **condition remains "true."** Once the condition becomes "false," the loop exits.
8. After **exit from the loop**, the code below the for-loop is executed and the program moves on.

### **Nested For Loops**

Just like for loops, you can nest one for loop inside another. This concept becomes incredibly useful when you're working with **multi-dimensional data structures** like a 2-D Array or need to solve complex problems involving **multiple iterations**.

![](https://static.takeuforward.org/wp/uploads/2023/09/multidimensional-1024x540.png)

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << "i = " << i << ", j = " << j << endl;
            // Nested loop code
        }
    }
    return 0;
}
```

**Output:**

i = 0, j = 0  
i = 0, j = 1  
i = 0, j = 2  
i = 1, j = 0  
i = 1, j = 1  
i = 1, j = 2  
i = 2, j = 0  
i = 2, j = 1  
i = 2, j = 2

**Conditionals Inside For Loops**

For loops are versatile; you can include **conditional statements** (if, else if, else) within them. This allows you to execute **different code blocks based on certain conditions** during each iteration.

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        // Code for even numbers
    } else {
        // Code for odd numbers
    }
}

**Customising For Loops**

You have flexibility in how you structure your for loop. For instance, you can customise the **increment step to achieve specific patterns** or **iterate a certain number of times**.

**Code:**

C++

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 25; i += 5) {
        cout << "i = " << i << endl;
    }
    return 0;
}
```

**Output:**

i = 1  
i = 6  
i = 11  
i = 16  
i = 21

In this example, i starts at 1 and increases by 5 in each iteration, resulting in five iterations.

![](https://static.takeuforward.org/wp/uploads/2023/09/5incloop-1024x733.png)