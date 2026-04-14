# Task 03b — Conditionals Practice

## What you need to know
- `if`, `elif`, `else`
- Boolean operators: `and`, `or`
- Comparison operators: `>`, `<`, `==`, `!=`, `>=`, `<=`

---

## Your Task

### Part A — Grade Checker
Write a program that asks the user to enter a **score** (0–100).
Print the matching grade:
- 80 and above → `"Grade: A"`
- 70 to 79 → `"Grade: B"`
- 60 to 69 → `"Grade: C"`
- 50 to 59 → `"Grade: D"`
- Below 50 → `"Grade: F — study harder!"`

If the user enters a number **below 0 or above 100**, print `"Invalid score."` instead.

### Example output (Part A)
```
Enter your score: 73
Grade: B
```
```
Enter your score: 105
Invalid score.
```

---

### Part B — Simple Calculator
Write a program that asks the user for:
1. A first number
2. An operator (`+`, `-`, `*`, `/`)
3. A second number

Then print the result.
- If the operator is `/` and the second number is `0`, print `"Error: cannot divide by zero."`
- If the operator is not one of the four above, print `"Unknown operator."`

### Example output (Part B)
```
Enter first number: 10
Enter operator: *
Enter second number: 4
Result: 40
```
```
Enter first number: 5
Enter operator: /
Enter second number: 0
Error: cannot divide by zero.
```

---

### Part C — Stretch Challenge: Day Checker
Write a program that asks the user to enter a **day of the week** (e.g. `Monday`).
- If it is a weekday (Monday to Friday): print `"It's a weekday. Time to work!"`
- If it is Saturday or Sunday: print `"It's the weekend. Enjoy!"`
- If the input is not a valid day: print `"I don't recognise that day."`

### Example output (Part C)
```
Enter a day: Saturday
It's the weekend. Enjoy!
```
```
Enter a day: Wednesday
It's a weekday. Time to work!
```
```
Enter a day: Funday
I don't recognise that day.
```

---

## Hints
- For Part A, check for the invalid score **first** before checking the grade ranges
- For Part B, use `input()` for the operator — it is already a string, no conversion needed
- For Part C, use `or` to combine multiple days in one condition — you did something similar in Part B of task 03

---

## File
Write your solution in `solution.py` in this folder. Label each part with a comment like `## PART A`.
