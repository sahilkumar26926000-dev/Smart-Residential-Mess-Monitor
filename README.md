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
this program shows that how code is implemented in residential technique;

import exceptionChecker.cutOffSuccessException;
import exceptionChecker.similarIdentityCheckIn;
import model.*;
import provide.*;

import java.time.LocalDate;
import java.time.LocalTime;
import java.util.List;
import java.util.Map;
public class applicableFunction {
    public static void main(String[] args) {
        System.out.println("#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*");
        System.out.println("  SMART RESIDENTAL MESS MONITOR    ");
        System.out.println("#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*");

        // 1. Setup Attendance Service (Lunch cut-off at 10:30 AM)
        AvailableProvider attendanceService = new AvailableProvider(LocalTime.of(10, 30));
        studentGetIn s1 = new studentGetIn("24BCE001", "Ishan Singh");
        studentGetIn s2 = new studentGetIn("25BCE002", "Rakhi Patel");
        studentGetIn s3 = new studentGetIn("25BAI003", "Mukesh Sharma");

        attendanceService.registerStudent(s1);
        attendanceService.registerStudent(s2);
        attendanceService.registerStudent(s3);

        // 2. Student Opt-Out before cut-off
        try {
            attendanceService.updateMealStatus("25BAI003", false, LocalTime.of(9, 40));
            System.out.println("[Attendance] Student Mukesh Sharma opted out successfully.");
        } catch (cutOffSuccessException e) {
            System.err.println("[Error] " + e.getMessage());
        }

        int confirmedCount = attendanceService.getConfirmedHeadcount();
        System.out.println("[Kitchen Portal] Confirmed Headcount: " + confirmedCount);

        // 3. Portion Calculation
        collectingData rice = new collectingData("Steamed Rice");
        rice.addIngredientRatio("Raw Plain Rice", 90.0);

        collectingData dal = new collectingData("Fry Dal");
        dal.addIngredientRatio("Mix Pulse Tadka Dal", 30.0);
        dal.addIngredientRatio("Ghee/Oil", 8.0);

        distributeEngine portionEngine = new distributeEngine();
        Map<String, Double> groceryList = portionEngine.calculateRequirementsInKg(
                List.of(rice, dal), confirmedCount, true
        );

        System.out.println("\n--- Raw Ingredients Scaled with 5% Safety Buffer ---");
        groceryList.forEach((ing, kg) -> System.out.printf(" - %-18s: %.2f kg%n", ing, kg));

        // 4. Meal Turnout & Check-In Validation
        System.out.println("\n--- Check-In Station ---");
        try {
            attendanceService.checkInStudent("24BCE001");
            System.out.println("[Check-In] 24BCE001 validated.");
            attendanceService.checkInStudent("24BCE001"); // Attempt duplicate
        } catch (similarIdentityCheckIn e) {
            System.out.println("[Blocked] " + e.getMessage());
        }

        // 5. Post-Meal Waste Logging
        discardTracker wasteService = new discardTracker();
        wasteService.logWaste(new recordWastes(LocalDate.now(), "Lunch", 2.3, 620.2));

        System.out.println("\n--- Daily Waste Audit ---");
        wasteService.getAllLogs().forEach(System.out::println);
        System.out.printf("Total Waste: %.2f kg | Total Loss: ₹%.2f%n",
                wasteService.getTotalWastedWeight(), wasteService.getTotalFinancialLoss());
    }
}
# output and result 
"Implements views that track student meal choices while recording food waste."
<img width="1919" height="1020" alt="Screenshot 2026-09-12 205852" src="https://github.com/user-attachments/assets/2453b00a-4978-48ae-b585-54956dc799ad" />







