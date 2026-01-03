# Software Specification
A system provided as a website and mobile app, which is used by guests who want to book accommodation at the "Grand Stay" hotel chain. The guests travel on their own initiative, and their relation to Grand Stay is that they create a profile to search for availability and manage reservations. The system is primarily an administrative tool responsible for managing the hotel’s inventory of rooms and processing bookings. Secondarily, it is a communication medium used to send confirmation emails and post-stay surveys. The system can register a new Hotel property (name, address), and manage the Rooms inside that Hotel. Each Room is identified by a room number and a type (e.g., Single, Double, Suite). It is critical to note that if a Hotel building is sold or demolished, the Rooms associated with it no longer exist in the system. A Guest can make a Booking, which reserves a specific Room Type for a specific date range. Once the stay is complete, an Invoice is generated linked to that Booking, detailing the room cost and any extra services (like room service). The app communicates with a central reservation system. The system allows guests to view past invoices. The app will be developed by Grand Stay’s digital team. Conflicting requirements regarding dynamic pricing and cancellation policies may need resolution.
# Class Diagram
![[hotel-class-diagram.png]]
# Functional Requirements
## Guest Functionality
FR1: The guest should be able to create a profile.
FR2: The guest should be able to search for accommodation availability.
FR3: The guest should be able to view, create, cancel reservations.
FR4: The guest should be able to make a booking with a specified room type and date range.
FR5: The guest should be able to view past invoices.
## System Functionality
FR6: The system should process bookings.
FR7: The system should send confirmation emails to guests.
FR8: The system should send post-stay surveys on email to guests.
FR9: The system should generate an invoice when a stay is complete.
## Staff Functionality
FR10: The staff should be able to register a new hotel with name and address.
FR11: The staff should be able to view, create, and delete the hotel's inventory of rooms.