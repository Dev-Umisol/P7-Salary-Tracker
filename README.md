# 📁 Salary Tracking System
A Python class that models an employee with validated name, level, and salary management including, promotion logic and property-based access control.

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Project](https://img.shields.io/badge/Learning-Journey-orange)

## 📌 About

This project was built to practice properties, getters, setters, and exception handling in Python OOP. The `Employee class` enforces strict rules around name, level, and salary changes, promotions are allowed but demotions are not, and salaries can never fall below the base rate for an employee's current level. All validation is handled through Python's `@property` decorator pattern rather than manual method calls.

## 🧠 What I Learned

- **`@property` with getters and setters** — Using `@property` to expose private attributes (`_name`, `_level`, `_salary`) safely, and `@attribute.setter` to intercept and validate changes before they're applied
- **Private attributes with `_`prefix** — Protecting internal state by prefixing attributes with underscore, preventing direct external modification
- **`raise TypeError` and `raise ValueError`** — Raising specific built-in exceptions with descriptive messages rather than just returning error strings, which is the correct Python pattern for class-level validation
- **Class-level variables** — Using `_base_salaries` as a class variable (shared across all instances) to store the salary lookup table, rather than duplicating it per instance
- **`__str__` vs `__repr__`** — Implementing both dunder methods: `__str__` for a clean human-readable label and `__repr__` for a developer facing string that could reconstruct the object
- **Promotion logic** — Comparing salary values from the class-level dictionary to enforce that level changes can only go upward, blocking both same level and downward changes

## 🛠️ Technologies Used

| Tool/Library | Purpose |
|--------------|---------|
| Python 3.x   | Core Language |

## 💡 How It Works

Employees are created with a name and a level. Valid levels and their base salaries are:

| Level | Base Salary |
|-------|-------------|
| `trainee` | $1,000 |
| `junior` | $2,000 |
| `mid-level` | $3,000 |
| `senior` | $4,000 |

Salary can be set above the base rate, but never below it. Level can only be promoted, never demoted.

**Example Output:**
```
Charlie Brown: trainee
Base salary: $1000
'Charlie Brown' promoted to 'junior'.
Salary updated to $2000.
```

## 🚀 Future Improvements

- [ ]  Add a give_raise(amount) method that applies a salary increase on top of the base
- [ ]  Track promotion history with timestamps using the datetime module
- [ ]  Add a Company class that holds a list of Employee objects and can report total payroll
- [ ]  Write unit tests with pytest to cover invalid levels, type errors, and demotion attempts

## 📂 Project Structure

```
salary-tracker/
│
├── P7SalaryTracker.py    # Employee class and example usage
└── README.md
```

*Part of my Python learning journey 🐍 — practicing properties, getters/setters, and exception handling in OOP*
