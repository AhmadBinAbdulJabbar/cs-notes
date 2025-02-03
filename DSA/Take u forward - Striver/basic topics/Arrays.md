
# **📌 Arrays in C++**

An **array** is a collection of elements of the **same data type**, stored in **contiguous memory locations**. It allows us to efficiently store and manipulate multiple values using a **single variable name**.

---

## **🔹 Declaring and Initializing an Array**

Syntax for declaring an array:

```cpp
dataType arrayName[size];
```

Example:

```cpp
int arr[5]; // Declares an integer array of size 5
```

💡 If not initialized, an array contains **garbage values** (random memory values).

---

### **✅ Initializing an Array**

We can initialize an array in multiple ways:

1️⃣ **At declaration**

```cpp
int arr[5] = {10, 20, 30, 40, 50}; 
```

2️⃣ **Partial initialization** (remaining values default to 0)

```cpp
int arr[5] = {1, 2}; // arr = {1, 2, 0, 0, 0}
```

3️⃣ **Omitting size (determined automatically)**

```cpp
int arr[] = {1, 2, 3, 4, 5}; // Size is inferred as 5
```

---

## **🔹 Accessing and Modifying Array Elements**

Array elements are accessed using their **index** (zero-based).

```cpp
int arr[3] = {5, 10, 15};
cout << arr[0]; // Outputs: 5
cout << arr[2]; // Outputs: 15
```

### **Modifying Elements**

```cpp
arr[1] = 20; // Changes value at index 1 to 20
cout << arr[1]; // Outputs: 20
```

💡 **Arrays are mutable**, meaning their elements can be changed after initialization.

---

## **🔹 Input and Output in Arrays**

Taking input for an array:

```cpp
int arr[5];
cin >> arr[0] >> arr[1] >> arr[2] >> arr[3] >> arr[4];
```

Printing an array:

```cpp
cout << arr[3]; // Prints the value at index 3
```

### **💡 Using Loops for Input & Output**

Instead of manually accessing elements, we use loops:

```cpp
int arr[5];

// Taking input
for (int i = 0; i < 5; i++) {
    cin >> arr[i];
}

// Printing output
for (int i = 0; i < 5; i++) {
    cout << arr[i] << " ";
}
```

💡 **Using loops reduces redundancy and improves efficiency!**

---

## **🔹 Array Size & Memory Considerations**

- The size of an array **must be a constant expression**.
- Array elements are stored **contiguously** in memory.
- If we **access an index out of bounds**, we get **undefined behavior**.

```cpp
int arr[5];
arr[5] = 10; // ❌ ERROR! Index 5 is out of bounds (valid indices: 0 to 4)
```

---

# **📌 2D Arrays in C++**

A **2D array** is an array of arrays (like a matrix).

### **✅ Declaring a 2D Array**

```cpp
dataType arrayName[rows][columns];
```

Example:

```cpp
int arr2D[2][3]; // 2 rows, 3 columns
```

### **✅ Initializing a 2D Array**

```cpp
int arr2D[2][3] = { {1, 2, 3}, {4, 5, 6} };
```

This represents:

```
1  2  3
4  5  6
```

💡 **Accessing elements:**

```cpp
cout << arr2D[1][2]; // Outputs: 6 (row index = 1, column index = 2)
```

💡 **Looping through a 2D array:**

```cpp
for(int i = 0; i < 2; i++) {
    for(int j = 0; j < 3; j++) {
        cout << arr2D[i][j] << " ";
    }
    cout << endl;
}
```

---

## **🔹 Key Points About Arrays**

✔ **Fixed Size:** Size of an array must be specified at declaration.  
✔ **Zero-Based Indexing:** First element is at index `0`, last at `size - 1`.  
✔ **Contiguous Memory:** Elements are stored in adjacent memory locations.  
✔ **Mutable:** Elements of an array can be modified.  
✔ **Garbage Values:** If not initialized, an array may contain random values.  
✔ **Out of Bounds Access:** Accessing an invalid index leads to **undefined behavior**.

---

# **📌 Your Code (With Fixes & Explanation)**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Declare an integer array of size 5
    int arr[5];

    // Taking input for the array
    cin >> arr[0] >> arr[1] >> arr[2] >> arr[3] >> arr[4];

    // Outputting a specific element
    cout << arr[3] << endl;

    // Display and modify the last element
    cout << "arr[4] = " << arr[4] << endl;
    arr[4] = 12; // Arrays are mutable
    cout << "arr[4] = " << arr[4] << endl;

    // Declaring and initializing a 2D array
    int arr2D[2][3] = { {1, 2, 3}, {4, 5, 6} };

    // Accessing a 2D array element
    cout << arr2D[1][2] << endl; // Outputs: 6

    // Accessing an out-of-bounds index (Fixed)
    // arr[5] = 10; // ❌ ERROR! Index 5 does not exist

    return 0;
}
```

---
