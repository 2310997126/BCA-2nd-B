Design a C++ program for an employee payroll system. Create classes for Employee and Payroll. Users can add employees, enter hours worked, calculate salaries, and generate payroll reports.
#include <iostream>
#include <vector>
#include <string>

using namespace std;

class Employee {
private:
    string name;
    double hourlyRate;
    double hoursWorked;

public:
    Employee(string _name, double _hourlyRate) : name(_name), hourlyRate(_hourlyRate), hoursWorked(0) {}

    void setHoursWorked(double hours) {
        hoursWorked = hours;
    }

    double calculateSalary() {
        return hourlyRate * hoursWorked;
    }

    string getName() const {
        return name;
    }

    double getHoursWorked() const {
        return hoursWorked;
    }
};

class Payroll {
private:
    vector<Employee> employees;

public:
    void addEmployee(const Employee& emp) {
        employees.push_back(emp);
    }

    void generatePayrollReport() const {
        cout << "Payroll Report:" << endl;
        for (const auto& emp : employees) {
            cout << "Employee Name: " << emp.getName() << endl;
            cout << "Hours Worked: " << emp.getHoursWorked() << endl;
            cout << "Salary: $" << emp.calculateSalary() << endl;
            cout << endl;
        }
    }
};

int main() {
    Payroll payroll;

    // Adding employees
    payroll.addEmployee(Employee("John Doe", 20.0));
    payroll.addEmployee(Employee("Jane Smith", 25.0));

    // Entering hours worked
    payroll.addEmployee(Employee("John Doe", 20.0));
    payroll.addEmployee(Employee("Jane Smith", 25.0));

    // Entering hours worked
    payroll.addEmployee(Employee("John Doe", 20.0));
    payroll.addEmployee(Employee("Jane Smith", 25.0));

    // Generating payroll report
    payroll.generatePayrollReport();

    return 0;
}
