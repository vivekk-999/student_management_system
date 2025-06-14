# student_management_system

students = {}

def add_student():
    name = input("Enter student name: ").title()
    marks = []
    for subject in ["Math", "Science", "English"]:
        score = int(input(f"Enter marks for {subject}: "))
        marks.append(score)
    students[name] = marks

def view_all():
    for name, marks in students.items():
        avg = sum(marks) / len(marks)
        print(f"{name}: Marks={marks}, Average={round(avg, 2)}")

def search_student():
    name = input("Enter name to search: ").title()
    if name in students:
        print(f"{name} - Marks: {students[name]}")
    else:
        print("Student not found.")

while True:
    print("\n--- MENU ---")
    print("1. Add Student")
    print("2. View All Students")
    print("3. Search Student")
    print("4. Exit")
    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        view_all()
    elif choice == "3":
        search_student()
    elif choice == "4":
        break
    else:
        print("Invalid option.")
