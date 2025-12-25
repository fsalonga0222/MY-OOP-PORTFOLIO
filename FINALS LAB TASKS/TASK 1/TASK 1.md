
<img width="602" height="598" alt="image" src="https://github.com/user-attachments/assets/99a0aff9-55ce-4a12-9565-0bc697de5840" />

 SOURCE CODE
        class Car:
        def __init__(self, color: str, price: float, size: str):
        self.__color = color
        self.__price = price
        self.__size = size.upper()
        def get_color(self) -> str:
        return self.__color
        def get_price(self) -> float:
        return self.__price
        def get_size(self) -> str:
        return self.__size
        def set_color(self, color: str) -> None:
        self.__color = color
        def set_price(self, price: float) -> None:
        self.__price = price
        def set_size(self, size: str) -> None:
        self.__size = size.upper()
        def __str__(self) -> str:
        size_descriptions = {
        'S': 'small',
        'M': 'medium',
        'L': 'large'
        }
        size_desc = size_descriptions.get(self.size, 'unknown')
        return f"Car ({self.__color}) - P{self.__price:.2f} - {size_desc}"
        if __name__ == "__main__":
        print("Action: Invoking the Car class constructor using Car('red', 19999.85,
        'M').") car1 = Car("red", 19999.85, 'M')
        print("Output:")
        print(car1, "\n")
        print("Action: Invoking the Car class constructor using Car('blue', 50000.00,
        'L').") car2 = Car("blue", 50000.00, 'L')
        print("Output:")
        
        print(car2, "\n")
        print("Action: Invoking the Car class constructor using Car('green', 12345.67, 'S').")
        car3 = Car("green", 12345.67, 'S')
        print("Output:")
        print(car3)

