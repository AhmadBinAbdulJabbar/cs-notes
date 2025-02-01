# C++ Basic Input/Output

## Including Libraries
C++ is a versatile language, and it relies on libraries to access various functionalities. To perform tasks like input and output, we include specific libraries at the beginning of our code. For instance, `#include<iostream>` is used for input and output operations, while `#include<math.h>` allows us to use mathematical functions.

## The Generic Skeleton
The generic skeleton of a C++ program consists of two main components: the library inclusion and the main function.

```cpp
#include<iostream>

int main() {
    // Your code here
    return 0;
}
```

## Output with `cout`
To display output in C++, you'll commonly use the `cout` function from the `iostream` library. 

```cpp
#include<iostream>

int main() {
    std::cout << "Hey, Striver!";
    return 0;
}
```
**Output:**
```
Hey, Striver!
```

### Using `\n` for Line Breaks
```cpp
#include<iostream>

int main() {
    std::cout << "Hey, Striver!" << "\n";
    std::cout << "Hey, Striver!";
    return 0;
}
```
**Output:**
```
Hey, Striver!

Hey, Striver!
```

### Using `std::endl` for Line Breaks
```cpp
#include<iostream>

int main() {
    std::cout << "Hey, Striver!" << std::endl;
    std::cout << "Hey, Striver!";
    return 0;
}
```
**Output:**
```
Hey, Striver!

Hey, Striver!
```

`\n` is typically faster than `std::endl` because `std::endl` flushes the output buffer, which can be a costly operation in terms of performance.

## Using `namespace std`
By adding `using namespace std;`, you can avoid writing `std::` before `cout` and `cin`.

```cpp
#include<iostream>
using namespace std;

int main() {
    cout << "Hey, Striver!" << endl;
    cout << "Hey, Striver!";
    return 0;
}
```

## Taking User Input using `cin`
User input can be taken using `cin`:

```cpp
#include<iostream>
using namespace std;

int main() {
    int x;
    cin >> x;
    cout << "Value of x: " << x;
    return 0;
}
```
**Input:**
```
10
```
**Output:**
```
Value of x: 10
```

### Taking Multiple Inputs
```cpp
#include<iostream>
using namespace std;

int main() {
    int x, y;
    cin >> x >> y;
    cout << "Value of x: " << x << " and y: " << y;
    return 0;
}
```
**Input:**
```
10 20
```
**Output:**
```
Value of x: 10 and y: 20
```

## Using `#include<bits/stdc++.h>`
To include almost all standard libraries at once, you can use `#include<bits/stdc++.h>`. 

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    int x, y;
    cin >> x >> y;
    cout << "Value of x: " << x << " and y: " << y;
    return 0;
}
```
**Input:**
```
10 20
```
**Output:**
```
Value of x: 10 and y: 20
```


