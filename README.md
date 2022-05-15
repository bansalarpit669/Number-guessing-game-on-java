# Number-guessing-game-on-java

package number_guessing_game;

/**
 *
 * @author pc
 */import javax.swing.*;
public class Number_Guessing_game {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        int Number = (int) (Math.random()*100 + 1);
        int userAnswer = 0;
        System.out.println("The correct guess would be " + Number);
        int count = 1;

        while (userAnswer != Number)
        {
            String response = JOptionPane.showInputDialog(null,
                "Enter a guess between 1 and 100", "Guessing Game", 3);
            
            userAnswer = Integer.parseInt(response);
            JOptionPane.showMessageDialog(null, ""+ determineGuess(userAnswer, Number, count));
            count++;
        }  

    }
    public static String determineGuess(int userAnswer, int Number, int count){
        if (userAnswer <=0 || userAnswer >100) {
            return "Your guess is invalid";
        }
        else if (userAnswer == Number ){
            return "Correct!\nTotal Guesses: " + count;
        }
        else if (userAnswer > Number) {
            return "Your guess is too high, try again.\nTry Number: " + count;
        }
        else if (userAnswer < Number) {
            return "Your guess is too low, try again.\nTry Number: " + count;
        }
        else {
            return "Your guess is incorrect\nTry Number: " + count;
        }
    }

}
