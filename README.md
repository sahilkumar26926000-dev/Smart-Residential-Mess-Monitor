# Smart-Residential-Mess-Monitor
College hostels and university dining halls face a big guessing game every day when making food. Because they do not know exactly how many students will show up for breakfast, lunch, or dinner, they experience two major problems at the same time: massive food waste and food shortages.
# Project Blueprint
This complete implementation and documentation package fulfills all requirements from the guidelines: the 3 required modules, 4 non-functional requirements, 5 structured classes, custom exceptions and unit tests.
# Problem Statement
❖ Massive Food Waste: Inflexible meal prep quotas 
cause 20–35% excess food disposal daily. 
❖ Manual Record Errors: Physical register logbooks 
lead to meal slip manipulation, duplicate billing, and 
sluggish queue throughput during peak hours. 
❖ Lack of Real-Time Feedback: Wardens and caterers 
receive no real-time telemetry on leftover inventory, 
menu popularity, or mess hygiene/stock conditions.
# functional Requirements 
User Authentication & profiles:
Role-based 
access for Students, Mess Managers, Kitchen Staff and Admins.
Meal Opt-In/Opt-Out Management: 
Students can mark leaves or cancel upcoming meals up to 3 hours prior to cooking cycles.package model;
Automated Waste Monitoring
Here, automatically detects the amount waste produce every days 
Reliability & Availability: System uptime >= 99.5% 
during scheduled dining windows (Breakfast, Lunch, 
Dinner).

# System Architecture
The system adopts a modern Three-Tier Architecture: 
● Presentation Tier: Responsive Web & Mobile 
frontend built with React.js or Flutter. 
● Application Tier: RESTful API backend using 
Imanaging business logic, notification triggers, and edge 
communication. 
● Data Tier: Relational database (PostgreSQL/MySQL) 
storing transaction records, student accounts, and 
sensor logs. 
● Edge / IoT Layer: ESP32/Arduino microcontroller 
connected to an RC522 RFID reader and an HX711 
Load Cell amplifier for waste bins, publishing logs via 
MQTT/HTTPS.
# Design Diagram

Mark Meal Attendance, Skip Meal, Log Waste Weight, 
Publish Menu, Review Analytics, View Monthly Bill.
ER Diagram : ->
● Users: user_id , name, email,  
● Meals: meal_id , date, meal_type (Breakfast/Lunch/Dinner), 
menu_description. 
● MealBookings: booking_id , user_id , meal_id , status 
(Opted-in/Opted-out/Attended), timestamp. 
● WasteLogs: log_id , meal_id , waste_weight_kg, recorded_at

# Testing Approach
The testing strategy uses automated unit tests written in pure Java. A 
dedicated test driver class  executes test cases against the core methods 
of the mess system, checking outputs against expected conditions and 
printing clear PASS/FAIL results to the console. 
# Main Program
this program shows that how code is implemented in residential technique





