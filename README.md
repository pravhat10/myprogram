Write a c program to store information of 10 employee (empid, name , salary) and display the detail of employee whose salary is highest using structure.
#include <stdio.h>

#define MAX_EMPLOYEES 10

struct Employee {
    int empid;
    char name[50];
    float salary;
};

int main() {
    struct Employee employees[MAX_EMPLOYEES];
    int highestSalaryIndex = 0;

    // Input employee details
    for (int i = 0; i < MAX_EMPLOYEES; i++) {
        printf("Enter details for employee %d\n", i + 1);
        printf("Enter employee ID: ");
        scanf("%d", &employees[i].empid);
        printf("Enter name: ");
        scanf("%s", employees[i].name);
        printf("Enter salary: ");
        scanf("%f", &employees[i].salary);

        // Track the highest salary
        if (employees[i].salary > employees[highestSalaryIndex].salary) {
            highestSalaryIndex = i;
        }
    }

    // Display the details of the employee with the highest salary
    printf("\nEmployee with the highest salary:\n");
    printf("Employee ID: %d\n", employees[highestSalaryIndex].empid);
    printf("Name: %s\n", employees[highestSalaryIndex].name);
    printf("Salary: %.2f\n", employees[highestSalaryIndex].salary);

    return 0;
}
