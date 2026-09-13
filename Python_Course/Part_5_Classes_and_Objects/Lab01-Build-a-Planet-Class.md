# Build a Planet Class

## Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## User Stories

- You should create a class named `Planet`.
- The `Planet` class should have an `__init__` method that:
  - Has four parameters: `self`, `name`, `planet_type`, and `star`.
  - Raises a `TypeError` with the message  
    `name, planet type, and star must be strings`  
    if any of the arguments passed in is not a string type.
  - Raises a `ValueError` with the message  
    `name, planet_type, and star must be non-empty strings`  
    if any of the arguments passed in is an empty string.
  - Assigns the values passed in to the instance attributes `name`, `planet_type`, and `star`.
- The `Planet` class should have an `orbit` method that returns a string in the format:  
  `{name} is orbiting around {star}....`
- The `Planet` class should have a `__str__` method that returns a string in the format:  
  `Planet: {name} | Type: {planet_type} | Star: {star}.`
- You should create three instances of the `Planet` class named:
  - `planet_1`
  - `planet_2`
  - `planet_3`
- You should print each planet object to see the `__str__` method output.
- You should call the `orbit` method on each planet object and print the result.

---

# CODE

```python
# ==========================================
# Planet Class Definition
# ==========================================

class Planet:
    
    def __init__(self, name, planet_type, star):
        """
        Initialize a Planet object.

        Parameters:
        name (str)         : Name of the planet
        planet_type (str)  : Type/category of the planet
        star (str)         : Name of the star the planet orbits
        """

        # ---- Type Validation ----
        # Ensure all arguments are strings
        if not isinstance(name, str) or not isinstance(planet_type, str) or not isinstance(star, str):
            raise TypeError('name, planet type, and star must be strings')
        
        # ---- Value Validation ----
        # Ensure strings are not empty
        elif name == "" or planet_type == "" or star == "":
            raise ValueError('name, planet_type, and star must be non-empty strings')
        
        # ---- Attribute Assignment ----
        self.name = name
        self.planet_type = planet_type
        self.star = star


    # ==========================================
    # Instance Methods
    # ==========================================

    def orbit(self):
        """
        Returns a string describing the planet's orbit.
        """
        return f'{self.name} is orbiting around {self.star}...'


    def __str__(self):
        """
        Returns a readable string representation of the object.
        Automatically called when using print().
        """
        return f'Planet: {self.name} | Type: {self.planet_type} | Star: {self.star}'


# ==========================================
# Object Creation
# ==========================================

planet_1 = Planet('planet_1', 'planet', 'star')
planet_2 = Planet('planet_2', 'planet', 'star')
planet_3 = Planet('planet_3', 'planet', 'star')


# ==========================================
# Output Section
# ==========================================

# Print object details (calls __str__ automatically)
print(planet_1)
print(planet_2)
print(planet_3)

# Print orbit descriptions
print(planet_1.orbit())
print(planet_2.orbit())
print(planet_3.orbit())
```
