#TO DO LIST
class ToDoList:
    def _init_(self):
        self.tasks = []

    def add_task(self):
        task = input("Enter a task: ")
        self.tasks.append(task)
        print(f"Task '{task}' added successfully!")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks available.")
        else:
            print("Your tasks:")
            for i, task in enumerate(self.tasks, 1):
                print(f"{i}. {task}")

    def delete_task(self):
        if not self.tasks:
            print("No tasks available.")
        else:
            self.view_tasks()
            try:
                task_num = int(input("Enter task number to delete: "))
                if 1 <= task_num <= len(self.tasks):
                    task = self.tasks.pop(task_num - 1)
                    print(f"Task '{task}' deleted successfully!")
                else:
                    print("Invalid task number.")
            except ValueError:
                print("Invalid input.")

    def run(self):
        while True:
            print("\nTo-Do List Menu:")
            print("1. Add Task")
            print("2. View Tasks")
            print("3. Delete Task")
            print("4. Quit")
            choice = input("Enter your choice: ")
            if choice == "1":
                self.add_task()
            elif choice == "2":
                self.view_tasks()
            elif choice == "3":
                self.delete_task()
            elif choice == "4":
                print("Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")

if _name_ == "_main_":
    todo = ToDoList()
    todo.run()
