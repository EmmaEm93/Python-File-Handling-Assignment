# Python-File-Handling-Assignment
Demonstrate your understanding of Python file handling by completing the following tasks.

Tasks:

File Creation:
Create a Python script (file_handling_assignment.py) that does the following:
Creates a new text file named "my_file.txt" in write mode ('w').
Write at least three lines of text to the file, including a mix of strings and numbers.




File Reading and Display:
Enhance your script to read the contents of "my_file.txt" and display them on the console.




File Appending:
Modify the script to open "my_file.txt" in append mode ('a').
Append three additional lines of text to the existing content.




Error Handling:
Implement error handling using try, except, and finally blocks to manage potential file-related exceptions (e.g., FileNotFoundError, PermissionError).


# file_handling_assignment.py

def create_file():
    try:
        with open('my_file.txt', 'w') as file:
            file.write("Hello, this is line 1.\n")
            file.write("The number 42 is my favorite.\n")
            file.write("Python is fun!\n")
        print("File created and content written successfully.")
    except Exception as e:
        print(f"Error occurred while creating the file: {e}")

def read_file():
    try:
        with open('my_file.txt', 'r') as file:
            content = file.read()
            print("File content:")
            print(content)
    except FileNotFoundError:
        print("Error: File not found. Please create the file first.")
    except PermissionError:
        print("Error: You do not have permission to read this file.")
    except Exception as e:
        print(f"Error occurred while reading the file: {e}")

def append_to_file():
    try:
        with open('my_file.txt', 'a') as file:
            file.write("Appending a new line 1.\n")
            file.write("Appending another number: 99.\n")
            file.write("Final line of the file.\n")
        print("Content appended successfully.")
    except FileNotFoundError:
        print("Error: File not found. Please create the file first.")
    except PermissionError:
        print("Error: You do not have permission to append to this file.")
    except Exception as e:
        print(f"Error occurred while appending to the file: {e}")

if __name__ == "__main__":
    create_file()
    read_file()
    append_to_file()
    read_file()  # Display content again after appending
