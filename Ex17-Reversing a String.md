# Ex17 Reversing a String Using Stack Data Structure
## DATE: 01/10/25
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1.Create an empty stack of characters.

2.Push each character of the input string onto the stack.

3.Create an empty StringBuilder for the reversed string.

4.Pop characters from the stack one by one and append to the result.

5.Return and print the reversed string. 

## Program:
```
/*
Program to reverses an input string using a stack
Developed by: NARRA RAMYA
RegisterNumber:  212223040128
import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
        Stack<Character> stack = new Stack<>();

        for (char ch : input.toCharArray()) {
            stack.push(ch);
        }

       
        StringBuilder reversed = new StringBuilder();
        while (!stack.isEmpty()) {
            reversed.append(stack.pop());
        }

        return reversed.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

      
        String reversed = reverseString(input);
        System.out.println(reversed);

        scanner.close();
    }
}

*/
```

## Output:
<img width="654" height="255" alt="image" src="https://github.com/user-attachments/assets/a9fa08ec-c9d5-421b-935e-8f0748391171" />



## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
