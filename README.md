import java.util.Scanner;

public class TravelTicketBooking {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Display available travel plans
        System.out.println("Welcome to our Travel Ticket Booking App!");
        System.out.println("Choose a Travel Plan:");
        System.out.println("1. Plan A: Beach Vacation - 7 Days");
        System.out.println("2. Plan B: Mountain Trek - 5 Days");
        System.out.println("3. Plan C: City Tour - 3 Days");
        System.out.print("Enter the number of the plan you want to choose (1/2/3): ");
        int planChoice = scanner.nextInt();

        // Input validation for plan choice
        if (planChoice < 1 || planChoice > 3) {
            System.out.println("Invalid choice! Exiting...");
            return;
        }

        // Proceed to ticket booking page
        System.out.print("How many people are you booking tickets for? ");
        int numberOfPeople = scanner.nextInt();
        scanner.nextLine();  // Consume newline left-over from nextInt()

        // Collect personal details (age and gender) for each person
        String[] names = new String[numberOfPeople];
        int[] ages = new int[numberOfPeople];
        String[] genders = new String[numberOfPeople];

        for (int i = 0; i < numberOfPeople; i++) {
            System.out.print("Enter name of person " + (i + 1) + ": ");
            names[i] = scanner.nextLine();
            System.out.print("Enter age of " + names[i] + ": ");
            ages[i] = scanner.nextInt();
            scanner.nextLine();  // Consume newline left-over
            System.out.print("Enter gender of " + names[i] + " (Male/Female/Other): ");
            genders[i] = scanner.nextLine();
        }

        // Proceed to payment page
        int totalCost = numberOfPeople * 1350;
        System.out.println("\n--- Payment Page ---");
        System.out.println("Total number of tickets: " + numberOfPeople);
        System.out.println("Total cost: " + totalCost + " INR");
        System.out.print("Click submit to confirm your booking (Y/N): ");
        String submit = scanner.nextLine();

        if (submit.equalsIgnoreCase("Y")) {
            System.out.println("\nThanks for booking a trip with us!");
        } else {
            System.out.println("Booking has been canceled.");
        }

        scanner.close();
    }
}
