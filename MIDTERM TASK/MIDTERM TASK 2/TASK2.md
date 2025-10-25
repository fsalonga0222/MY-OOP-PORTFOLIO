Midterm Lab Task 2:


<img width="669" height="701" alt="image" src="https://github.com/user-attachments/assets/69f15ed1-a36a-4488-a727-c7798ec52235" />

Source Code:

    product_name = str(input("Enter Product Name:"))
    category = str(input("Enter Category:"))
    quality = float(input("Enter Quality Rating:"))  
    price = float(input("Enter Price Rating:"))
    service = float(input("Enter Service Rating:"))  

    def calculate_average_rating(quality,price,service):  
      total = quality + price + service  avg = total / 3  return avg  
    
    def analyze_product():  
      print("Product Name: %s " %product_name )
      print("Category: %s" % category )
      print("Quality Rating: %.2f" % quality) 
      print("Price Rating: %.2f "% price)  
      print("Service Rating: %.2f" % service)  
      print("Overall Average Rating: %.2f" % calculate_average_rating(quality, price, service)) 
      
    analyze product()
Output:

Sample Output 1:


<img width="692" height="406" alt="image" src="https://github.com/user-attachments/assets/2772de41-b0fe-4325-b19d-44ee9d90af02" />

Sample Output 2:

<img width="561" height="389" alt="image" src="https://github.com/user-attachments/assets/cd4daeb2-cb1f-4aba-b7b9-0e15ca410769" />
