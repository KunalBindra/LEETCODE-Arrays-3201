# LEETCODE-Arrays-3201
### 🧪 Let's Dry Run with Example:

```java
nums = {2, 4, 3, 1, 6, 8, 7}
```

#### Step 1: Count Even and Odd

```java
int counteven = 0;
int oddcount = 0;
```

Iterating through `nums`:

| c (nums\[i]) | c % 2 == 0? | counteven | oddcount |
| ------------ | ----------- | --------- | -------- |
| 2            | Yes         | 1         | 0        |
| 4            | Yes         | 2         | 0        |
| 3            | No          | 2         | 1        |
| 1            | No          | 2         | 2        |
| 6            | Yes         | 3         | 2        |
| 8            | Yes         | 4         | 2        |
| 7            | No          | 4         | 3        |

👉 After this loop:

```java
counteven = 4
oddcount = 3
```

---

#### Step 2: Count Alternating Parity Changes

```java
int count = 1;
int prevparity = nums[0] % 2; // 2 % 2 = 0 (even)
```

Loop from index `i = 1` to end:

| i | nums\[i] | currparity | prevparity | currparity != prevparity? | count | update prevparity |
| - | -------- | ---------- | ---------- | ------------------------- | ----- | ----------------- |
| 1 | 4        | 0          | 0          | No                        | 1     | No                |
| 2 | 3        | 1          | 0          | Yes                       | 2     | 1                 |
| 3 | 1        | 1          | 1          | No                        | 2     | No                |
| 4 | 6        | 0          | 1          | Yes                       | 3     | 0                 |
| 5 | 8        | 0          | 0          | No                        | 3     | No                |
| 6 | 7        | 1          | 0          | Yes                       | 4     | 1                 |

👉 After this loop:

```java
count = 4 // Number of parity switches (thus, max alternating parity segment length)
```

---

### Step 3: Final Result

```java
return Math.max(Math.max(counteven, oddcount), count)
= Math.max(Math.max(4, 3), 4)
= Math.max(4, 4)
= 4
```

---

### ✅ Final Output:

```java
maximumLength({2, 4, 3, 1, 6, 8, 7}) = 4
```

---

### 📌 Summary:

* **counteven**: total even numbers
* **oddcount**: total odd numbers
* **count**: length of the longest alternating even/odd sequence
* The function returns the **maximum** of these three.
