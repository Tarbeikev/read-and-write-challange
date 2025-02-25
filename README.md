# read-and-write-challange
def modify_content(content):
    # Modify the content in some way (example: convert to uppercase)
    return content.upper()

def read_and_write_file():
    try:
        # Ask the user for the filename
        input_filename = input("Enter the filename to read from: ")
        
        # Open and read the file
        with open(input_filename, "r") as input_file:
            content = input_file.read()
        
        # Modify the content
        modified_content = modify_content(content)
        
        # Write the modified content to a new file
        output_filename = "modified_" + input_filename
        with open(output_filename, "w") as output_file:
            output_file.write(modified_content)
        
        print(f"Modified content has been written to {output_filename}")
    
    except FileNotFoundError:
        print("Error: The file does not exist.")
    except IOError:
        print("Error: Could not read the file.")

# Run the function
read_and_write_file()
