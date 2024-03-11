# Task-1-Java
import java.util.Random;
import java.util.Scanner;

public class GuessTheNumber {
    public static void main(String[] args) {
        System.out.println("Welcome to the Guess the Number game!");
        Scanner scanner = new Scanner(System.in);
        String playAgain = "yes";
        int totalAttempts = 0;
        int totalRounds = 0;
        while (playAgain.toLowerCase().equals("yes")) {
            totalRounds += 1;
            Random random = new Random();
            int targetNumber = random.nextInt(100) + 1;
            int attempts = 0;
            int maxAttempts = 5;
            while (true) {
                System.out.print("Guess the number between 1 and 100: ");
                int userGuess = scanner.nextInt();
                attempts += 1;
                totalAttempts += 1;
                if (userGuess == targetNumber) {
                    System.out.println("Congratulations! You guessed the correct number " + targetNumber + " in " + attempts + " attempts!");
                    break;
                } else if (userGuess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
                if (attempts >= maxAttempts) {
                    System.out.println("Sorry, you've reached the maximum number of attempts. The correct number was " + targetNumber + ".");
                    break;
                }
            }
            System.out.print("Do you want to play again? (yes/no): ");
            playAgain = scanner.next();
        }
        System.out.println("Game Over!");
        System.out.println("You played " + totalRounds + " round(s) and made a total of " + totalAttempts + " attempt(s).");
    }
}
