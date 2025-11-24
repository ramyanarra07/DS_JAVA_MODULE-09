# Ex19 Palindrome Check Using Deque
## DATE: 08/10/2025
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1.Convert the input string to lowercase and remove all non-alphanumeric characters.

2.Insert each character of the cleaned string into a deque.

3.Repeatedly remove one character from the front and one from the rear.

4.If any pair of removed characters does not match, return false.

5.If all pairs match (or deque becomes empty), the string is a palindrome.

## Program:
```
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: NARRA RAMYA
RegisterNumber: 212223040128
import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
        // Convert to lowercase and remove non-alphanumeric characters
        message = message.toLowerCase().replaceAll("[^a-z0-9]", "");
        
        Deque<Character> deque = new ArrayDeque<>();
        
        // Add all characters to the deque
        for (char c : message.toCharArray()) {
            deque.addLast(c);
        }
        
        // Compare characters from both ends
        while (deque.size() > 1) {
            if (deque.pollFirst() != deque.pollLast()) {
                return false;  // Mismatch found
            }
        }
        
        return true;  // All characters matched
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //System.out.println("Enter a message:");
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }

        scanner.close();
    }
}

 
*/
```

## Output:
<img width="565" height="299" alt="image" src="https://github.com/user-attachments/assets/0b7fde59-21f9-4f88-8262-6ecbbc29c8a1" />



## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
