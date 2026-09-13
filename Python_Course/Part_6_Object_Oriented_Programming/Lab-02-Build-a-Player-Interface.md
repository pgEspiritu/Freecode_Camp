# 🎮 Build a Player Interface

## 🎯 Objective
Fulfill the user stories below and get all the tests to pass to complete the lab.

---

## 📖 User Stories

You should define an abstract class named Player that inherits from the abc.ABC class.

The Player class should have an __init__ method that sets:

- 🔹 The moves attribute to an empty list.
- 🔹 The position attribute to (0, 0).
- 🔹 The path attribute to a list containing the initial position.

The Player class should have a method named make_move that:

- 🎲 Uses random.choice to get a random move from the moves attribute (defined in the concrete class).
- ➕ Adds the values from the selected move to the current position and updates the position attribute.
- 🧭 Appends the new position tuple to the path attribute.
- ✅ Returns the new position.

The Player class should have an abstract method named level_up to be implemented in concrete classes.

You should define a Pawn class that inherits from the Player class.

The Pawn class should use super() to call the parent's __init__ method and then set the moves attribute to a list of tuples representing x, y coordinates.

Each coordinate tuple should represent a movement of 1 unit in the following directions: ⬆️ up, ⬇️ down, ⬅️ left, ➡️ right.

The Pawn class should implement a concrete level_up method by adding more moves to the moves attribute. The added moves should represent the four diagonal movements (for example, 1 unit down plus 1 unit left).

---

## ⚠️ Note
Standard library modules should be imported without using aliases. Tests related to the Player class will fail until the Pawn class becomes instantiable.

---

## CODE

```python
from abc import ABC, abstractmethod   # Import tools for creating abstract base classes
import random                         # Import random module for selecting moves randomly


# ---------------------------------------------------------
# Abstract Base Class: Player
# ---------------------------------------------------------
class Player(ABC):
    def __init__(self):
        # List of possible moves.
        # This will be defined by concrete subclasses (e.g., Pawn).
        self.moves = []

        # Current position of the player on a 2D grid (x, y).
        # Player starts at origin.
        self.position = (0, 0)

        # Stores the history of all positions visited.
        # Initialized with the starting position.
        self.path = [self.position]

    def make_move(self):
        """
        Selects a random move from available moves,
        updates the player's position, records the move,
        and returns the new position.
        """

        # Randomly select a movement tuple (dx, dy)
        dx, dy = random.choice(self.moves)

        # Update position by adding movement offsets
        self.position = (
            self.position[0] + dx,
            self.position[1] + dy
        )

        # Record the new position in the path history
        self.path.append(self.position)

        # Return updated position
        return self.position

    @abstractmethod
    def level_up(self) -> None:
        """
        Abstract method that must be implemented
        by subclasses to enhance or modify movement abilities.
        """
        pass


# ---------------------------------------------------------
# Concrete Class: Pawn
# ---------------------------------------------------------
class Pawn(Player):
    def __init__(self):
        # Call parent constructor to initialize
        # moves, position, and path attributes
        super().__init__()

        # Define basic movement set:
        # one unit in four cardinal directions
        self.moves = [
            (0, 1),    # Move up
            (0, -1),   # Move down
            (-1, 0),   # Move left
            (1, 0)     # Move right
        ]

    def level_up(self):
        """
        Enhances the pawn's movement by adding
        diagonal movement options.
        """

        # Additional diagonal movements
        diagonal_moves = [
            (1, 1),     # Up-right
            (1, -1),    # Down-right
            (-1, 1),    # Up-left
            (-1, -1)    # Down-left
        ]

        # Add new moves to existing move list
        self.moves.extend(diagonal_moves)
```
