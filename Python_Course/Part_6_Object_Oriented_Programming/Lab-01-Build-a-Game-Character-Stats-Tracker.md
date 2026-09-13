# 🎮 Build a Game Character Stats Tracker

In this lab, you'll build a **game character stats tracker**.  
The program will allow you to **create a character**, **update attributes**, and **retrieve current stats**.

---

## 🎯 Objective

Fulfill the **user stories** below and get **all tests to pass** to complete the lab.

---

## 📌 User Stories

### 1️⃣ Create the GameCharacter Class
- Create a class named **`GameCharacter`** that represents a game character and manages character stats.

---

### 2️⃣ Initial Attributes (Upon Instantiation)

When a new `GameCharacter` object is created, it should have:

- `_name` → set to the string provided during instantiation
- `_health` → set to **100**
- `_mana` → set to **50**
- `_level` → set to **1**

---

### 3️⃣ Name Property (Read-Only)
- Create a **`name`** property
- It should allow **read-only access** to the character’s name

---

### 4️⃣ Health Property
- Define a **getter** that returns the current health
- Define a **setter** that:
  - Prevents health from going **below 0**
  - Caps health at a **maximum of 100**

---

### 5️⃣ Mana Property
- Define a **getter** that returns the current mana
- Define a **setter** that:
  - Prevents mana from going **below 0**
  - Caps mana at a **maximum of 50**

---

### 6️⃣ Level Getter
- Create a **getter** for `level` that returns the character’s current level

---

### 7️⃣ level_up Method
Define a method named **`level_up`** that:

- Increases the character’s level by **1**
- Resets:
  - `health` to **100**
  - `mana` to **50**
- Uses the **property setters** when resetting values
- Prints a message in the format:
```text
<name> leveled up to <level>!
```

---

### 8️⃣ __str__ Method
Define a `__str__` method that returns a formatted string including:

- Character name
- Character level
- Current health
- Current mana

---

### 🧾 Example Output

For a character named **Kratos**, right after instantiation:
```text
Name: Kratos
Level: 1
Health: 100
Mana: 50
```


---

## ▶️ Usage Example

```python
hero = GameCharacter('Kratos')  # Creates a new character named Kratos
print(hero)  # Displays the character's stats

hero.health -= 30  # Decreases health by 30
hero.mana -= 10    # Decreases mana by 10
print(hero)  # Displays the updated stats

hero.level_up()  # Levels up the character
print(hero)  # Displays the stats after leveling up

---

# CODE

```python
class GameCharacter:
    # The GameCharacter class represents a game character and manages its stats

    def __init__(self, name):
        # Constructor method that runs when a new GameCharacter object is created
        # Initializes the character's name, health, mana, and level
        self._name = name        # Stores the character's name (read-only)
        self._health = 100       # Sets initial health to 100
        self._mana = 50          # Sets initial mana to 50
        self._level = 1          # Sets initial level to 1
    
    @property
    def name(self):
        # Getter for the character's name (read-only property)
        return self._name
    
    @property
    def health(self):
        # Getter for the character's current health
        return self._health
    
    @health.setter
    def health(self, new_health):
        # Setter for health that enforces valid limits
        # Prevents health from going below 0 or above 100
        if new_health < 0:
            self._health = 0
        elif new_health > 100:
            self._health = 100
        else:
            self._health = new_health
        return self._health  # Returns the updated health value
    
    @property
    def mana(self):
        # Getter for the character's current mana
        return self._mana
    
    @mana.setter
    def mana(self, new_mana):
        # Setter for mana that enforces valid limits
        # Prevents mana from going below 0 or above 50
        if new_mana < 0:
            self._mana = 0
        elif new_mana > 50:
            self._mana = 50
        else:
            self._mana = new_mana
        return self._mana  # Returns the updated mana value

    @property
    def level(self):
        # Getter for the character's current level
        return self._level
    
    def level_up(self):
        # Increases the character's level by 1
        # Resets health and mana using their respective setters
        self._level += 1
        self.health = 100
        self.mana = 50
        # Prints a message indicating the character leveled up
        print(f"{self._name} leveled up to {self.level}!")
        
    def __str__(self):
        # Returns a formatted string representing the character's current stats
        return (f"Name: {self._name}\n"
                f"Level: {self._level}\n"
                f"Health: {self._health}\n"
                f"Mana: {self._mana}\n")
    
# Creates a new GameCharacter object named 'Kratos'
hero = GameCharacter('Kratos')
print(hero)  # Prints the initial stats of the character

# Decreases the character's health by 30 using the health setter
hero.health -= 30

# Decreases the character's mana by 10 using the mana setter
hero.mana -= 10

print(hero)  # Displays the updated stats after taking damage and using mana

# Levels up the character, increasing level and resetting health and mana
hero.level_up()

print(hero)  # Displays the stats after leveling up
```
