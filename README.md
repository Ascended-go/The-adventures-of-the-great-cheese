# The-adventures-of-the-great-cheese
Cheese
import java.util.Random;
import java.util.Scanner;

public class CheeseGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        // Game variables
        int cheesePosition = 0;
        int mousePosition = 5;
        boolean gameRunning = true;

        System.out.println("Welcome to the Cheese Escape Game!");
        System.out.println("You are a piece of cheese trying to escape without getting caught by a mouse.");

        while (gameRunning) {
            System.out.println("Your position: " + cheesePosition);
            System.out.println("Mouse position: " + mousePosition);
            System.out.println("Enter 'move' to move forward or 'stay' to stay in place:");

            String playerAction = scanner.nextLine();

            if (playerAction.equalsIgnoreCase("move")) {
                cheesePosition++;
            }

            // Mouse moves randomly
            if (random.nextBoolean()) {
                mousePosition++;
            } else {
                mousePosition--;
            }

            // Check for game over conditions
            if (cheesePosition == mousePosition) {
                System.out.println("The mouse caught you! Game over.");
                gameRunning = false;
            } else if (cheesePosition >= 10) {
                System.out.println("You escaped the area! You win!");
                gameRunning = false;
            }
        }

        scanner.close();
    }
}
