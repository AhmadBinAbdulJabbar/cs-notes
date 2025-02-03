

## 📝 **C++ Data Types**

### 📌 **1. Overview of Data Types in C++**

Data types define the type of value a variable can hold, as well as its memory usage and range.

#### 🔹 **Common Data Types in C++**

|Data Type|Memory (bytes)|Range|
|---|---|---|
|`int`|4|`-2,147,483,648` to `2,147,483,647` (`±10⁹`)|
|`long`|4 or 8|`-2,147,483,648` to `2,147,483,647` (if 4 bytes) `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807` (if 8 bytes)|
|`long long`|8|`-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807` (`±10¹⁸`)|
|`unsigned int`|4|`0` to `4,294,967,295`|
|`unsigned long`|4 or 8|`0` to `4,294,967,295` (if 4 bytes) `0` to `18,446,744,073,709,551,615` (if 8 bytes)|
|`unsigned long long`|8|`0` to `18,446,744,073,709,551,615`|
|`float`|4|`±3.4 × 10³⁸` (7 decimal places)|
|`double`|8|`±1.8 × 10³⁰⁸` (15-16 decimal places)|
|`long double`|8, 12, or 16|`±1.2 × 10⁴⁹³²` (up to 19 decimal places)|
|`char`|1|`-128` to `127` (`0` to `255` if unsigned)|
|`bool`|1|`true (1)` or `false (0)`|
|`string`|Varies|Depends on the content|

---

### 📌 **2. Integer Data Types (`int`, `long`, `long long`, `unsigned int`)**

Used for storing whole numbers (no decimal points).

```cpp
int i = 10;
long l = 1234567891;
long long ll = 15000000000;
unsigned int ui = 4000000000; // No negative values allowed

cout << "i = " << i << endl;
cout << "l = " << l << endl;
cout << "ll = " << ll << endl;
cout << "ui = " << ui << endl;
```

👉 **Why use `unsigned`?**  
`unsigned int` doubles the positive range but doesn't allow negative values.

---

### 📌 **3. Floating-Point Data Types (`float`, `double`, `long double`)**

Used for storing decimal numbers.

```cpp
float f = 5.123456;
double d = 5.123456789;
long double ld = 5.1234567890123456789;

cout << "f = " << f << endl;
cout << "d = " << d << endl;
cout << "ld = " << ld << endl;
```

🧐 **Why is `double` also storing only 6 decimal places in your code?**  
👉 **By default, `cout` only prints up to 6 decimal places.** To see full precision:

```cpp
cout << fixed << setprecision(15) << d << endl;
cout << fixed << setprecision(18) << ld << endl;
```

🔹 **When to use which?**

- `float` → **faster** but less precise.
- `double` → **default choice** for most calculations.
- `long double` → **highest precision**, used in **scientific calculations**.

---

### 📌 **4. Boolean Data Type (`bool`)**

Stores **true/false** values.

```cpp
bool isCodingFun = true;
bool isHomeworkDone = false;

cout << "isCodingFun = " << isCodingFun << endl;  // Output: 1
cout << "isHomeworkDone = " << isHomeworkDone << endl;  // Output: 0
```

---

### 📌 **5. Character Data Type (`char`)**

Used for storing **single** characters.

```cpp
char ch1 = 'A';
char ch2;
cin >> ch2;
cout << "ch1 = " << ch1 << " and ch2 = " << ch2 << endl;
```

🔹 `char` stores ASCII values internally (e.g., `'A'` = `65` in ASCII).

👉 **To get ASCII value of a character**:

```cpp
cout << (int)ch1 << endl; // Outputs 65
```

---

### 📌 **6. String Data Type (`string`)**

Used for storing text.

#### ✅ **Taking Single-Word Input**

```cpp
string s1;
cin >> s1;  // Takes input until space
cout << s1 << endl;
```

#### ✅ **Taking Multiple Words as Input (`getline`)**

```cpp
string str;
getline(cin, str);  // Reads the whole line (including spaces)
cout << str << endl;
```

👉 **Why use `getline()`?**  
`cin` stops input at spaces, while `getline()` reads the entire line.

---

### 📌 **7. Data Type Ranges (Easiest Way to Remember)**

Instead of memorizing exact values, just **remember the powers of 10**:

|Data Type|Approximate Range|
|---|---|
|`int`|`-10⁹ to 10⁹`|
|`long long`|`-10¹⁸ to 10¹⁸`|
|`unsigned int`|`0 to 4 × 10⁹`|
|`unsigned long long`|`0 to 18 × 10¹⁸`|
|`float`|`±3.4 × 10³⁸` (7 decimal places)|
|`double`|`±1.8 × 10³⁰⁸` (15-16 decimal places)|
|`long double`|`±1.2 × 10⁴⁹³²` (up to 19 decimal places)|

👉 **Easy rules**:

- `int` → **up to** `10⁹`
- `long long` → **up to** `10¹⁸`
- `float` → **10³⁸**, `double` → **10³⁰⁸`,` long double` → **10⁴⁹³²**
- `unsigned` → **doubles the positive range** but no negatives

---

### 📌 **8. Full Code Example**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Integer types
    int i = 10;
    long l = 1234567891;
    long long ll = 15000000000;
    unsigned int ui = 4000000000;

    cout << "i = " << i << endl;
    cout << "l = " << l << endl;
    cout << "ll = " << ll << endl;
    cout << "ui = " << ui << endl;

    // Floating-point types
    float f = 5.123456;
    double d = 5.123456789;
    long double ld = 5.1234567890123456789;

    cout << "f = " << f << endl;
    cout << fixed << setprecision(15) << "d = " << d << endl;
    cout << fixed << setprecision(18) << "ld = " << ld << endl;

    // String input
    string s;
    cin.ignore();
    getline(cin, s);
    cout << "String: " << s << endl;

    // Character input
    char ch;
    cin >> ch;
    cout << "Character: " << ch << endl;

    return 0;
}
```
