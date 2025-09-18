# my-first-repo
my first github repository
# todo_list.py

tasks = []

def show_menu():
    print("\n=== To-Do List App ===")
    print("1. Show tasks")
    print("2. Add task")
    print("3. Remove task")
    print("4. Exit")

def show_tasks():
    if not tasks:
        print("No tasks yet.")
    else:
        print("\nYour tasks:")
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")

def add_task():
    task = input("Enter a new task: ")
    tasks.append(task)
    print(f"Task '{task}' added.")

def remove_task():
    show_tasks()
    if tasks:
        try:
            num = int(input("Enter the task number to remove: "))
            removed = tasks.pop(num - 1)
            print(f"Task '{removed}' removed.")
        except (ValueError, IndexError):
            print("Invalid task number.")

while True:
    show_menu()
    choice = input("Choose an option: ")
    if choice == "1":
        show_tasks()
    elif choice == "2":
        add_task()
    elif choice == "3":
        remove_task()
    elif choice == "4":
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please try again.")
