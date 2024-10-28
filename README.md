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

# Section C
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

 #Section C
 #Section C
# Define the list of subjects only once at the beginning of your code
subjects_data = ['English', 'Mathematics', 'Economics']

# Create a dictionary to store student data
students_data = {}  # Changed the name from 'students' to 'students_data' to avoid shadowing

# Function to add student data
def add_student(name, subject_grades):
    if name not in students_data:
        students_data[name] = subject_grades
    else:
        print(f"Student {name} already exists.")

# Function to display student information
def display_student_info():
    print("\nStudent Summary:")
    for name, subject_grades in students_data.items():
        for subject, grades in subject_grades.items():
            average = sum(grades) / len(grades) if grades else 0
            print(f"Name: {name}, Subject: {subject}, Grades: {grades}, Average: {average:.2f}")

# Function to find the highest and lowest grades for each subject across all students
def subject_statistics():
    print("\nSubject Statistics:")
    for subject in subjects_data:
        all_grades = []
        for subject_grades in students_data.values():
            if subject in subject_grades:
                all_grades.extend(subject_grades[subject])
        if all_grades:
            highest = max(all_grades)
            lowest = min(all_grades)
            print(f"{subject} - Highest: {highest}, Lowest: {lowest}")
        else:
            print(f"{subject} - No grades available.")

# Add students with their grades
add_student("Mark", {'English': [45, 67, 78], 'Mathematics': [50, 60, 70], 'Economics': [55, 65, 75]})
add_student("Matthew", {'English': [100, 80, 91], 'Mathematics': [90, 85, 95], 'Economics': [88, 92, 79]})
add_student("John", {'English': [98, 54, 76], 'Mathematics': [80, 70, 60], 'Economics': [90, 80, 85]})

# Display student information and statistics
display_student_info()
subject_statistics()
# Replace the list of tuples with a dictionary where each student's name is the key, and their grades, which are also stored in another dictionary are the values - moving fromn list-based structure to ditcionary-base structure.
# Write functions to add new students, update their grades and remove said students.
# Extend the dictionary to handle multiple subjects with each subject storing its grades as a list.
# Implement a fuction that allows the user to see the grades for a specific subject of all students.
# There is a function that allows for the user to search for a specific student by name and retrieve all the grades of that student along with the average.
# add_student(name,subject_grades) adds a new student and their grades.
# display_student_info() displays each student's grades and calculates the average for each subject.
# subjects_statistics calculates the highest and lowest grades for each subject across all students.
# had encountered a problem where a variable was redeclared such that subjects had to be changed to subjects_data and students to students_data to avoid shadowing issues.

# Revised Section C code
# Section C
# Define the list of subjects only once at the beginning of your code
subjects_data = ['English', 'Mathematics', 'Economics']

# Create a dictionary to store student data
students_data = {}

# Main menu system
while True:
    print("\nMenu:")
    print("1. Add or Update Student")
    print("2. Remove Student")
    print("3. Search Student by Name")
    print("4. Display All Students")
    print("5. Subject Statistics")
    print("6. Exit")

    choice = input("Enter your choice: ")

    if choice == '1':
        name = input("Enter student name: ")
        subject_grades = {}

        for subject in subjects_data:
            grades = input(f"Enter grades for {subject} (comma-separated): ").split(',')
            grades = [int(grade) for grade in grades]  # Convert grades to integers
            subject_grades[subject] = grades

        if name in students_data:
            students_data[name].update(subject_grades)  # Update existing grades
            print(f"Updated grades for {name}.")
        else:
            students_data[name] = subject_grades  # Add new student
            print(f"Added {name} to the system.")

    elif choice == '2':
        name = input("Enter the name of the student to remove: ")
        if name in students_data:
            del students_data[name]
            print(f"Removed {name} from the system.")
        else:
            print(f"Student {name} not found.")

    elif choice == '3':
        name = input("Enter the name of the student to search: ")
        if name in students_data:
            print(f"Grades for {name}:")
            for subject, grades in students_data[name].items():
                average = sum(grades) / len(grades) if grades else 0
                print(f"  {subject}: {grades}, Average: {average:.2f}")
        else:
            print(f"Student {name} not found.")

    elif choice == '4':
        print("\nStudent Summary:")
        if not students_data:
            print("No students available.")
        for name, subject_grades in students_data.items():
            for subject, grades in subject_grades.items():
                average = sum(grades) / len(grades) if grades else 0
                print(f"Name: {name}, Subject: {subject}, Grades: {grades}, Average: {average:.2f}")

    elif choice == '5':
        print("\nSubject Statistics:")
        for subject in subjects_data:
            all_grades = []
            for subject_grades in students_data.values():
                if subject in subject_grades:
                    all_grades.extend(subject_grades[subject])
            if all_grades:
                highest = max(all_grades)
                lowest = min(all_grades)
                print(f"{subject} - Highest: {highest}, Lowest: {lowest}")
            else:
                print(f"{subject} - No grades available.")

    elif choice == '6':
        print("Exiting program.")
        break

    else:
        print("Invalid choice. Please try again.")
# Funtions were removed. 
# A menu that allows the user to add, remove, update a value of a student was added.
# It also allows the user to view subject specific results and search for students grades by name.

# Section D

# Section A
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

# Section B
# Define a list of subjects
subjects = ['English', 'Mathematics', 'Economics']

# Create a list to store student data as tuples (name, grades)
students_list = []

# Function to add student data
def add_student(name, grades):
    students_list.append((name, grades))

# Function to calculate average grades and display information
def display_student_info():
    print("\nStudent Summary:")
    for name, grades in students_list:
        average = sum(grades) / len(grades)
        print(f"Name: {name}, Grades: {grades}, Average: {average:.2f}")

# Function to find highest and lowest grades for each subject
def subject_statistics():
    for i, subject in enumerate(subjects):
        subject_grades = [grades[i] for _, grades in students_list]
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

# Section C
# Define the list of subjects only once at the beginning of your code
subjects_data = ['English', 'Mathematics', 'Economics']

# Create a dictionary to store student data
students_data = {}

# Function to add or update student data
def add_or_update_student():
    name = input("Enter student name: ")
    subject_grades = {}

    for subject in subjects_data:
        grades = input(f"Enter grades for {subject} (comma-separated): ").split(',')
        grades = [int(grade) for grade in grades]  # Convert grades to integers
        subject_grades[subject] = grades

    if name in students_data:
        students_data[name].update(subject_grades)  # Update existing grades
        print(f"Updated grades for {name}.")
    else:
        students_data[name] = subject_grades  # Add new student
        print(f"Added {name} to the system.")

# Function to remove a student
def remove_student():
    name = input("Enter the name of the student to remove: ")
    if name in students_data:
        del students_data[name]
        print(f"Removed {name} from the system.")
    else:
        print(f"Student {name} not found.")

# Function to search for a student by name and retrieve their grades and average
def search_student():
    name = input("Enter the name of the student to search: ")
    if name in students_data:
        print(f"Grades for {name}:")
        for subject, grades in students_data[name].items():
            average = sum(grades) / len(grades) if grades else 0
            print(f"  {subject}: {grades}, Average: {average:.2f}")
    else:
        print(f"Student {name} not found.")

# Function to display all students' information
def display_all_students():
    print("\nStudent Summary:")
    if not students_data:
        print("No students available.")
    for name, subject_grades in students_data.items():
        for subject, grades in subject_grades.items():
            average = sum(grades) / len(grades) if grades else 0
            print(f"Name: {name}, Subject: {subject}, Grades: {grades}, Average: {average:.2f}")

# Function to show subject statistics (highest and lowest grades)
def subject_statistics():
    print("\nSubject Statistics:")
    for subject in subjects_data:
        all_grades = []
        for subject_grades in students_data.values():
            if subject in subject_grades:
                all_grades.extend(subject_grades[subject])
        if all_grades:
            highest = max(all_grades)
            lowest = min(all_grades)
            print(f"{subject} - Highest: {highest}, Lowest: {lowest}")
        else:
            print(f"{subject} - No grades available.")

# Main menu function
def menu():
    while True:
        print("\nMenu:")
        print("1. Add or Update Student")
        print("2. Remove Student")
        print("3. Search Student by Name")
        print("4. Display All Students")
        print("5. Subject Statistics")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            add_or_update_student()
        elif choice == '2':
            remove_student()
        elif choice == '3':
            search_student()
        elif choice == '4':
            display_all_students()
        elif choice == '5':
            subject_statistics()
        elif choice == '6':
            print("Exiting program.")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the menu
menu()

# This section is simply a more revised version of sections A, B and C with functions and error handling

# Section E

# Class representing a single student
class Student:
    def __init__(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        if subject not in self.grades:
            self.grades[subject] = []
        self.grades[subject].append(grade)

    def calculate_average(self):
        total_grades = 0
        total_subjects = 0
        for subject_grades in self.grades.values():
            total_grades += sum(subject_grades)
            total_subjects += len(subject_grades)
        return total_grades / total_subjects if total_subjects > 0 else 0

    def print_details(self):
        print(f"Student Name: {self.name}")
        for subject, grades in self.grades.items():
            print(f"  {subject}: {grades}")
        print(f"  Average Grade: {self.calculate_average():.2f}")

# Class representing the gradebook containing multiple students
class Gradebook:
    def __init__(self):
        self.students = []

    def add_student(self, name):
        student = self.find_student(name)
        if student:
            print(f"Student {name} already exists.")
        else:
            new_student = Student(name)
            self.students.append(new_student)
            print(f"Student {name} added.")

    def remove_student(self, name):
        student = self.find_student(name)
        if student:
            self.students.remove(student)
            print(f"Student {name} removed.")
        else:
            print(f"Student {name} not found.")

    def find_student(self, name):
        for student in self.students:
            if student.name == name:
                return student
        return None

    def add_grade_to_student(self, name, subject, grade):
        student = self.find_student(name)
        if student:
            student.add_grade(subject, grade)
            print(f"Grade {grade} added to {subject} for {name}.")
        else:
            print(f"Student {name} not found.")

    def sort_students_by_average(self):
        return sorted(self.students, key=lambda student: student.calculate_average(), reverse=True)

    def sort_students_by_subject_grade(self, subject):
        return sorted(self.students, key=lambda student: student.grades.get(subject, [0]), reverse=True)

    def print_all_students(self):
        if not self.students:
            print("No students in the gradebook.")
        for student in self.students:
            student.print_details()

# Testing the OOP implementation
def main():
    gradebook = Gradebook()

    # Add students
    gradebook.add_student("Mark")
    gradebook.add_student("John")
    gradebook.add_student("Matthew")

    # Add grades
    gradebook.add_grade_to_student("Mark", "English", 85)
    gradebook.add_grade_to_student("Mark", "Mathematics", 90)
    gradebook.add_grade_to_student("John", "English", 70)
    gradebook.add_grade_to_student("John", "Mathematics", 80)
    gradebook.add_grade_to_student("Matthew", "English", 95)
    gradebook.add_grade_to_student("Matthew", "Mathematics", 88)

    # Print all students
    print("\nAll students:")
    gradebook.print_all_students()

    # Sort students by average and print
    print("\nStudents sorted by average grade:")
    sorted_students = gradebook.sort_students_by_average()
    for student in sorted_students:
        student.print_details()

    # Remove a student
    gradebook.remove_student("John")

    # Print updated student list
    print("\nUpdated student list:")
    gradebook.print_all_students()

if __name__ == "__main__":
    main()

# The STUDENT CLASS does the following: 
# Manages individual student data and methods for adding grades and calculating the average.
# add_grade() adds grades for a given subject.
# calculate_average() calculates the overall average of the student.
# print_details() prints the student’s details including their grades and average.
# The Gradebook Class breaks odwn into:
# Manages a list of students and provides functionality to:
# Add a student.
# Remove a student.
#Find a student by name.
# Add grades to a specific student.
# Sort students by average grade or by grades in a specific subject.
# Print all student details.
# Advanced Operations:
# Searching: The find_student() method checks if a student exists by name.
# Sorting: Methods like sort_students_by_average() and sort_students_by_subject_grade() sort students based on their average or subject-specific grades.
# Removal: The remove_student() method allows removing a student from the gradebook.
# Testing and Usage:
# The main() function demonstrates adding students, assigning grades, printing the gradebook, sorting students by averages, and removing a student.

# Section F

class StudentNotFoundError(Exception):
    """Raised when a student is not found in the gradebook."""
    pass


class InvalidGradeError(Exception):
    """Raised when an invalid grade is entered."""
    pass


# Class representing a single student
class Student:
    def __init__(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        if not (0 <= grade <= 100):
            raise InvalidGradeError(f"Grade must be between 0 and 100. Invalid grade: {grade}")
        if subject not in self.grades:
            self.grades[subject] = []
        self.grades[subject].append(grade)

    def calculate_average(self):
        total_grades = sum([sum(grades) for grades in self.grades.values()])
        total_subjects = sum([len(grades) for grades in self.grades.values()])
        return total_grades / total_subjects if total_subjects > 0 else 0

    def print_details(self):
        print(f"Student Name: {self.name}")
        for subject, grades in self.grades.items():
            print(f"  {subject}: {grades}")
        print(f"  Average Grade: {self.calculate_average():.2f}")


# Class representing the gradebook containing multiple students
class Gradebook:
    def __init__(self):
        self.students = []

    def add_student(self, name):
        if self.find_student(name):
            print(f"Student {name} already exists.")
        else:
            new_student = Student(name)
            self.students.append(new_student)
            print(f"Student {name} added.")

    def remove_student(self, name):
        student = self.find_student(name)
        if student:
            self.students.remove(student)
            print(f"Student {name} removed.")
        else:
            raise StudentNotFoundError(f"Student {name} not found.")

    def find_student(self, name):
        for student in self.students:
            if student.name == name:
                return student
        return None

    def add_grade_to_student(self, name, subject, grade):
        student = self.find_student(name)
        if student:
            try:
                student.add_grade(subject, grade)
                print(f"Grade {grade} added to {subject} for {name}.")
            except InvalidGradeError as e:
                print(e)
        else:
            raise StudentNotFoundError(f"Student {name} not found.")

    # Sorting students by average grade using Bubble Sort
    def sort_students_by_average(self):
        n = len(self.students)
        for i in range(n):
            for j in range(0, n - i - 1):
                if self.students[j].calculate_average() < self.students[j + 1].calculate_average():
                    self.students[j], self.students[j + 1] = self.students[j + 1], self.students[j]
        return self.students

    # Sorting students by name using Bubble Sort
    def sort_students_by_name(self):
        n = len(self.students)
        for i in range(n):
            for j in range(0, n - i - 1):
                if self.students[j].name > self.students[j + 1].name:
                    self.students[j], self.students[j + 1] = self.students[j + 1], self.students[j]
        return self.students

    def search_student_by_name(self, name):
        student = self.find_student(name)
        if student:
            student.print_details()
        else:
            raise StudentNotFoundError(f"Student {name} not found.")

    def print_all_students(self):
        if not self.students:
            print("No students in the gradebook.")
        for student in self.students:
            student.print_details()


# Main function to interact with the system
def main():
    gradebook = Gradebook()

    while True:
        print("\nMenu:")
        print("1. Add Student")
        print("2. Remove Student")
        print("3. Add Grade")
        print("4. Search Student by Name")
        print("5. Display All Students")
        print("6. Sort Students by Name")
        print("7. Sort Students by Average Grade")
        print("8. Exit")

        choice = input("Enter your choice: ")

        try:
            if choice == '1':
                name = input("Enter student name: ")
                gradebook.add_student(name)

            elif choice == '2':
                name = input("Enter student name to remove: ")
                gradebook.remove_student(name)

            elif choice == '3':
                name = input("Enter student name: ")
                subject = input("Enter subject: ")
                grade = float(input("Enter grade: "))
                gradebook.add_grade_to_student(name, subject, grade)

            elif choice == '4':
                name = input("Enter student name to search: ")
                gradebook.search_student_by_name(name)

            elif choice == '5':
                gradebook.print_all_students()

            elif choice == '6':
                sorted_by_name = gradebook.sort_students_by_name()
                print("\nStudents sorted by name:")
                for student in sorted_by_name:
                    student.print_details()

            elif choice == '7':
                sorted_by_average = gradebook.sort_students_by_average()
                print("\nStudents sorted by average grade:")
                for student in sorted_by_average:
                    student.print_details()

            elif choice == '8':
                print("Exiting the program.")
                break

            else:
                print("Invalid choice. Please try again.")

        except (StudentNotFoundError, InvalidGradeError) as e:
            print(f"Error: {e}")
        except ValueError:
            print("Invalid input. Please enter a valid value.")


if __name__ == "__main__":
    main()

# This code implements a gradebook system with functionalities to manage students and their grades using an object-oriented approach. Here's a detailed explanation:
# Custom Exceptions:
# StudentNotFoundError: Raised when a student is not found in the gradebook (e.g., during removal or searching).
# InvalidGradeError: Raised when an invalid grade is entered (outside the 0-100 range).
# Breakdown of Classes
# Student: Represents a single student with attributes:
# name: Student's name (string)
# grades: Dictionary to store grades for different subjects (subject: list of grades)
# Methods:
# add_grade(subject, grade): Adds a grade to a specific subject, raising InvalidGradeError for invalid grades.
# calculate_average(): Calculates the overall average grade for the student.
# print_details(): Prints the student's name, grades for each subject, and average grade.
# Gradebook: Represents the gradebook system, managing multiple students and their grades.
# Attributes of Gradebook:
# students: List containing Student objects.
# Methods:
# add_student(name): Adds a new student to the gradebook, checking for duplicates.
# remove_student(name): Removes a student from the gradebook, raising StudentNotFoundError if not found.
# find_student(name): Finds a student by name and returns the Student object (or None if not found).
# add_grade_to_student(name, subject, grade): Adds a grade to a specific subject for a student, handling potential StudentNotFoundError and InvalidGradeError.
# sort_students_by_average(): Sorts the students based on their average grade (using Bubble Sort - consider more efficient algorithms for larger datasets).
# sort_students_by_name(): Sorts the students alphabetically by name (using Bubble Sort).
# search_student_by_name(name): Searches for a student by name and displays their details, raising StudentNotFoundError if not found.
# print_all_students(): Prints information for all students in the gradebook.
# Main Function (main()):

# Creates a Gradebook instance.
# Presents a menu with options to:
# Add student
# Remove student
# Add grade
# Search student by name
# Display all students
# Sort by name
# Sort by average
# Exit
# Takes user input for their choice.
# Uses a try-except block to handle potential exceptions:
# Catches StudentNotFoundError and InvalidGradeError raised during operations, displaying informative error messages.
# Catches ValueError for invalid user input (e.g., non-numeric grade) and prompts the user to enter a valid value.

# Improvements:
# Sorting: Consider using more efficient sorting algorithms (e.g., Timsort) for larger datasets.
# Error Handling: You can add more specific exception handling (e.g., separate exception for missing student name during search).
# This code effectively demonstrates object-oriented programming principles for managing student grades. It provides functionalities for adding, removing, searching, and displaying student information. By incorporating the suggested improvements, you can enhance its performance and user experience.










