# Final Project - Python OOP & Module Organization

## Overview
This project demonstrates object-oriented programming (OOP) principles by organizing multiple tasks into reusable Python modules. Each task is solved using classes, inheritance, and proper design patterns, with a Jupyter notebook that imports and tests these modules.

## Project Structure

```
project/
├── Final project.ipynb       # Main notebook with task demonstrations
├── README.md                 # This file
└── python/                   # Python modules directory
    ├── banking.py           # Task-1: BankAccount class
    ├── calculators.py       # Task-2: Calculator classes
    ├── animals.py           # Task-3: Abstract Animal class
    ├── file_processing.py   # Task-4, Task-5, Task-6: File handling & word frequency
    └── hospital_system.py   # Task-7: Hospital Management System
```

## Tasks Overview

### Task-1: BankAccount Class (`banking.py`)
**Objective:** Manage a bank account with deposits, withdrawals, and balance checking.

**Features:**
- `BankAccount` class with `__init__`, `deposit()`, `withdraw()`, `check_balance()`
- Input validation for negative amounts
- Real-time balance updates

**Usage:**
```python
from banking import BankAccount
account = BankAccount(1000)
account.deposit(500)
account.withdraw(200)
print(account.check_balance())  # 1300
```

---

### Task-2: Calculator Classes (`calculators.py`)
**Objective:** Convert calculator functions into reusable class methods with inheritance.

**Classes:**
- `Calculator`: Basic operations (add, subtract, multiply, divide)
- `AdvancedCalculator`: Extends Calculator with power, modulus, square_root

**Usage:**
```python
from calculators import Calculator, AdvancedCalculator
calc = Calculator()
print(calc.add(10, 5))  # 15

adv = AdvancedCalculator()
print(adv.power(2, 8))    # 256
print(adv.square_root(16)) # 4.0
```

---

### Task-3: Abstract Animal Classes (`animals.py`)
**Objective:** Demonstrate abstract base classes and polymorphism.

**Classes:**
- `Animal`: Abstract base class with abstract method `make_sound()` and concrete `describe()`
- `Dog`, `Cat`, `Cow`: Concrete subclasses implementing `make_sound()`

**Usage:**
```python
from animals import Dog, Cat, Cow
dog = Dog("Buddy", "Dog")
print(dog.describe())          # This is a Dog named Buddy
print(dog.make_sound())        # Woof! Woof!
```

---

### Task-4: TextFileReader Class (`file_processing.py`)
**Objective:** Encapsulate file reading and text analysis functionality.

**Features:**
- `TextFileReader` class with methods:
  - `read_file()`: Load file contents
  - `count_lines()`: Count lines
  - `count_words()`: Count words
  - `count_characters()`: Count characters
  - `display_content()`: Print file content

**Usage:**
```python
from file_processing import TextFileReader
reader = TextFileReader("test.txt")
if reader.read_file():
    print(f"Lines: {reader.count_lines()}")
    print(f"Words: {reader.count_words()}")
    reader.display_content()
```

---

### Task-5: Word Frequency Counter (`file_processing.py`)
**Objective:** Find unique words and count their frequency.

**Function:**
- `count_word_frequency(words_list)`: Returns dictionary with word counts

**Usage:**
```python
from file_processing import count_word_frequency
words = ["Ali", "Hi", "Ali", "Hi", "Ali"]
freq = count_word_frequency(words)
print(freq)  # {'Ali': 3, 'Hi': 2}
```

---

### Task-6: UserExtractor Class (`file_processing.py`)
**Objective:** Extract and manage usernames from username:password files.

**Function & Class:**
- `read_txt_file(file_path)`: Read file with error handling
- `UserExtractor`: Extract usernames from formatted file
  - `extract_usernames()`: Parse username:password format
  - `display_usernames()`: Print extracted users

**Usage:**
```python
from file_processing import read_txt_file, UserExtractor
extractor = UserExtractor("users.txt")
print(extractor.extract_usernames())
extractor.display_usernames()
```

---

### Task-7: Hospital Management System (`hospital_system.py`)
**Objective:** Model a hospital with departments, staff, and patients using OOP.

**Classes:**
- `Person` (ABC): Base class for staff and patients
- `Patient`: Extends Person with patient ID and medical record
- `Staff`: Extends Person with staff ID and position
- `Department`: Manages patients and staff
- `Hospital`: Manages departments

**Usage:**
```python
from hospital_system import Hospital, Department, Staff, Patient

hospital = Hospital("City General Hospital", "Downtown")
dept = Department("Cardiology")

doctor = Staff("Dr. Ahmed", 45, "S001", "Cardiologist")
patient = Patient("John Smith", 55, "P001", "Heart Disease")

dept.add_staff(doctor)
dept.add_patient(patient)
hospital.add_department(dept)
```

---

## Running the Project

### Option 1: Run the Jupyter Notebook
```bash
jupyter notebook "Final project.ipynb"
```
The notebook will:
1. Set up the Python path to locate modules
2. Import and test each task sequentially
3. Display output for verification

### Option 2: Run Individual Modules
```bash
cd project/python
python -c "from banking import BankAccount; acc = BankAccount(1000); acc.deposit(500); print(acc.check_balance())"
```

## Key Design Patterns

✅ **Object-Oriented Design:** Classes with `__init__`, methods, and inheritance  
✅ **Abstract Base Classes:** Used for Animal and Person hierarchies  
✅ **Encapsulation:** Private/protected data and public methods  
✅ **Polymorphism:** Subclasses override parent methods  
✅ **Error Handling:** Try-except blocks for file operations  
✅ **Modularity:** Separate .py files for each task  

## Requirements

- Python 3.7+
- Jupyter Notebook (for running the .ipynb file)
- Standard library only (no external dependencies)

## File Details

| File | Lines | Classes | Functions |
|------|-------|---------|-----------|
| `banking.py` | ~30 | 1 | - |
| `calculators.py` | ~20 | 2 | - |
| `animals.py` | ~25 | 4 | - |
| `file_processing.py` | ~50 | 2 | 2 |
| `hospital_system.py` | ~40 | 5 | - |
| **Total** | **~165** | **14** | **2** |

## Testing

Each task is tested in the Jupyter notebook with sample data:
- Task-1: Create account, deposit/withdraw
- Task-2: Basic and advanced calculations
- Task-3: Create animals and call methods
- Task-4: Read and analyze a test file
- Task-5: Count word frequencies
- Task-6: Extract usernames from file
- Task-7: Create hospital with departments and staff

## Author Notes

This project demonstrates:
- Proper code organization into modules
- Reusable class design
- Inheritance and polymorphism
- Error handling best practices
- Clean separation of concerns

---

**Last Updated:** February 8, 2026  
**Status:** ✅ Complete and Ready
