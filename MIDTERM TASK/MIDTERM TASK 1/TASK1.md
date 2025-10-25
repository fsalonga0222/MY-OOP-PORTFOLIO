Midterm Lab Task 1

Problem 1. Use Appropriate Escape Sequence( \n, \t \b \ ..etc) for the problem below

<img width="1036" height="593" alt="image" src="https://github.com/user-attachments/assets/fc9310c8-9b95-44c3-9e51-9bb21b468052" />

Source Code:

      print("Database Record\n")
      print("\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\")
      print("Name:\t\tJohn Doe")
      print("Email:\t\tjohn.doe@example.com")
      print("University:\tABC University")

Output:

<img width="517" height="193" alt="image" src="https://github.com/user-attachments/assets/fa7184d1-197c-41b0-bfb0-eb7a5d294c15" />

Problem 2. Using Placeholders for Email Details: Use appropriate type specifiers %s, %d, %f etc… for this task


<img width="833" height="568" alt="image" src="https://github.com/user-attachments/assets/40ed9f38-0444-4d3a-aae8-19fd927faf7f" />


Source Code:

    sender = "Jane"
    subject = "Greetings"
    version = 1.2
    discount = 10.50
    status = "A"
    code = "ABCD123"
    location = "City XYZ"
    age = 30
    company = "ABC Corporation"
    website = "www.example.com"
    phone = "+1 123-456-7890"
    job_title = "Software Engineer"
    department = "Engineering"
    
    print("Dear John, I hope this email finds you well.")
    print("I wanted to reach out and say hello.")
    print("I hope you are doing well and enjoying your day.")
    print("It's been a while since we last spoke, and I wanted to catch up with you.")
    print("Let's plan to meet up soon and have a great time together!")
    print(f"Subject: {subject}")
    print(f"Sender: {sender}")
    print(f"Version: {version}")
    print(f"Discount: {discount:.2f}%")
    print(f"Status: {status}")
    print(f"Code: {code}")
    print(f"Location: {location}")
    print(f"Age: {age}")
    print(f"Company: {company}")
    print(f"Website: {website}")
    print(f"Phone: {phone}")
    print(f"Job Title: {job_title}")
    print(f"Department: {department}")
Output:


<img width="759" height="469" alt="image" src="https://github.com/user-attachments/assets/5cf5a1fd-3198-494e-9c14-c6962d0660ee" />

Problem 3. Book Reservation; Accept User Input


<img width="770" height="278" alt="image" src="https://github.com/user-attachments/assets/884f50f9-2d38-4963-8d28-fb94f948da24" />

Source Code:

    title = input("Enter the book title: ")
    author = input("Enter the author: ")
    year = int(input("Enter the year of publication: "))
    genre = input("Enter the genre: ")
    library = input("Enter the library: ")
    member_id = input("Enter your member ID: ")
    return_date = input("Enter the return date: ")
    
    print(f"\nYou have successfully reserved the book '{title}' by {author}.")
    print(f"Year of Publication: {year}")
    print(f"Genre: {genre}")
    print(f"Library: {library}")
    print(f"Member ID: {member_id}")
    print(f"Return Date: {return_date}")
Output:

<img width="757" height="422" alt="image" src="https://github.com/user-attachments/assets/dcd7add0-1a38-4a6f-a69b-f9c50610ab6d" />

Problem 4. Day Identifier

<img width="714" height="603" alt="image" src="https://github.com/user-attachments/assets/cc02bc33-9438-4679-a9e9-48fbfedeacd7" />

Source Code:

    day = int(input("Enter day: "))
    
    if day == 1:
        print("Monday")
    elif day == 2:
        print("Tuesday")
    elif day == 3:
        print("Wednesday")
    elif day == 4:
        print("Thursday")
    elif day == 5:
        print("Friday")
    elif day == 6:
        print("Saturday")
    elif day == 7:
        print("Sunday")
    else:
        print("Invalid input")
Output:

<img width="224" height="179" alt="image" src="https://github.com/user-attachments/assets/66c7d03b-4530-42c5-b1b0-1e187aa7ae47" />

