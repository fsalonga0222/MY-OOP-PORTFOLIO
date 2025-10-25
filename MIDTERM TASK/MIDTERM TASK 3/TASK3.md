Midterm Lab Task 3:

Modify the menuCart program and include the following requirements:

Problem 1: Validate user choice (If choice is not in the cart) - "display item is not in the cart"

Problem 2: Input Customer Name and Age if age is 60 and above provide 20% discount from the total purchased.

Source Code:

    menu={"Burger":35.00,
      "Tacos":50.00,
      "Fries":20.00,
      "Ice Coffee":25.00}
    
    cart = []
    total = 0
    print("------- M E N U ----------")
    for key, value in menu.items():
    print(f"{key:15}:P{value:.2f}")
    print("--------------------------")
    
    
    while True:
      food = input("Select an item from the menu (q to quit):")
    if food.lower() == 'q':
      break
    elif food not in menu:
      print("Item is not in the Cart")
    elif menu.get(food) not in menu:
      cart.append(food)
    name = input("Enter Customer Name:")
    age = int(input("Enter Customer Age:"))
    
    
    print("Your orders are")
    for food in cart:
      total = total + menu.get(food)
      print(food, end=" ")
    if age >= 60:
      discount = total * 0.20
      total -= discount
    print(f"Senior discount applied (20%): -P{discount:0.2f}")
    print()
    print(f"Total Purchased:P{total: 0.2f}")
Output:

<img width="621" height="484" alt="image" src="https://github.com/user-attachments/assets/74715f4f-9e2e-47a6-8202-7c021c429c6c" />

