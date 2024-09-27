# To-do-list
# to_do_list.py

def show_menu():
    print("\nMenu:")
    print("1. View To-Do List")
    print("2. Add Task")
    print("3. Remove Task")
    print("4. Exit")


def view_tasks(tasks):
    if not tasks:
        print("\nYour to-do list is empty.")
    else:
        print("\nYour To-Do List:")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")


def add_task(tasks):
    task = input("\nEnter the task you want to add: ")
    tasks.append(task)
    print(f"Task '{task}' added.")


def remove_task(tasks):
    if not tasks:
        print("\nNo tasks to remove.")
    else:
        view_tasks(tasks)
        try:
            task_num = int(input("\nEnter the task number you want to remove: "))
            if 1 <= task_num <= len(tasks):
                removed_task = tasks.pop(task_num - 1)
                print(f"Task '{removed_task}' removed.")
            else:
                print("Invalid task number.")
        except ValueError:
            print("Please enter a valid number.")


def main():
    tasks = []
    while True:
        show_menu()
        choice = input("\nEnter your choice (1-4): ")

        if choice == '1':
            view_tasks(tasks)
        elif choice == '2':
            add_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            print("Exiting the To-Do List app. Goodbye!")
            break
        else:
            print("Invalid choice. Please choose a valid option from the menu.")


if __name__ == "__main__":
    main()
