import tkinter as tk
import random
import string

def generate_password():
    password_length = int(length_entry.get())
    if password_length <= 0:
        result_label.config(text="Please enter a valid length.")
        return

    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(password_length))
    result_label.config(text="Generated Password: " + password)

# Create a tkinter window
root = tk.Tk()
root.title("Password Generator")

# Label and entry for password length
length_label = tk.Label(root, text="Enter Password Length:")
length_label.pack()

length_entry = tk.Entry(root)
length_entry.pack()

# Button to generate password
generate_button = tk.Button(root, text="Generate Password", command=generate_password)
generate_button.pack()

# Label to display the generated password
result_label = tk.Label(root, text="")
result_label.pack()

# Run the tkinter main loop
root.mainloop()
