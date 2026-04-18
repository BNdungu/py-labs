# Task 03c — Conditionals Challenge

## What you need to know
- `if`, `elif`, `else`
- Boolean operators: `and`, `or`, `not`
- Comparison operators: `>`, `<`, `==`, `!=`, `>=`, `<=`

---

## Your Task

### Part A — Age Category
Write a program that asks the user to enter their **age**.
Print the matching category:
- Below 0 or above 120 → `"Invalid age."`
- 0 to 12 → `"Child"`
- 13 to 17 → `"Teenager"`
- 18 to 64 → `"Adult"`
- 65 and above → `"Senior"`

### Example output (Part A)
```
Enter your age: 16
Teenager
```
```
Enter your age: -3
Invalid age.
```

---

### Part B — Cinema Ticket Price
Write a program that asks for the user's **age** and whether it is a **weekday or weekend** (`weekday` / `weekend`).

Use this pricing:
- Child (0–12): `3` on weekday, `4` on weekend
- Teenager (13–17): `5` on weekday, `6` on weekend
- Adult (18–64): `8` on weekday, `10` on weekend
- Senior (65+): `5` on weekday, `6` on weekend
- If the age is invalid: print `"Invalid age."` and stop
- If the day type is not `weekday` or `weekend`: print `"Invalid day type."`

Print the result as: `"Ticket price: £X"`

### Example output (Part B)
```
Enter your age: 10
Weekday or weekend? weekday
Ticket price: £3
```
```
Enter your age: 30
Weekday or weekend? weekend
Ticket price: £10
```

---

### Part C — Stretch Challenge: Number Classifier
Write a program that asks the user for a **number** (whole number).
Print **all** of the following that apply — one per line:
- If the number is `0`: print `"Zero"`
- If positive: print `"Positive"` — if negative: print `"Negative"`
- If even: print `"Even"` — if odd: print `"Odd"` (zero counts as even)
- If divisible by 5: print `"Divisible by 5"`
- If greater than 100 or less than -100: print `"Out of the usual range"`

### Example output (Part C)
```
Enter a number: -15
Negative
Odd
Divisible by 5
```
```
Enter a number: 0
Zero
Even
```
```
Enter a number: 120
Positive
Even
Divisible by 5
Out of the usual range
```

---

## Hints
- For Part A, check for the invalid age **first**
- For Part B, reuse your age category logic from Part A inside the ticket checker
- For Part C, each condition is **independent** — use separate `if` statements, not `elif`

---

## File
Write your solution in `solution.py` in this folder. Label each part with a comment like `## PART A`.
