# Highest_GWA_Reader
# Python Program to Read a File Containing the Name of 20 Students with their GWA

This Python code reads a file named `students.txt`, which contains the names of 20 students together with their GWA (General Weighted Average). The code outputs the name of the student who got the highest GWA (including the GWA).

## Usage
The code prompts the user to enter "Yes" or "No" to indicate whether they are ready to view the output. If the user enters "Yes," the program reads the `students.txt` file and outputs the name of the student with the highest GWA in a congratulatory message. If the user enters "No," the program prints a message indicating that the user is not ready.

## Sample Output
```
Welcome!
Are you ready? (Yes or No): Yes
Yes, here it is!
Congratulations!
Mat Sanchez got the highest GWA of 1.03! Keep it up!
```

## Code Explanation

```python
# install pyfiglet
import pyfiglet
print("Welcome!")

# ask the user to continue
answer = input("Are you ready? (Yes or No): ")
if answer == "Yes":
    print("Yes, here it is!")  # or do something
elif answer == "No":
    print('You answered No.')  # or do something else
else:
    print(f"Your answer can only be Yes or No. You answered {answer}")

# create ASCII banner
ascii_banner = pyfiglet.figlet_format("CONGRATULATIONS!")
print(ascii_banner)

def student():
    # open file named students.txt(read)
    with open('students.txt', 'r') as students:
    
    # set the variables highest GWA and name of the student with highest GWA
        highest_gwa = 2
        highest_gwa_student = ' '
        
        # read students.txt line by line
        for line in students:
            # split line into name and GWA
            name, gwa = line.strip().split(',')
            
            # convert GWA to float
            gwa = float(gwa)
            
            # check who got the highest GWA in students.txt
            if gwa > highest_gwa:
                highest_gwa = gwa
                highest_gwa_student = name
                
        # print the output with text color
        print('\033[1;35;40m]' + f'{highest_gwa_student} got the highest GWA of {highest_gwa}! Keep it up!')
       
student()
```

- First, the code installs the `pyfiglet` module, which is used to create an ASCII banner.
- The code prompts the user to enter "Yes" or "No" using the `input()` function and stores the answer in the `answer` variable. 
- The code uses conditional statements to check whether the user entered "Yes" or "No" and prints the appropriate message. 
- The code creates an ASCII banner using the `figlet_format()` method of the `pyfiglet` module.
- The `student()` function reads the `students.txt` file line by line using the `with open()` statement and sets the initial values for the variables `highest_gwa` and `highest_gwa_student`.
- The function reads each line of the file using a for loop and splits each line into name and gwa using the strip() and split() methods.
- The gwa variable is converted to a float using the float() method
- Check who got the highest GWA in students.txt using 'if' statement
