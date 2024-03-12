## Day 36: File Handling in Python

### Introduction to File Handling

File handling is a crucial aspect of programming, allowing you to store, retrieve, and manipulate data on your computer. Python provides simple methods for file handling operations such as reading, writing, and appending content to files.

### Opening and Closing Files

Before you can read or write to a file, you need to open it using Python's built-in `open()` function. This function returns a file object, which provides methods and attributes to interact with the file content. It's also important to close the file when you're done with it to free up system resources.

```python
# Opening a file
file = open('example.txt', 'r')  # 'r' mode opens the file for reading

# Closing a file
file.close()
```

### Reading from Files

Python allows you to read the entire content of a file or read it line by line. This flexibility is useful for processing large files or when you need to perform operations on each line.

```python
# Reading the entire content
file = open('example.txt', 'r')
content = file.read()
print(content)
file.close()

# Reading line by line
file = open('example.txt', 'r')
for line in file:
    print(line, end='')
file.close()
```

### Writing to Files

Writing to a file in Python is straightforward. You can overwrite existing content or append to the end of the file. Remember, writing mode ('w') will create the file if it doesn't exist and overwrite it if it does.

```python
# Writing to a file (overwriting)
file = open('example.txt', 'w')
file.write("This is new content.")
file.close()

# Appending to a file
file = open('example.txt', 'a')
file.write("\nAdding a new line.")
file.close()
```

### Using `with` Statement for File Handling

The `with` statement simplifies file handling by abstracting the complexity of ensuring that files are properly closed after their suite finishes, even if exceptions are thrown.

```python
# Reading using 'with'
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# Writing using 'with'
with open('example.txt', 'w') as file:
    file.write("Simplified file handling.")
```

### Real-Life Example: Data Logging

Consider a scenario where you need to log data from a sensor into a file for later analysis.

```python
import datetime

# Simulate sensor data with a function
def get_sensor_data():
    return "23.5, 48.6, 1013.2"  # Example values: temperature, humidity, pressure

# Log data with timestamps
with open('sensor_log.txt', 'a') as file:
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    data = get_sensor_data()
    file.write(f"{timestamp}: {data}\n")
```

### Assignment: Create a Personal Diary Application

Your task is to create a simple console-based diary application that allows users to write and read entries based on dates.

**Requirements:**

1. Implement a function to add a new diary entry with the current date and time.
2. Implement a function to read entries from a specific date.
3. Use appropriate file handling methods to ensure data is stored persistently across sessions.

```python
import datetime

def add_diary_entry():
    """
    Adds a new entry to the diary with the current date and time.
    """
    # Prompt the user to write a diary entry
    # Get the current date and time
    # Open the diary file in append mode and write the entry
    # Inform the user that the entry has been added
    pass  # Remove this line when you add your code

def read_diary_entries():
    """
    Reads and displays diary entries from a specific date.
    """
    # Prompt the user for a date
    # Open the diary file in read mode
    # Read the file's content and find entries for the given date
    # Display the entries for the given date
    pass  # Remove this line when you add your code

def main():
    """
    The main function to run the Personal Diary Application.
    """
    while True:
        print("\nPersonal Diary Application")
        print("1. Add a new diary entry")
        print("2. Read diary entries")
        print("3. Exit")

        choice = input("Choose an option (1/2/3): ")

        if choice == "1":
            add_diary_entry()
        elif choice == "2":
            read_diary_entries()
        elif choice == "3":
            print("Exiting the application. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
```

This structure sets up a simple menu system that allows the user to add new diary entries, read entries from a specific date, or exit the application. The `add_diary_entry` and `read_diary_entries` functions are placeholders where you will implement the logic for handling diary entries.

To complete this assessment, follow these steps:
1. Implement the `add_diary_entry` function to prompt the user for diary content, record the current date and time, and append this information to a diary file.
2. Implement the `read_diary_entries` function to ask the user for a specific date, then read and display all entries from the diary file that match this date.
3. Test the application thoroughly to ensure it correctly adds new entries and can retrieve and display entries for specific dates.

### LinkedIn Post for Achievement

"Day 36 of my coding journey, and I've unlocked the power of file handling in Python! 🗂️ From reading and writing files to managing data logs, I'm now equipped to handle real-world data processing tasks with ease. 📊🐍 #Day36 #100DaysOfCoding #Python #FileHandling #DataProcessing"

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
