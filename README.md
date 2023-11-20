# Internship-task-3-for-python-development
#create to do list programme using python
# Define an empty list to store tasks
tasks = []

def show_menu():
    print("To-Do List Menu:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark Task as Completed")
    print("4. Remove Task")
    print("5. Exit")

def add_task():
    task = input("Enter the task: ")
    tasks.append({"task": task, "completed": False})
    print("Task added!")

def view_tasks():
    if not tasks:
        print("No tasks yet.")
    else:
        print("Tasks:")
        for i, task in enumerate(tasks, start=1):
            status = " [X]" if task["completed"] else " [ ]"
            print(f"{i}.{status} {task['task']}")

def mark_completed():
    view_tasks()
    choice = int(input("Enter the task number to mark as completed: "))
    if 1 <= choice <= len(tasks):
        tasks[choice - 1]["completed"] = True
        print("Task marked as completed!")
    else:
        print("Invalid choice.")

def remove_task():
    view_tasks()
    choice = int(input("Enter the task number to remove: "))
    if 1 <= choice <= len(tasks):
        del tasks[choice - 1]
        print("Task removed!")
    else:
        print("Invalid choice.")

# Main program loop
while True:
    show_menu()
    option = input("Enter your choice: ")

    if option == "1":
        add_task()
    elif option == "2":
        view_tasks()
    elif option == "3":
        mark_completed()
    elif option == "4":
        remove_task()
    elif option == "5":
        print("Exiting...")
        break
    else:
        print("Invalid choice. Please enter a valid option.")
