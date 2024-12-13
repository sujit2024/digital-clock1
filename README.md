# digital-clock1
import tkinter as tk
from time import strftime

def update_time():
    current_time = strftime('%H:%M:%S %p')  # Format: Hour:Minute:Second AM/PM
    label.config(text=current_time)
    label.after(1000, update_time)  # Updates the time every 1000 milliseconds (1 second)

# Initialize tkinter root
root = tk.Tk()
root.title("Digital Clock")
root.geometry("300x150")  # Set the window size
root.resizable(False, False)  # Disable resizing

# Set background and font style for the clock
label = tk.Label(
    root, 
    font=("Helvetica", 48, "bold"), 
    bg="black", 
    fg="cyan"
)
label.pack(expand=True)

# Call the function to update time
update_time()

# Start the tkinter main loop
root.mainloop()
