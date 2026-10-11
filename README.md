# Aviation_flight_dispatcher_java
simple Java program built to simulate an airline flight dispatch weather safety check.

import java.util.Scanner;

public class SimpleDispatcher {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("=== AIRLINE DISPATCH SYSTEM ===");
       
        // 1. Take destination airport input
        System.out.print("Enter Destination Airport Code (e.g., DEL, BOM, BLR): ");
        String airport = scanner.nextLine().toUpperCase();

        // 2. Take wind speed input
        System.out.print("Enter Current Wind Speed (in knots): ");
        int windSpeed = scanner.nextInt();

        System.out.println("\n---------------------------------");
        System.out.println("Analyzing Flight Plan for: " + airport);
        System.out.println("Wind Condition: " + windSpeed + " Knots");

        // 3. Dispatch Decision Logic (If-Else Rules)
        if (windSpeed > 25) {
            System.out.println("STATUS: DISPATCH DENIED!");
            System.out.println("Reason: Stormy conditions. Wind speed exceeds safe landing limits.");
        } else if (windSpeed >= 15 && windSpeed <= 25) {
            System.out.println(" STATUS: DISPATCH APPROVED WITH CAUTION");
            System.out.println("Reason: Strong winds. Add extra contingency fuel for the flight.");
        } else {
            System.out.println(" STATUS: DISPATCH APPROVED");
            System.out.println("Reason: Weather is clear and stable for departure.");
        }
        System.out.println("---------------------------------");

        scanner.close();
    }
}
 