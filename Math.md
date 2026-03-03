## $${\color{red} 🧮 \ Math}$$

### 🔹 Basic Operators

| Operator | Description            |
| -------- | ---------------------- |
| `+`      | Addition               |
| `-`      | Subtraction            |
| `*`      | Multiplication         |
| `/`      | Division               |
| `%`      | Modulus (remainder)    |
| `**`     | Exponentiation (power) |

```php
$sum = 5 + 3;        // 8
$mod = 10 % 3;       // 1
$pow = 2 ** 3;       // 8
```

---

### 🔹 Operator Categories

#### Arithmetic

`+  -  *  /  %  **`

```php
$result = 10 / 2;
```

#### Assignment

`=  +=  -=  *=  /=  %=  **=`

```php
$a = 5;
$a += 2;   // 7
```

#### Comparison

`==  ===  !=  !==  <  >  <=  >=  <=>`

```php
$a == $b;   // Equal (loose)
$a === $b;  // Equal (strict)
```

#### Logical

`&&  ||  !  and  or  xor`

```php
if ($a > 0 && $b > 0) {}
```

#### Increment / Decrement

`++  --`

```php
$count++;
--$count;
```

---

### 🔹 Common Math Functions

| Function         | Description                           |
| ---------------- | ------------------------------------- |
| `abs(x)`         | Absolute value                        |
| `round(x, p)`    | Round to nearest (precision optional) |
| `floor(x)`       | Round down                            |
| `ceil(x)`        | Round up                              |
| `min(a, b, ...)` | Smallest value                        |
| `max(a, b, ...)` | Largest value                         |
| `pow(x, y)`      | x to the power of y                   |
| `sqrt(x)`        | Square root                           |
| `exp(x)`         | e^x                                   |
| `log(x)`         | Natural log (base e)                  |
| `log10(x)`       | Base-10 log                           |
| `pi()`           | π (3.14159...)                        |

---

### 🔹 Random Numbers

| Function            | Description                                 |
| ------------------- | ------------------------------------------- |
| `rand(min, max)`    | Random integer                              |
| `mt_rand(min, max)` | Better random integer (faster, recommended) |
| `lcg_value()`       | Random float (0–1)                          |

```php
$random = mt_rand(1, 100);
```

---

### 🔹 Trigonometry

| Function     | Description       |
| ------------ | ----------------- |
| `sin(x)`     | Sine              |
| `cos(x)`     | Cosine            |
| `tan(x)`     | Tangent           |
| `asin(x)`    | Arcsine           |
| `acos(x)`    | Arccosine         |
| `atan(x)`    | Arctangent        |
| `deg2rad(x)` | Degrees → Radians |
| `rad2deg(x)` | Radians → Degrees |

---

### 🔹 Division & Remainders

| Function       | Description      |
| -------------- | ---------------- |
| `intdiv(a, b)` | Integer division |
| `fmod(a, b)`   | Float remainder  |

```php
intdiv(7, 2);  // 3
fmod(7, 2);    // 1
```

---

### 🔹 Number Formatting

| Function              | Description             |
| --------------------- | ----------------------- |
| `number_format(x, d)` | Format number as string |

```php
number_format(1234.567, 2); // "1,234.57"
```

---

### 🔹 Rounding Summary

| Function   | Behavior        |
| ---------- | --------------- |
| `round(x)` | Nearest integer |
| `ceil(x)`  | Always up       |
| `floor(x)` | Always down     |

