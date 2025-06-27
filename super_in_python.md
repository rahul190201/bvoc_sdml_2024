# 🐍 Understanding `super()` in Python - Practice Sheet

## 📘 What is `super()`?

The `super()` function in Python is used to call a method from the parent (or superclass) in the child (subclass).  
It is most commonly used in the `__init__()` method to initialize the parent class when extending functionality in the child class.

---

## ✅ Example 1: Basic Inheritance with `super()`

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print(f"Person: {self.name}, Age: {self.age}")

class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id
        print(f"Student ID: {self.student_id}")

s1 = Student("Rahul", 15, "S123")
```

**Output:**
```
Person: Rahul, Age: 15
Student ID: S123
```

---

## ✅ Example 2: Extending a Vehicle Class

```python
class Vehicle:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
        print(f"Vehicle: {self.brand}, Model: {self.model}")

class Car(Vehicle):
    def __init__(self, brand, model, doors):
        super().__init__(brand, model)
        self.doors = doors
        print(f"Doors: {self.doors}")

c1 = Car("Toyota", "Camry", 4)
```

---

## 📝 Practice Sheet

### 🔍 Part 1: Concept Check (Short Answer)

1. What does the `super()` function do in Python?  
2. Why is `super()` preferred over calling the parent class directly?  
3. In which method is `super()` most commonly used?  
4. What would happen if you forget to call `super().__init__()` in a child class?

---

### 🧠 Part 2: Fill in the Blanks

Fill in the missing line using `super()`.

```python
class Animal:
    def __init__(self, species):
        self.species = species
        print(f"I am a {self.species}")

class Dog(Animal):
    def __init__(self, species, breed):
        # Call the parent constructor
        __________
        self.breed = breed
        print(f"My breed is {self.breed}")

d = Dog("Mammal", "Labrador")
```

**Expected Output:**
```
I am a Mammal
My breed is Labrador
```

---

### 🎯 Part 3: Mini Project – Inheritance Chain

Create a chain of classes using `super()`.

#### Objective:
Use `super()` to build a family of classes: `Vehicle` → `Car` → `ElectricCar`.

#### Instructions:
1. Create a class `Vehicle` with:
   - `__init__(self, brand, model)`
   - `display_info()` method to print brand and model.

2. Create a subclass `Car`:
   - Adds `doors` attribute.
   - Uses `super()` to initialize brand and model.
   - Overrides `display_info()` to include doors.

3. Create a subclass `ElectricCar`:
   - Adds `battery_capacity`.
   - Uses `super()` to initialize Car.
   - Overrides `display_info()` to include battery info.

#### Example Output:
```
Brand: Tesla
Model: Model 3
Doors: 4
Battery: 75 kWh
```

---

### 💡 Bonus: Reflection Questions

- What would happen if `super()` was not used in the `ElectricCar` class?
- What are the advantages of using inheritance and `super()` in a real-world application?

---

Happy Coding! 🎉
