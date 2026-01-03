# Software Specification
A system provided as an app and a web portal, which is used by university students and faculty who want to borrow physical resources from the Central University Library. The users visit the library or use the digital services on their own initiative, and their only relation to the library administration is that they use the system to search for, reserve, and manage loans of educational materials. The system is primarily an administrative tool that is responsible for managing the library’s inventory (books, journals, laptops) and tracking the movement of these items between the library and the members. Secondarily, it is a communication medium that the library uses to notify members about available reservations or overdue fines. The system can register a new library member (student or staff), catalog a new physical item with unique identifiers (ISBN, Asset ID), create a loan transaction, place a reservation on a currently borrowed item, and calculate fines for late returns. The app is running on the member’s smartphone, while the web portal is accessible via standard browsers on campus computers. Both interfaces communicate through the university network with a central database that stores the catalog, member registry, and active loan status. On the smartphone, there is always a cached copy of the member's current active loans and due dates, so they are accessible even if the campus Wi-Fi is weak in certain stack areas. The app includes a barcode scanner to allow students to self-checkout items at designated kiosks and a search filter to locate items by specific floor and shelf numbers. The system will be developed by the University’s IT services in cooperation with the head librarians, administrative staff, and the student union. It may be necessary to resolve conflicting requirements regarding borrowing limits and privacy of reading history. The system will be used by an academic population with generally high IT skills, but potentially high turnover rates every semester.
# Functional Requirements
## User Functionality
FR1: The user should be able to search for educational materials.
FR2: The user should be able to reserve educational materials.
FR3: The user should be able to manage loans of educational materials.
## System Functionality
FR4: The system should be able to manage the library's inventory (books, journals, laptops).
FR5: The system should be able to track movement of the inventory between the library and members.
FR6: The system should be able to register a new member (student of staff).
FR7: The system should be able to catalog a new physical item with unique identifiers (ISBN, Asset ID).
FR8: The system should be able to create a loan transaction.
FR9: The system should be able to place a reservation on a currently borrowed item.
FR9: The system should be able to calculate fines for late returns.
## Student Functionality
FR9: The student should always be able to see their current active loans and due dates even when offline.
FR10: The student should be able to scan a barcode to checkout items at designated kisosk.
FR11: The student should be able to use a search filter to locate items by specific floor and shelf numbers.