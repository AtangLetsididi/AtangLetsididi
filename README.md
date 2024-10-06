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

