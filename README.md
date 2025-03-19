import tkinter as tk
from tkinter import messagebox

# Function to register student
def register_student():
    name = name_entry.get().strip()
    age = age_entry.get().strip()
    grade = grade_entry.get().strip()
    
    if name and age.isdigit() and grade.replace('.', '', 1).isdigit():
        age = int(age)
        grade = float(grade)
        messagebox.showinfo("Registration Complete", f"Student: {name}\nAge: {age}\nAverage Grade: {grade:.2f}")
        clear_fields()
    else:
        messagebox.showerror("Error", "Please enter valid data.")

# Function to clear input fields
def clear_fields():
    name_entry.delete(0, tk.END)
    age_entry.delete(0, tk.END)
    grade_entry.delete(0, tk.END)

# Creating the main window
window = tk.Tk()
window.title("Student Registration")
window.geometry("320x200")

# Labels and input fields
tk.Label(window, text="Student Name:").grid(row=0, column=0, padx=10, pady=5, sticky="e")
name_entry = tk.Entry(window, width=25)
name_entry.grid(row=0, column=1, padx=10, pady=5)

tk.Label(window, text="Age:").grid(row=1, column=0, padx=10, pady=5, sticky="e")
age_entry = tk.Entry(window, width=10)
age_entry.grid(row=1, column=1, padx=10, pady=5)

tk.Label(window, text="Average Grade:").grid(row=2, column=0, padx=10, pady=5, sticky="e")
grade_entry = tk.Entry(window, width=10)
grade_entry.grid(row=2, column=1, padx=10, pady=5)

# Buttons
tk.Button(window, text="Register", command=register_student).grid(row=3, column=0, columnspan=2, pady=10)
tk.Button(window, text="Clear", command=clear_fields).grid(row=4, column=0, columnspan=2, pady=5)

# Start the graphical interface
window.mainloop()

