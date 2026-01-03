# Software Specification
A system provided as a desktop application used by HR managers at "TechCorp" to calculate monthly payroll. The HR manager uses the system to input employee hours and approve the final payout. The system is responsible for calculating the net salary based on gross hours, tax rates, and pension deductions. It is critical that the system validates that no employee has worked more than 60 hours a week, as this is illegal. The system can register a new employee (Name, ID, Hourly Rate) and store this data in a legacy SQL database. When the HR manager clicks "Process," the system iterates through the employee list, applies the "Standard Tax Algorithm v2.0," and generates a PDF payslip for each employee. The application also allows the HR manager to manually override a tax rate if an exception occurs. The system automatically emails the PDF payslip to the employee.
# Functional Requirements
## HR Manager Functionality
FR1: The HR manager should be able to input employee hours.
FR2: The HR manager should be able to see a calculated net salary based on gross hours, tax rates, and pension deductions.
FR3: The HR manager should be able to approve final payouts.
FR4: The HR manager should be able to register a new employee (Name, ID, Hourly Rate).
FR5: The HR manager should be able to manually override a tax rate.
## System Functionality
FR6: The system should ensure that no employee works more than 60 hours a week.
FR7: The system should generate a PDF payslip for each employee when a button is clicked.
FR8: The system should automatically email the PDF payslip to employees.