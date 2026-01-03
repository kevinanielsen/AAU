# Software Specification
A system provided as a web portal, which is used by university students who want to sign up for courses offered by various departments. The students attend the university on their own initiative, and their relation to the system is that they use it to manage their study plan and view grades. The system is primarily an administrative tool responsible for managing the university’s academic structure (Departments, Degrees, Courses) and processing student enrollments. Secondarily, it is a communication medium that professors use to publish course materials and announcements. The system can register a new student with a unique student ID, define a Department (e.g., Computer Science, Biology), and create Courses that belong to a specific Department. A Course is defined by a code, title, and credit value. The system must also manage "Course Offerings," which are specific instances of a Course taught in a specific semester (e.g., "Intro to Java" in Fall 2023 vs. Spring 2024). Students do not link directly to a Course, but rather to a specific Course Offering. When a student signs up, an Enrollment is created which eventually stores the grade received. The portal communicates with a central database. On the student's laptop, the browser caches the schedule for the current semester. The system will be developed by the University Registrar in cooperation with the Faculties. Conflicting requirements regarding class size limits and waitlists may need resolution.
# Class Diagram
![[course-management-system-class-diagram.png]]
# Functional Requirements
## Student Functionality
FR1: The student should be able to sign up for courses offered by various departments.
FR2: The student should be able to manage their study plan.
FR3: The student should be able to view their grades.
FR4: The system should be able to register a new student with a unique student ID.
## Professor Functionality
FR5: The professors should be able to publish course materials.
FR6: The professors should be able to publish announcements.
## Academic Structure
FR7: The system should be able to process student enrollments.
FR8: The system should be able to define a department.
FR9: The system should be able to create a course that belongs to a department, defined by code, title, and credit value.
FR10: The system should be able to manage course offerings, e.g., "Intro to Java" in Fall 2023 vs. Spring 2024.
FR11: The system should link a student to a specific course offering.
FR12: The system should create an enrollment when a student signs up.
FR13: The system should store the grade received in the enrollment.
