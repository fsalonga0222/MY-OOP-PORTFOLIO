<img width="716" height="445" alt="image" src="https://github.com/user-attachments/assets/1d686bfe-ab1e-4e35-823e-0aef18cc94e4" />

SOURCE CODE

      import mysql.connector
      
      
      conn = mysql.connector.connect(
         host="localhost",
         user="root",
         password="",
         database="employees_db"
      )
      
      
      cursor = conn.cursor()
      
      
      def add_employee():
         emp_id = input("Enter Employee ID:")
         fn = input("Enter Full Name:")
         post = input("Enter Position:")
         dept = input("Enter Department:")
         rate = float(input("Enter Rate:"))
         cursor.execute("INSERT INTO employees_db(emp_id, full_name, position, department, rate)""VALUES(%s,%s,%s,%s,%s)",
                        (emp_id, fn, post, dept, rate))
         conn.commit()
         print("Employee added Sucessfully!\n")
      
      
      def view_employees():
         cursor.execute("SELECT * FROM employees_db")
         rows = cursor.fetchall()
         if rows:
             print("\nEmployees List:")
             for row in rows:
                 print(row)
         else:
             print("\nNo employees found.\n")
      
      
      def update_employee():
         emp_id = input("Enter employee ID to update: ")
         full_name = input("Enter new name: ")
         rate = float(input("Enter new salary: "))
         cursor.execute("UPDATE employees_db SET full_name=%s, rate=%s WHERE emp_id=%s",
                        (full_name, rate, emp_id))
         print("\nEmployee updated successfully!\n")
         view_employees()
      
      
      def delete_employee():
         emp_id = input("Enter employee ID to delete: ")
         cursor.execute("DELETE FROM employees_db WHERE emp_id=%s", (emp_id,))
         conn.commit()
         print("\nEmployee deleted successfully!\n")
         view_employees()
      
      
      def search_employee():
         print("\nSearch Employee")
         print("1. Search by Name")
         print("2. Search by Employee ID")
         choice = input("Enter option: ")
         if choice == "1":
             full_name = input("Enter name to search: ")
             cursor.execute("SELECT * FROM employees_db WHERE full_name LIKE %s", ('%' + full_name + '%',))
         elif choice == "2":
             emp_id = input("Enter employee ID to search: ")
             cursor.execute("SELECT * FROM employees_db WHERE emp_id=%s", (emp_id,))
         else:
             print("Invalid option.\n")
             return
         result = cursor.fetchall()
         if result:
             print("\nSearch Results:")
             for row in result:
                 print(row)
         else:
             print("\nNo matching employee found.\n")
      
      
      def main_menu():
         while True:
             print("\n----- Employee Manager -----")
             print("1. Add Employee")
             print("2. View Employees")
             print("3. Update Employee")
             print("4. Delete Employee")
             print("5. Search Employee")
             print("6. Exit")
             choice = input("Enter your choice: ")
             if choice == "1":
                 add_employee()
             elif choice == "2":
                 view_employees()
             elif choice == "3":
                 update_employee()
             elif choice == "4":
                 delete_employee()
             elif choice == "5":
                 search_employee()
             elif choice == "6":
                 print("Exiting program...")
                 conn.close()
                 break
             else:
                 print("Invalid choice. Try again.\n")
      
      
      if __name__ == "__main__":
         main_menu()
         cursor.close()
         conn.close()

OUTPUT

<img width="718" height="357" alt="image" src="https://github.com/user-attachments/assets/0b58a302-6c88-4014-b43e-8330161f021a" />

<img width="714" height="391" alt="image" src="https://github.com/user-attachments/assets/26d502ef-108f-4a21-9e1b-bc91f2f08bef" />

<img width="715" height="368" alt="image" src="https://github.com/user-attachments/assets/e90f7193-8176-4159-be58-221a273680dc" />

<img width="715" height="327" alt="image" src="https://github.com/user-attachments/assets/90aff704-625b-486b-8532-431f67b5f048" />

<img width="718" height="434" alt="image" src="https://github.com/user-attachments/assets/7c35d339-4002-4727-8ec7-f50d5d7100f9" />

