# Software Specification
A system provided as a mobile app, which is used by electric vehicle (EV) drivers who want to locate charging stations and charge their vehicles at the GreenCharge network. The drivers use the charging network on their own initiative, and their only relation to GreenCharge is that they create an account to initiate charging sessions and pay for energy consumed. The system is primarily an administrative tool that is responsible for authenticating users at physical charging pillars, monitoring the energy transfer in real-time, and processing billing based on kilowatt-hours (kWh) used. Secondarily, it is a communication medium that drivers use to report broken chargers and receive receipts for their transactions. The system can register a new driver profile with payment details, manage a list of the driver’s vehicles (Make, Model, Connector Type), start and stop a charging session, invoice the user, and maintain a history of energy consumption. The app is running on the driver’s smartphone. It communicates through a cellular network with a cloud server that manages the state of all charging pillars (Available, Occupied, Out of Order) and user accounts. On the smartphone, there is always a cached copy of the driver's charging history from the last 30 days, so receipts are viewable even in underground parking garages where signal is lost. The app includes support for GPS-based routing to the nearest available charger and an NFC feature to unlock specific charging pillars by tapping the phone. The system will be developed by GreenCharge’s engineering team in cooperation with hardware manufacturers, energy providers, and a focus group of early-adopter EV drivers. It may be necessary to resolve conflicting requirements regarding the complexity of tariff structures versus the simplicity of the user interface. The app will be used by the general public with varying degrees of technical knowledge regarding electrical specifications.
# Functional Requirements
## Driver Functionality
FR1: The driver should be able to create an account.
FR2: The driver should be able to start a charging session.
FR3: The driver should be able to stop a charging session.
FR4: The driver should be able to receive and pay for invoices.
FR5: The driver should be able to see a history of energy consumption and receipts, even when offline.
FR6: The driver should be able to see the state of all charging pillars (available, occupied, out of order).
FR7: The driver should be able to see a route to the nearest available charger.
FR8: The driver should be able to use NFC to unlock charges by tapping the phone.
FR9: The driver should be able to report broken chargers.
FR10: The driver should be able to receive receipts for their transactions.
FR11: The driver should be able to make a driver profile with payment details.
FR12: The driver should be able to add and remove their vehicles (make, model, and connector type).
## System Functionality
FR13: The system should be able to monitor the energy transfer in real time.
FR14: The system should be able to process billing based on usage in kWh.
# Class Diagram
![[ev-class-diagram.png]]