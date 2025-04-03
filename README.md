# python-assignment-week-4
File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.

def modify_content(content):
    """
    Modify the content as needed. This example converts text to uppercase.
    """
    return content.upper()


def read_and_modify_file():
    input_filename = input("Enter the input filename: ")
    output_filename = "modified_" + input_filename
    
    try:
        with open(input_filename, 'r', encoding='utf-8') as infile:
            content = infile.read()

        modified_content = modify_content(content)

        with open(output_filename, 'w', encoding='utf-8') as outfile:
            outfile.write(modified_content)

        print(f"Modified content written to {output_filename}")
    except FileNotFoundError:
        print("Error: Input file not found.")
    except IOError:
        print("Error: Unable to read or write to file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")




