# Build a User Configuration Manager

In this lab, you will build a **User Configuration Manager** that allows users to manage their settings such as **theme**, **language**, and **notifications**. You will implement functions to **add**, **update**, **delete**, and **view** user settings.

## Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## User Stories

### 1. `add_setting` Function

You should define a function named `add_setting` with two parameters representing:

- A **dictionary** of settings
- A **tuple** containing a key-value pair

#### Requirements:

- Convert the key and value to **lowercase**.
- If the key **exists**, return:  
```python
Setting '[key]' already exists! Cannot add a new setting with this name.
```

- If the key **doesn't exist**, add the key-value pair to the dictionary and return:  
```python
Setting '[key]' added with value '[value]' successfully!
```

- The messages returned should have the **key and value in lowercase**.

---

### 2. `update_setting` Function

You should define a function named `update_setting` with two parameters representing:

- A **dictionary** of settings
- A **tuple** containing a key-value pair

#### Requirements:

- Convert the key and value to **lowercase**.
- If the key **exists**, update its value in the dictionary and return:  
```python
Setting '[key]' updated to '[value]' successfully!
```

- If the key **doesn't exist**, return:  
```python
Setting '[key]' does not exist! Cannot update a non-existing setting.
```

- The messages returned should have the **key and value in lowercase**.

---

### 3. `delete_setting` Function

You should define a function named `delete_setting` with two parameters:

- A **dictionary** of settings
- A **key** to delete

#### Requirements:

- Convert the key passed to **lowercase**.
- If the key **exists**, remove the key-value pair from the dictionary and return:  
```python
Setting '[key]' deleted successfully!
```

- If the key **does not exist**, return:  
```python
Setting not found!
```

- The messages returned should have the **key in lowercase**.

---

### 4. `view_settings` Function

You should define a function named `view_settings` with one parameter:

- A **dictionary** of settings

#### Requirements:

- If the dictionary is **empty**, return:  
```python
No settings available.
```

- If the dictionary contains settings, return a string displaying the settings in the following format:  
```python
Current User Settings:
Key1: value1
Key2: value2
```


- The key should be **capitalized**.  

**Example:**

```python
view_settings({'theme': 'dark', 'notifications': 'enabled', 'volume': 'high'})
```

Output:

```python
Current User Settings:
Theme: dark
Notifications: enabled
Volume: high
```

---

### Testing

For testing the code, create a dictionary named test_settings to store some user configuration preferences.

---

# CODE

```Python
def add_setting(settings,settings_pair):
    key, value = settings_pair
    key_lower = key.lower()
    value_lower = str(value.lower())

    if key_lower in settings:
        return f"Setting '{key_lower}' already exists! Cannot add a new setting with this name."
    
    settings[key_lower] = value_lower
    return f"Setting '{key_lower}' added with value '{value_lower}' successfully!"


def update_setting(settings, settings_pair): 
    key, value = settings_pair
    key_lower = key.lower()
    value_lower = str(value).lower()

    if key_lower not in settings:
        return f"Setting '{key_lower}' does not exist! Cannot update a non-existing setting."
    
    settings[key_lower] = value_lower
    return f"Setting '{key_lower}' updated to '{value_lower}' successfully!"

def delete_setting(settings, key):
    key_lower = key.lower()

    if key_lower in settings:
        del settings[key_lower]
        return f"Setting '{key_lower}' deleted successfully!"
    
    return "Setting not found!"

def view_settings(settings):
    if not settings:
        return "No settings available."
    
    result = "Current User Settings:\n"
    for key, value in settings.items():
        result += f"{key.title()}: {value}\n"
    return result
    
test_settings = {"Theme": "Dark", "Notifications": "Enabled"}

```
