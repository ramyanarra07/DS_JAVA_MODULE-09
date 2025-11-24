# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 26/09/2025
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1.Create a stack and scan the string character by character.


2.Push every opening bracket (, {, [ onto the stack.


3.For every closing bracket, check if the stack is empty — if yes, it's unbalanced.


4.Pop the top element and verify if it matches the type of closing bracket.


5.After scanning, if the stack is empty, it is balanced; otherwise, unbalanced.

 

## Program:
```
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: NARRA RAMYA
RegisterNumber: 212223040128
import java.util.Scanner;

public class ParenChecker {
    static class ArrayStack {
        private char[] data;
        private int top;

        public ArrayStack(int capacity) {
            data = new char[capacity];
            top = -1;
        }

        public boolean isEmpty() { return top == -1; }
        public boolean isFull() { return top == data.length - 1; }

        public void push(char c) {
            if (isFull()) throw new RuntimeException("Stack overflow");
            data[++top] = c;
        }
        public char pop() {
            if (isEmpty()) throw new RuntimeException("Stack underflow");
            return data[top--];
        }
        public char peek() {
            if (isEmpty()) throw new RuntimeException("Stack is empty");
            return data[top];
        }
    }


    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

*/
```

## Output:
<img width="872" height="213" alt="image" src="https://github.com/user-attachments/assets/ce3e9018-79ba-4e34-95fb-374e081b201e" />



## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
