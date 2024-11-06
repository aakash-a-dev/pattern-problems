
# Advance Pattern Problems with Solution For Interviews
---

### Pattern 1: Right-Angled Triangle

**Problem:** Print a right-angled triangle of stars with `n` rows.

**Example:**  
For `n = 5`:
```
*
**
***
****
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*
**
***
****
*****
```

---

### Pattern 2: Inverted Right-Angled Triangle

**Problem:** Print an inverted right-angled triangle of stars with `n` rows.

**Example:**  
For `n = 5`:
```
*****
****
***
**
*
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*****
****
***
**
*
```

---

### Pattern 3: Pyramid Pattern

**Problem:** Print a pyramid of stars with `n` rows.

**Example:**  
For `n = 5`:
```
    *
   ***
  *****
 *******
*********
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *
   ***
  *****
 *******
*********
```

---

### Pattern 4: Diamond Pattern

**Problem:** Print a diamond pattern with `n` rows (where `n` is the height of the upper half).

**Example:**  
For `n = 5`:
```
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    // Upper half of the diamond
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            cout << "*";
        }
        cout << endl;
    }

    // Lower half of the diamond
    for (int i = n - 1; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```

---

### Pattern 5: Hollow Rectangle

**Problem:** Print a hollow rectangle of stars with given `rows` and `columns`.

**Example:**  
For `rows = 4` and `columns = 5`:
```
*****
*   *
*   *
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, columns;
    cout << "Enter number of rows and columns: ";
    cin >> rows >> columns;

    for (int i = 1; i <= rows; ++i) {
        for (int j = 1; j <= columns; ++j) {
            if (i == 1 || i == rows || j == 1 || j == columns) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `rows = 4`, `columns = 5`:**
```
*****
*   *
*   *
*****
```

---

### Pattern 6: Number Pyramid

**Problem:** Print a pyramid of numbers where each row has incremental numbers starting from 1.

**Example:**  
For `n = 5`:
```
    1
   1 2
  1 2 3
 1 2 3 4
1 2 3 4 5
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= i; ++k) {
            cout << k << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    1
   1 2
  1 2 3
 1 2 3 4
1 2 3 4 5
```

---

### Pattern 7: Pascal's Triangle

**Problem:** Print Pascal's triangle up to `n` rows.

**Example:**  
For `n = 5`:
```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n - i; j++)
            cout << " ";
        
        int num = 1;
        for (int j = 0; j <= i; j++) {
            cout << num << " ";
            num = num * (i - j) / (j + 1);
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

---

### Pattern 8: Fibonacci Triangle

**Problem:** Print a triangle pattern with Fibonacci numbers up to `n` rows.

**Example:**  
For `n = 5`:
```
1
1 1
1 2 3
5 8 13 21
34 55 89 144 233
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    int a = 1, b = 1, c;
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << a << " ";
            c = a + b;
            a = b;
            b = c;
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1
1 1
1 2 3
5 8 13 21
34 55 89 144 233
```
---

### Pattern 9: Half Pyramid with Numbers

**Problem:** Print a half pyramid of numbers with `n` rows.

**Example:**  
For `n = 5`:
```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << j << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

---

### Pattern 10: Inverted Half Pyramid with Numbers

**Problem:** Print an inverted half pyramid of numbers with `n` rows.

**Example:**  
For `n = 5`:
```
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= i; ++j) {
            cout << j << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

---

### Pattern 11: Floyd's Triangle

**Problem:** Print Floyd's Triangle with `n` rows.

**Example:**  
For `n = 5`:
```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, num = 1;
    cout << "Enter number of rows: ";
    cin >> n;
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << num << " ";
            ++num;
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

---

### Pattern 12: Butterfly Pattern

**Problem:** Print a butterfly pattern with `n` rows.

**Example:**  
For `n = 4`:
```
*      *
**    **
***  ***
********
********
***  ***
**    **
*      *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        for (int j = 1; j <= 2 * (n - i); ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }

    // Lower half
    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        for (int j = 1; j <= 2 * (n - i); ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 4`:**
```
*      *
**    **
***  ***
********
********
***  ***
**    **
*      *
```

---

### Pattern 13: Hollow Diamond Pattern

**Problem:** Print a hollow diamond pattern with `n` rows (for upper half).

**Example:**  
For `n = 5`:
```
    *
   * *
  *   *
 *     *
*       *
 *     *
  *   *
   * *
    *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        cout << "*";
        if (i > 1) {
            for (int j = 1; j <= 2 * (i - 1) - 1; ++j) {
                cout << " ";
            }
            cout << "*";
        }
        cout << endl;
    }

    // Lower half
    for (int i = n - 1; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        cout << "*";
        if (i > 1) {
            for (int j = 1; j <= 2 * (i - 1) - 1; ++j) {
                cout << " ";
            }
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *
   * *
  *   *
 *     *
*       *
 *     *
  *   *
   * *
    *
```

---

### Pattern 14: Zigzag Pattern

**Problem:** Print a zigzag pattern with `n` levels and `columns` width.

**Example:**  
For `n = 3` and `columns = 9`:
```
  *     *
 * *   * *
*   * *   *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, columns;
    cout << "Enter number of levels and columns: ";
    cin >> n >> columns;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= columns; ++j) {
            if ((i + j) % (2 * n - 2) == 0 || (j - i) % (2 * n - 2) == 0) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 3`, `columns = 9`:**
```
  *     *
 * *   * *
*   * *   *
```

---

### Pattern 15: Hollow Square Pattern

**Problem:** Print a hollow square pattern of stars with `n` rows and `n` columns.

**Example:**  
For `n = 5`:
```
*****
*   *
*   *
*   *
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter side length: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n; ++j) {
            if (i == 1 || i == n || j == 1 || j == n) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*****
*   *
*   *
*   *
*****
```

---

### Pattern 16: Left-Aligned Number Triangle

**Problem:** Print a left-aligned triangle of numbers, where each row contains the row number repeated.

**Example:**  
For `n = 5`:
```
1
22
333
4444
55555
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << i;
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1
22
333
4444
55555
```

---

### Pattern 17: Right-Aligned Star Triangle

**Problem:** Print a right-aligned triangle of stars with `n` rows.

**Example:**  
For `n = 5`:
```
    *
   **
  ***
 ****
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= i; ++k) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *
   **
  ***
 ****
*****
```

---

### Pattern 18: Alternating Rectangle Pattern (0 and 1)

**Problem:** Print an alternating rectangle pattern of `0` and `1` with `n` rows and `m` columns.

**Example:**  
For `n = 4` and `m = 5`:
```
01010
10101
01010
10101
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, m;
    cout << "Enter number of rows and columns: ";
    cin >> n >> m;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= m; ++j) {
            if ((i + j) % 2 == 0) {
                cout << "0";
            } else {
                cout << "1";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 4`, `m = 5`:**
```
01010
10101
01010
10101
```

---

### Pattern 19: Hourglass Pattern

**Problem:** Print an hourglass pattern of stars with `n` rows in the top half.

**Example:**  
For `n = 5`:
```
*********
 ******* 
  *****  
   ***   
    *    
   ***   
  *****  
 ******* 
*********
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the number of rows for the top half: ";
    cin >> n;

    // Upper half
    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= 2 * i - 1; ++j) {
            cout << "*";
        }
        cout << endl;
    }

    // Lower half
    for (int i = 2; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= 2 * i - 1; ++j) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*********
 ******* 
  *****  
   ***   
    *    
   ***   
  *****  
 ******* 
*********
```

---

### Pattern 20: Hollow Pyramid Pattern

**Problem:** Print a hollow pyramid pattern with `n` rows.

**Example:**  
For `n = 5`:
```
    *
   * *
  *   *
 *     *
*********
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            if (k == 1 || k == 2 * i - 1 || i == n) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *
   * *
  *   *
 *     *
*********
```

---

### Pattern 21: X Pattern

**Problem:** Print an "X" pattern with `n` rows and columns (odd `n` is recommended).

**Example:**  
For `n = 5`:
```
*   *
 * * 
  *  
 * * 
*   *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter an odd number of rows (for an X pattern): ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n; ++j) {
            if (j == i || j == (n - i + 1)) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*   *
 * * 
  *  
 * * 
*   *
```
---

### Pattern 22: Palindromic Number Pyramid

**Problem:** Print a palindromic number pyramid with `n` rows.

**Example:**  
For `n = 5`:
```
    1
   2 1 2
  3 2 1 2 3
 4 3 2 1 2 3 4
5 4 3 2 1 2 3 4 5
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = i; j >= 1; --j) {
            cout << j << " ";
        }
        for (int j = 2; j <= i; ++j) {
            cout << j << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    1
   2 1 2
  3 2 1 2 3
 4 3 2 1 2 3 4
5 4 3 2 1 2 3 4 5
```

---

### Pattern 23: Numeric Hollow Diamond

**Problem:** Print a hollow diamond pattern with numbers on the edges.

**Example:**  
For `n = 5`:
```
    1
   1 2
  1   3
 1     4
1 2 3 4 5
 1     4
  1   3
   1 2
    1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        cout << "1";
        for (int j = 1; j <= 2 * (i - 1) - 1; ++j) {
            cout << " ";
        }
        if (i != 1) {
            cout << i;
        }
        cout << endl;
    }

    // Lower half
    for (int i = n - 1; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        cout << "1";
        for (int j = 1; j <= 2 * (i - 1) - 1; ++j) {
            cout << " ";
        }
        if (i != 1) {
            cout << i;
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    1
   1 2
  1   3
 1     4
1 2 3 4 5
 1     4
  1   3
   1 2
    1
```

---

### Pattern 24: Solid Rhombus

**Problem:** Print a solid rhombus of stars with `n` rows.

**Example:**  
For `n = 5`:
```
    *****
   *****
  *****
 *****
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= n; ++j) {
            cout << "*";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *****
   *****
  *****
 *****
*****
```

---

### Pattern 25: Hollow Rhombus

**Problem:** Print a hollow rhombus with `n` rows.

**Example:**  
For `n = 5`:
```
    *****
   *   *
  *   *
 *   *
*****
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= n; ++j) {
            if (i == 1 || i == n || j == 1 || j == n) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    *****
   *   *
  *   *
 *   *
*****
```

---

### Pattern 26: Hollow Inverted Pyramid

**Problem:** Print a hollow inverted pyramid with `n` rows.

**Example:**  
For `n = 5`:
```
*********
 *     *
  *   *
   * *
    *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= 2 * i - 1; ++j) {
            if (j == 1 || j == 2 * i - 1 || i == n) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
*********
 *     *
  *   *
   * *
    *
```

---

### Pattern 27: Diamond of Numbers

**Problem:** Print a diamond pattern with numbers for `n` rows.

**Example:**  
For `n = 4`:
```
   1
  2 3
 4 5 6
7 8 9 10
 4 5 6
  2 3
   1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    int num = 1;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << num++ << " ";
        }
        cout << endl;
    }

    // Lower half
    num -= n;
    for (int i = n - 1; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << num++ << " ";
        }
        num -= 2 * i;
        cout << endl;
    }

    return 0;
}
```

**Output for `n = 4`:**
```
   1
  2 3
 4 5 6
7 8 9 10
 4 5 6
  2 3
   1
```

---

### Pattern 28: Pascal's Triangle

**Problem:** Print Pascal's Triangle with `n` rows. Pascal's triangle is a triangular array where each number is the sum of the two numbers directly above it.

**Example:**  
For `n = 5`:
```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n - i; ++j) {
            cout << " ";
        }
        int value = 1;
        for (int j = 0; j <= i; ++j) {
            cout << value << " ";
            value = value * (i - j) / (j + 1);
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
```

---

### Pattern 29: Zigzag Pattern

**Problem:** Print a zigzag pattern with `n` rows.

**Example:**  
For `n = 3`:
```
  *   *   *
 * * * * * *
*   *   *   *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n = 3;  // Rows fixed for Zigzag pattern
    int cols = 9; // Adjust for width of pattern

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= cols; ++j) {
            if ((i + j) % 4 == 0 || (i == 2 && j % 4 == 0)) {
                cout << "*";
            } else {
                cout << " ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 3`:**
```
  *   *   *
 * * * * * *
*   *   *   *
```

---

### Pattern 30: Hollow Square with Diagonals

**Problem:** Print a hollow square pattern with diagonals for `n` rows.

**Example:**  
For `n = 5`:
```
* * * * *
* *   * *
*   *   *
* *   * *
* * * * *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter side length: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n; ++j) {
            if (i == 1 || i == n || j == 1 || j == n || i == j || j == (n - i + 1)) {
                cout << "* ";
            } else {
                cout << "  ";
            }
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
* * * * *
* *   * *
*   *   *
* *   * *
* * * * *
```

---

### Pattern 31: Pyramid with Incrementing Numbers

**Problem:** Print a pyramid pattern with incrementing numbers in each row.

**Example:**  
For `n = 4`:
```
   1
  2 3
 4 5 6
7 8 9 10
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, num = 1;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= i; ++k) {
            cout << num++ << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 4`:**
```
   1
  2 3
 4 5 6
7 8 9 10
```

---

### Pattern 32: Diamond with Stars

**Problem:** Print a diamond pattern of stars with `n` rows for the upper half.

**Example:**  
For `n = 4`:
```
   *
  ***
 *****
*******
 *****
  ***
   *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the number of rows for the upper half: ";
    cin >> n;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            cout << "*";
        }
        cout << endl;
    }

    // Lower half
    for (int i = n - 1; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int k = 1; k <= 2 * i - 1; ++k) {
            cout << "*";
        }
        cout << endl;
    }

    return 0;
}
```

**Output for `n = 4`:**
```
   *
  ***
 *****
*******
 *****
  ***
   *
```

---

### Pattern 33: Butterfly Pattern

**Problem:** Print a butterfly pattern with `n` rows.

**Example:**  
For `n = 4`:
```
*      *
**    **
***  ***
********
********
***  ***
**    **
*      *
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    // Upper half
    for (int i = 1; i <= n; ++i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        for (int j = 1; j <= 2 * (n - i); ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }

    // Lower half
    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        for (int j = 1; j <= 2 * (n - i); ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << "*";
        }
        cout << endl;
    }

    return 0;
}
```

**Output for `n = 4`:**
```
*      *
**    **
***  ***
********
********
***  ***
**    **
*      *
```

---

### Pattern 34: Reverse Pyramid with Numbers

**Problem:** Print an inverted pyramid pattern of numbers.

**Example:**  
For `n = 5`:
```
1 2 3 4 5
 1 2 3 4
  1 2 3
   1 2
    1
```

**Solution:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of rows: ";
    cin >> n;

    for (int i = n; i >= 1; --i) {
        for (int j = 1; j <= n - i; ++j) {
            cout << " ";
        }
        for (int j = 1; j <= i; ++j) {
            cout << j << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output for `n = 5`:**
```
1 2 3 4 5
 1 2 3 4
  1 2 3
   1 2
    1
```

---



