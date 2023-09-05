# lab01_assignment
class Employee:
    def __init__(self, empID,name, age, sal):
        self.empID=empID
        self.name = name
        self.age = age
        self.sal = sal

    def __str__(self):
        return f"{self.empID},{self.name}, {self.age}, ${self.sal}"

def sort_employees(employees, key):
    if key == 1:
        return sorted(employees, key=lambda emp: emp.age)
    elif key == 2:
        return sorted(employees, key=lambda emp: emp.name)
    elif key == 3:
        return sorted(employees, key=lambda emp: emp.sal)
    else:
        return employees

def main():
    employees = [
        Employee("161E90", "Raman", 41, 56000),
        Employee("161F91", "Himadri", 38, 67500),
        Employee("161F99", "Jaya", 51, 82100),
        Employee("171E20", "Tejas", 30, 55000),
        Employee("171G30", "Ajay", 45, 44000)
    ]

    print("Employee Data:")
    for emp in employees:
        print(emp)

    while True:
        print("\nSorting Options:")
        print("1. Sort by Age")
        print("2. Sort by Name")
        print("3. Sort by Salary")
        print("4. Quit")

        choice = int(input("Enter your choice: "))

        if choice == 4:
            break

        employees = sort_employees(employees, choice)

        print("\nSorted Employee Data:")
        for emp in employees:
            print(emp)

if __name__ == "__main__":
    main()
