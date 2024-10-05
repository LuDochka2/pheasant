# pheasantimport random
import time

class Pheasant:
    def __init__(self, name, grid_size=10):
        self.name = name
        self.grid_size = grid_size
        # Start the pheasant at the center of the grid
        self.x = grid_size // 2
        self.y = grid_size // 2

    def move(self):
        # Randomly move the pheasant one step in any direction
        dx, dy = random.choice([(0, 1), (1, 0), (0, -1), (-1, 0)])
        self.x = (self.x + dx) % self.grid_size
        self.y = (self.y + dy) % self.grid_size

    def position(self):
        return (self.x, self.y)

    def display(self):
        print(f"{self.name} is currently at position {self.position()}")


def simulate_pheasant_movement(steps=20):
    pheasant = Pheasant(name="Pheasant", grid_size=10)
    
    for step in range(steps):
        pheasant.move()
        pheasant.display()
        time.sleep(1)  # Pause for a moment to simulate time passing


if __name__ == "__main__":
    simulate_pheasant_movement(steps=10)
