# **📌 Strings in C++ (Basics)**

A **string** in C++ is a sequence of characters used to store and manipulate text. C++ provides two main ways to handle strings:

1. **C-Style Strings** (Character Arrays)
2. **std::string Class** (Preferred, from the `<string>` library)

---

# **1️⃣ C-Style Strings (Character Arrays)**

A **C-style string** is an array of characters **terminated by a null character (`\0`)**.

### **✅ Declaring and Initializing C-Style Strings**

```cpp
char str1[] = "Hello";  // Automatically adds '\0' at the end
char str2[6] = "World"; // Explicit size (5 chars + '\0')
char str3[] = {'H', 'i', '\0'}; // Manual null termination
```

### **✅ Taking Input for C-Style Strings**

```cpp
char name[20];
cin >> name;  // Takes input until space (stops at whitespace)
cout << name;
```

💡 **Problem:** `cin` stops at spaces, so `"John Doe"` would only take `"John"`.

### **✅ Using `cin.getline()` for Multi-Word Input**

```cpp
char name[20];
cin.getline(name, 20); // Takes input with spaces
cout << name;
```

### **✅ Printing a C-Style String**

```cpp
char greet[] = "Hello";
cout << greet; // Outputs: Hello
```

---

# **2️⃣ `std::string` Class (Recommended)**

The **C++ Standard Library (`std::string`)** makes string handling easier.

### **✅ Declaring and Initializing a `std::string`**

```cpp
string s1 = "Ahmad";
string s2("Hello");
string s3;
s3 = "World";
```

### **✅ Taking Input for Strings**

```cpp
string name;
cin >> name;  // Stops at space
cout << name;
```

💡 **For multi-word input, use `getline()`**

```cpp
string fullName;
getline(cin, fullName);
cout << fullName;
```

---

## **🔹 String Operations in C++**

C++ `std::string` provides several useful operations.

### **✅ Finding String Length**

```cpp
string s = "Ahmad";
cout << s.length();  // Outputs: 5
```

or

```cpp
cout << s.size();  // Also gives 5
```

### **✅ Accessing Characters (Indexing)**

```cpp
cout << s[0];  // 'A'
cout << s[3];  // 'a'
```

### **✅ Modifying a Character**

```cpp
s[4] = 'a';
cout << s; // Outputs: "Ahmaa"
```

### **✅ Concatenation (Joining Strings)**

```cpp
string first = "Hello";
string second = " World";
string result = first + second;  // "Hello World"
cout << result;
```

### **✅ Comparing Strings**

```cpp
string a = "apple";
string b = "banana";
if (a == b)
    cout << "Equal";
else
    cout << "Not Equal"; // Outputs: Not Equal
```

### **✅ Extracting a Substring**

```cpp
string s = "Ahmad Jabbar";
cout << s.substr(6, 6); // Outputs: "Jabbar"
```

🔹 **Syntax:** `s.substr(start_index, length)`

### **✅ Searching in a String**

```cpp
string s = "programming";
cout << s.find("gram"); // Outputs: 3 (index of "g")
```

🔹 **Returns** the starting index of the substring.

---

# **📌 Example Code for String Basics**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "Ahmad";  // Declare a string
    int len = s.length(); // Get the length of the string

    // Access last character
    cout << "Last character: " << s[len - 1] << endl;

    // Modify the last character
    s[len - 1] = 'a';
    cout << "Modified string: " << s << endl;

    // String concatenation
    string name = "Hello";
    string greet = name + " Ahmad";
    cout << "Concatenated string: " << greet << endl;

    // Taking full sentence input
    string fullName;
    cout << "Enter your full name: ";
    getline(cin, fullName);
    cout << "Your name is: " << fullName << endl;

    return 0;
}
```

---

## **🔹 Key Takeaways**

✔ **C-style strings (`char array`) need `\0` termination**  
✔ **Prefer `std::string` over C-style strings** for flexibility  
✔ **Use `getline(cin, str)` for multi-word input**  
✔ **Strings are mutable (characters can be modified using `s[i] = 'x'`)**  
✔ **Use `.length()` or `.size()` to find string length**  
✔ **Concatenation is done using `+` operator**  
✔ **Use `.substr(start, length)` for substring extraction**  
✔ **Use `.find("word")` to search within a string**
