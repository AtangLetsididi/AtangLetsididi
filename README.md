def main():
    # Prompt the user for the number of students
    try:
        num_students = int(input("Enter the number of students in the class: "))

        # Check if the entered number is valid
        if num_students < 0:
            print("Please enter a non-negative integer.")
            return

        students = []
        total_grade = 0

        # Loop to get each student's name and grade
        for _ in range(num_students):
            name = input("Enter the student's name: ")

            while True:
                grade = input("Enter the student's grade in a single subject (0-100): ")
                try:
                    # Convert the grade to float for average calculation
                    grade = float(grade)

                    # Check if the grade is within the valid range
                    if 0 <= grade <= 100:
                        students.append((name, grade))
                        total_grade += grade
                        break  # Exit the loop if the grade is valid
                    else:
                        print("Invalid grade. Please enter a number between 0 and 100.")
                except ValueError:
                    print("Invalid input. Please enter a numeric value.")

        # Calculate the average grade
        if num_students > 0:
            average_grade = total_grade / num_students
            print("\nStudents and their grades:")
            for student in students:
                print(f"Name: {student[0]}, Grade: {student[1]}")
            print(f"\nTotal average grade for the class: {average_grade:.2f}")
        else:
            print("No students to calculate an average.")

    except ValueError:
        print("Invalid input! Please enter an integer.")


if __name__ == "__main__":
    main()

# The program starts by asking for the number of students in the class.
# It then checks whether the input given is a non-negative integer, if not, it displays the words "Please enter a non-negative integer."
# It then uses a loop method to gather each student's name and grade.
# The collected information is stored in lists of tuples.
# It then prints out the names and grades of all the students.
GRADE AVERAGE CALCALUATION
# The program will now expect numeric input gor grades and further convecrt them to float for calculations.
# It keeps a running total of the grades. After all grades are collecting, the program calculates the average grade of the class and prints the results. 
# NOTE THAT: Ensure input is valid numeric values, if input is invalid, the program will print the words "Invalid input. Please enter a numeric value."
BASIC VALIDATION
# There is a while loop that continues to prompt for the grade until a valid input, which in ths case is a number between 0 ans 100 is entered into the program.
# If the entered grade falls within the range of 0 and 100 it is valid. Otherwise if it does not fall wwithin the ragnge? It prints "Inval#id grade. Please enter a number between 0 and 100".
# It prompts the user to enter a numeric value if the user enter a nonnumeric value by telling the uer the input is invalid.

# Section B
# Section B
# Define a list of subjects

subjects = ['English', 'Mathematics', 'Economics']
# Create a list to store student data as tuples (name, grades)

students = []
# Function to add student data
def add_student(name, grades):

    students.append((name, grades))
# Function to calculate average grades and display information
def display_student_info():
print("\nStudent Summary:")
for name, grades in students:

        average = sum(grades) / len(grades)
print(f"Name: {name}, Grades: {grades}, Average: {average:.2f}")
# Function to find highest and lowest grades for each subject
def subject_statistics():
for i, subject in enumerate(subjects):

        subject_grades = [grades[i] for _, grades in students]

        highest = max(subject_grades)

        lowest = min(subject_grades)
print(f"\n{subject} - Highest: {highest}, Lowest: {lowest}")
# Add students with their grades

add_student("Mark", [45, 67, 78])

add_student("Matthew", [100, 80, 91])

add_student("John", [98, 54, 76])
# Display student information and statistics

display_student_info()

subject_statistics()

 # We have modified our code to allow each student to have grades for multiple subjects
 # We define the subjects in a list
 # The student's names and grades are stored as tuples in a list called students
 # The add_student function is then used to add the name and grades in a tuple to students
 # The display_student_info function calculates and displays each student's grades and their average.
 # The subject_statistics function calculates and prints the highest and lowest grades for each subject by extracting grades based on their index.
