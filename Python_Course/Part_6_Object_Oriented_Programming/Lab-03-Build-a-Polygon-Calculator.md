# 🏗️ Build a Polygon Area Calculator

In this project, you will use **object-oriented programming** to create a **Rectangle** class and a **Square** class. The **Square** class should be a subclass of **Rectangle** and inherit its methods and attributes.

## 🎯 Objective

Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📜 User Stories

### 📐 Rectangle Class

You should create a **Rectangle** class.

When a Rectangle object is created, it should be initialized with **width** and **height** attributes. The class should also contain the following methods:

- `set_width`: Sets the width of the rectangle.  
- `set_height`: Sets the height of the rectangle.  
- `get_area`: Returns area (`width × height`).  
- `get_perimeter`: Returns perimeter `2(width + height)`.  
- `get_diagonal`: Returns diagonal `√(width² + height²)`.  
- `get_picture`: Returns a string that represents the shape using lines of `*`. The number of lines should be equal to the height and the number of `*` in each line should be equal to the width. There should be a new line (`\n`) at the end of each line. If the width or height is larger than 50, this should return the string: `"Too big for picture."`.  
- `get_amount_inside`: Takes another shape (square or rectangle) as an argument. Returns the number of times the passed in shape could fit inside the shape (with no rotations). For instance, a rectangle with a width of 4 and a height of 8 could fit in two squares with sides of 4.  
- `__str__`: If an instance of a Rectangle is represented as a string, it should look like: `Rectangle(width=5, height=10)`.

---

### 🔲 Square Class

You should create a **Square** class that subclasses **Rectangle**.

When a Square object is created, it should be initialized with a single **side** length. The `__init__` method should store the side length in both the width and height attributes from the Rectangle class.

The Square class should contain the following methods:

- `set_width`: Overrides the `set_width` method from the Rectangle class. It should set the width and height to the side length.  
- `set_height`: Overrides the `set_height` method from the Rectangle class. It should set the width and height to the side length.  
- `set_side`: Sets the height and width of the square equal to the side length.  
- The Square class should be able to access the Rectangle class methods.  
- `__str__`: If an instance of a Square is represented as a string, it should look like: `Square(side=9)`.

---

## 💻 Usage Example

```python
rect = Rectangle(10, 5)
print(rect.get_area())          # 50
rect.set_height(3)
print(rect.get_perimeter())     # 26
print(rect)                     # Rectangle(width=10, height=3)
print(rect.get_picture())       # Prints rectangle of stars

sq = Square(9)
print(sq.get_area())            # 81
sq.set_side(4)
print(sq.get_diagonal())        # 5.656854249492381
print(sq)                       # Square(side=4)
print(sq.get_picture())         # Prints square of stars

rect.set_height(8)
rect.set_width(16)
print(rect.get_amount_inside(sq)) # 8
```

## 📝 Expected Output

```python
50
26
Rectangle(width=10, height=3)
**********
**********
**********

81
5.656854249492381
Square(side=4)
****
****
****
****

8
```

---

# CODE 

```python
import math

# ----------------------------
# 📐 Rectangle Class
# ----------------------------
class Rectangle:
    def __init__(self, width, height):
        """
        Initialize a rectangle with width and height attributes.
        """
        self.width = width
        self.height = height

    def set_width(self, width):
        """
        Set a new width for the rectangle.
        """
        self.width = width

    def set_height(self, height):
        """
        Set a new height for the rectangle.
        """
        self.height = height

    def get_area(self):
        """
        Calculate and return the area of the rectangle.
        Formula: area = width * height
        """
        return self.width * self.height

    def get_perimeter(self):
        """
        Calculate and return the perimeter of the rectangle.
        Formula: perimeter = 2 * (width + height)
        """
        return 2 * (self.width + self.height)

    def get_diagonal(self):
        """
        Calculate and return the diagonal of the rectangle using Pythagoras theorem.
        Formula: diagonal = sqrt(width^2 + height^2)
        """
        return math.sqrt((self.width ** 2) + (self.height ** 2))

    def get_picture(self):
        """
        Returns a string that visually represents the rectangle using '*'.
        Each line represents the width, number of lines represents the height.
        If width or height > 50, returns "Too big for picture."
        """
        if self.width > 50 or self.height > 50:
            return "Too big for picture."
        picture = ""
        for _ in range(self.height):
            picture += "*" * self.width + "\n"
        return picture

    def get_amount_inside(self, other_shape):
        """
        Calculate how many times another shape (rectangle or square)
        can fit inside this rectangle without rotation.
        """
        width_fit = self.width // other_shape.width
        height_fit = self.height // other_shape.height
        return width_fit * height_fit

    def __str__(self):
        """
        String representation of the rectangle for easy reading.
        """
        return f"Rectangle(width={self.width}, height={self.height})"


# ----------------------------
# 🔲 Square Class
# ----------------------------
class Square(Rectangle):
    def __init__(self, side):
        """
        Initialize a square with all sides equal to 'side'.
        Inherits from Rectangle.
        """
        super().__init__(side, side)  # Set both width and height to side length

    def set_width(self, side):
        """
        Override set_width to ensure width and height remain equal.
        """
        self.width = side
        self.height = side

    def set_height(self, side):
        """
        Override set_height to ensure width and height remain equal.
        """
        self.width = side
        self.height = side

    def set_side(self, side):
        """
        Convenience method to set both width and height to the same side length.
        """
        self.width = side
        self.height = side

    def __str__(self):
        """
        String representation of the square for easy reading.
        """
        return f"Square(side={self.width})"


# ----------------------------
# 💻 Usage Example
# ----------------------------
if __name__ == "__main__":
    # Create a rectangle
    rect = Rectangle(10, 5)
    print("Area of rectangle:", rect.get_area())         # 50
    rect.set_height(3)
    print("Perimeter of rectangle:", rect.get_perimeter())  # 26
    print(rect)                                          # Rectangle(width=10, height=3)
    print(rect.get_picture())                            # Visual rectangle

    # Create a square
    sq = Square(9)
    print("Area of square:", sq.get_area())             # 81
    sq.set_side(4)
    print("Diagonal of square:", sq.get_diagonal())     # 5.656854249492381
    print(sq)                                           # Square(side=4)
    print(sq.get_picture())                             # Visual square

    # Check how many squares fit in the rectangle
    rect.set_height(8)
    rect.set_width(16)
    print("Squares that fit inside rectangle:", rect.get_amount_inside(sq))  # 8
```
