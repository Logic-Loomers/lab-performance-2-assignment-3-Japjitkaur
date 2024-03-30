[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Fmb6W2KK)
Design a C++ program for an employee payroll system. Create classes for Employee and Payroll. Users can add employees, enter hours worked, calculate salaries, and generate payroll reports.
#include <iostream>
using namespace std;
const int MAX_EMPLOYEES = 100;
class Employee {
public:
    string name;
    int id;
    double hourlyRate;
};
class Payroll {
public:
    Employee employees[MAX_EMPLOYEES];
    int numEmployees;
    Payroll() {
        numEmployees = 0;
    }
    void addEmployee(string name, int id, double hourlyRate) {
        if (numEmployees < MAX_EMPLOYEES) {
            employees[numEmployees].name = name;
            employees[numEmployees].id = id;
            employees[numEmployees].hourlyRate = hourlyRate;
            numEmployees++;
        } else {
            cout << "Cannot add more employees. Maximum limit reached." << endl;
        }
    }
    double calculateSalary(int id, double hoursWorked) {
        for (int i = 0; i < numEmployees; i++) {
            if (employees[i].id == id) {
                return employees[i].hourlyRate * hoursWorked;
            }
        }
    }
    void generatePayrollReport() {
        cout << "Payroll Report:" << endl;
        for (int i = 0; i < numEmployees; i++) {
            cout << "Name: " << employees[i].name << ", ID: " << employees[i].id << endl;  } }
};
int main() {
    Payroll payroll;
    payroll.addEmployee("John Doe", 1, 10.0);
    payroll.addEmployee("Jane Smith", 2, 12.0);
    payroll.addEmployee("Mike Johnson", 3, 15.0);
    double hoursWorked = 40.0;
    int employeeId = 2;
    double salary = payroll.calculateSalary(employeeId, hoursWorked);
    cout << "Salary for employee with ID " << employeeId << ": $" << salary << endl;
    payroll.generatePayrollReport();
}
