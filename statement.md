# Problem Statemnet
Residential hostels and university campuses face recurring challenges in mess management, including unpredictable meal attendance, extensive food wastage, manual dietary tracking, and slow grievance resolution. Traditional paper logs or disjointed spreadsheets fail to provide real-time visibility into daily student dining turnouts, leading to either critical shortages or massive surpluses of prepared food.
# Scope of the Project
The Smart Mess Residential Monitor is a Java-based desktop/backend application designed to automate hostel mess operations. The system handles:
* Resident check-ins and authentication per meal session.
* Meal plan selection, attendance logging, and dietary preference management.
* Real-time consumption analytics to assist kitchen staff in forecasting meal demand.
* Issue reporting and feedback logging for residential mess committees.
* The current scope focuses on core business logic, object-oriented data models, file I/O or database persistence, and console/GUI reporting within a local hostel network environment.

# Target Usrs
Hostel Residents / Students: To view daily menus, check into meals, log dietary preferences, and submit feedback.
Mess Contractors & Kitchen Staff: To access real-time meal counts, monitor grocery consumption, and reduce food waste.
Hostel Wardens & Mess Committee Members: To track attendance trends, oversee billing/rations, and resolve quality complaints.

# High-Level Features
Resident Profile & Meal Management: CRUD operations for resident records, meal plan subscriptions, and dietary preferences.
Smart Session Check-in System: Fast meal validation (Breakfast, Lunch, Snacks, Dinner) preventing duplicate entries per session.
Inventory & Consumption Forecaster: Basic algorithmic estimation of ingredients needed based on past attendance trends.
Mess Feedback & Grievance Module: Categorized feedback collection (hygiene, taste, portion) with status tracking.
Administrative Analytics & Reporting: Automated generation of daily attendance, wastage summaries, and billing export reports.
