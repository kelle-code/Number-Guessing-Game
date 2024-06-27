# Number Guessing Game

This is a simple text-based number guessing game implemented in Java. The game generates a random number between 1 and 100, and the player has to guess the number. The game provides feedback if the guess is too high or too low.

## How to Play

1. The game will prompt you to guess a number between 1 and 100.
2. Enter your guess.
3. The game will tell you if your guess is too high, too low, or correct.
4. Keep guessing until you find the correct number.

## Code Example

```java
import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Random random = new Random();
        Scanner scanner = new Scanner(System.in);
        int numberToGuess = random.nextInt(100) + 1;
        int numberOfTries = 0;
        boolean hasGuessedCorrectly = false;
        
        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("Guess a number between 1 and 100:");

        while (!hasGuessedCorrectly) {
            int guess = scanner.nextInt();
            numberOfTries++;
            
            if (guess < 1 || guess > 100) {
                System.out.println("Invalid guess. Please guess a number between 1 and 100.");
            } else if (guess < numberToGuess) {
                System.out.println("Too low! Try again.");
            } else if (guess > numberToGuess) {
                System.out.println("Too high! Try again.");
            } else {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You guessed the number in " + numberOfTries + " tries.");
            }
        }
        
        scanner.close();
    }
}
