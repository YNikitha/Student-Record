student_stack = []

def add_student():
    name = input("Enter student name: ")
    roll = input("Enter roll number: ")
    marks = float(input("Enter marks: "))
    
    student = {
        "Name": name,
        "Roll": roll,
        "Marks": marks
    }
    student_stack.append(student)
    print(f"\n{name}'s record added successfully.")

def remove_student():
    if not student_stack:
        print("No records to remove.")
    else:
        removed = student_stack.pop()
        print(f"Removed record: {removed['Name']}")

def view_last_student():
    if not student_stack:
        print("No records to view.")
    else:
        print("Last added student:")
        print(student_stack[-1])

def display_all_students():
    if not student_stack:
        print("No student records available.")
    else:
        print("\n--- All Student Records ---")
        for student in reversed(student_stack):
            print(f"Name: {student['Name']}, Roll: {student['Roll']}, Marks: {student['Marks']}")

def menu():
    while True:
        print("\n===== Student Record Manager =====")
        print("1. Add Student")
        print("2. Remove Last Student")
        print("3. View Last Student")
        print("4. Display All Students")
        print("5. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == '1':
            add_student()
        elif choice == '2':
            remove_student()
        elif choice == '3':
            view_last_student()
        elif choice == '4':
            display_all_students()
        elif choice == '5':
            print("Exiting program...")
            break
        else:
            print("Invalid choice!")

if __name__ == "__main__":
    menu()
