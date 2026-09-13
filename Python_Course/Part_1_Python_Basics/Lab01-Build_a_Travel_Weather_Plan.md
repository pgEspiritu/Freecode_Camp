# Build a Travel Weather Planner

For this lab, you will use conditional statements to determine whether commuting is possible based on the weather, the distance to travel, and the availability of a vehicle.

## Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## Requirements

You should create the following variables:

- `distance_mi` (a number representing the distance to travel in miles)
- `is_raining` (a boolean representing if the user is currently experiencing rainy weather)
- `has_bike` (a boolean representing if the user has a bicycle)
- `has_car` (a boolean representing if the user has a car)
- `has_ride_share_app` (a boolean representing if the user has an app that allows them to request a ride)

You should use conditional statements to determine whether commuting is possible based on the values of these variables.

You should use `if`, `elif`, and `else` statements to evaluate the distance categories in ascending order.

---

## Conditions

### 1. If `distance_mi` is a falsy value:
- You should print `False`.

### 2. If the distance is less than or equal to 1 mile:
- You should print `True` only if it is not raining.
- Otherwise, you should print `False`.

### 3. If the distance is greater than 1 mile and less than or equal to 6 miles:
- You should print `True` only if the person has a bike and it is not raining.
- Otherwise, you should print `False`.

### 4. If the distance is greater than 6 miles:
- You should print `True` if the person has a car or has a ride-share app.
- Otherwise, you should print `False`.


# CODE

```python
distance_mi = 0
is_raining = False
has_bike = True
has_car = True
has_ride_share_app = True

if not distance_mi:
    print(False)
elif distance_mi <= 1:
    if not is_raining:
        print(True)
    else:
        print(False)
elif distance_mi > 1 and distance_mi <= 6:
    if has_bike and not is_raining:
        print(True)
    else:
        print(False)
elif distance_mi > 6:
    if has_car or has_ride_share_app:
        print(True)
    else:
        print(False)
```
