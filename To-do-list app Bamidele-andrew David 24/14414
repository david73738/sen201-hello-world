import tkinter as tk
from tkinter import messagebox

# Create main window
root = tk.Tk()
root.title("To-Do List App")
root.geometry("400x400")
root.resizable(False, False)

# Functions
def add_task():
    task = task_entry.get()
    if task == "":
        messagebox.showwarning("Warning", "Please enter a task")
    else:
        task_listbox.insert(tk.END, task)
        task_entry.delete(0, tk.END)

def delete_task():
    try:
        selected = task_listbox.curselection()
        task_listbox.delete(selected)
    except:
        messagebox.showwarning("Warning", "Select a task to delete")

def mark_complete():
    try:
        selected = task_listbox.curselection()
        task = task_listbox.get(selected)
        task_listbox.delete(selected)
        task_listbox.insert(tk.END, f"✔ {task}")
    except:
        messagebox.showwarning("Warning", "Select a task to complete")

# GUI Layout
tk.Label(root, text="My To-Do List", font=("Arial", 16)).pack(pady=10)

task_entry = tk.Entry(root, width=35, font=("Arial", 12))
task_entry.pack(pady=10)

tk.Button(root, text="Add Task", width=25, command=add_task, bg="#28a745", fg="white").pack(pady=5)
tk.Button(root, text="Mark Complete", width=25, command=mark_complete, bg="#007bff", fg="white").pack(pady=5)
tk.Button(root, text="Delete Task", width=25, command=delete_task, bg="#dc3545", fg="white").pack(pady=5)

task_listbox = tk.Listbox(root, width=50, height=12, font=("Arial", 12))
task_listbox.pack(pady=10)

# Run the app
root.mainloop()
