class Student:
    def __init__(self, student_id, name):
        self.student_id = student_id
        self.name = name
        self.grades = {}

    def add_grade(self, course, grade):
        self.grades[course] = grade

    def calculate_gpa(self):
        if not self.grades:
            return 0
        total_sum = sum(self.grades.values())
        return total_sum / len(self.grades)

    def get_letter_grade(self, numeric_grade):
        if numeric_grade < 40:
            return 'F'
        elif numeric_grade < 50:
            return 'D'
        elif numeric_grade < 60:
            return 'C'
        elif numeric_grade < 70:
            return 'B'
        else:
            return 'A'

def main():
    students = []

    john = Student("0013", "John")
    john.add_grade("PHE", 60)
    students.append(john)

    samuel = Student("0014", "Samuel")
    samuel.add_grade("Agric science", 45)
    students.append(samuel)

    paul = Student("0015", "Paul")
    paul.add_grade("CRS", 77)
    students.append(paul)

    praise = Student("0016", "Praise")
    praise.add_grade("Further Maths", 55)
    students.append(praise)

    joseph = Student("0017", "Joseph")
    joseph.add_grade("Quantitative Reasoning", 70)
    students.append(joseph)

    jude = Student("0018", "Jude")
    jude.add_grade("Verbal Reasoning", 90)
    students.append(jude)
    
    Jacob = Student("0019", "Jacob")
    Jacob.add_grade("Socail Studies", 90)
    students.append(Jacob)
    
    Emmanuel  = Student("0020", "Jacob")
    Emmanuel.add_grade("Mathematics", 39)
    students.append(Emmanuel)
    
    print("\n\nGrading Results:\n")
    for student in students:
        print(f"Name: {student.name}, ID: {student.student_id}")
        for course, grade in student.grades.items():
            letter_grade = student.get_letter_grade(grade)
            print(f"Course: {course}, Grade: {grade}, Letter Grade: {letter_grade}")
        print("\n")

if __name__ == "__main__":
    main()
