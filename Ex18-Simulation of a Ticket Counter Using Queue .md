# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE:03/10/2025
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1.For every enqueue command, create a new node and add it at the rear of the queue.

2.For dequeue, remove the node at the front and print the served customer.

3.If the queue becomes empty after dequeue, set both front and rear to null.

4.For display, traverse the linked list from front to rear and print names.

5.Continue reading commands until exit is entered, then terminate the program.  

## Program:
```
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: NARRA RAMYA
RegisterNumber: 212223040128
import java.util.Scanner;

class Node {
    String customerName;
    Node next;

    public Node(String name) {
        this.customerName = name;
        this.next = null;
    }
}

class TicketQueue {
    private Node front;
    private Node rear;

    public TicketQueue() {
        this.front = this.rear = null;
    }

    public void enqueue(String customerName) {
        Node newNode = new Node(customerName);
        if (rear == null) {
            front = rear = newNode;
            return;
        }
        rear.next = newNode;
        rear = newNode;
    }

    public void dequeue() {
        if (front == null) {
            System.out.println("Queue is empty. No customer to serve.");
            return;
        }
        System.out.println("Serving customer: " + front.customerName);
        front = front.next;
        if (front == null) {
            rear = null;
        }
    }

    public void displayQueue() {
        if (front == null) {
            System.out.println("Queue is empty.");
            return;
        }
        System.out.print("Queue: ");
        Node temp = front;
        while (temp != null) {
            System.out.print(temp.customerName);
            if (temp.next != null) System.out.print(" -> ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class TicketCounter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        TicketQueue queue = new TicketQueue();
        String command;

        //System.out.println("Ticket Counter Simulation");
        //System.out.println("Commands: enqueue <name>, dequeue, display, exit");

        while (true) {
            //System.out.print("Enter command: ");

            // Fix for NoSuchElementException
            if (!scanner.hasNextLine()) {
                //System.out.println("No more input. Exiting simulation.");
                break;
            }

            command = scanner.nextLine().trim();
            if (command.isEmpty()) continue;

            String[] parts = command.split(" ");

            switch (parts[0]) {
                case "enqueue":
                    if (parts.length >= 2) {
                        queue.enqueue(parts[1]);
                    } else {
                        System.out.println("Please provide a customer name.");
                    }
                    break;
                case "dequeue":
                    queue.dequeue();
                    break;
                case "display":
                    queue.displayQueue();
                    break;
                case "exit":
                    System.out.println("Exiting simulation.");
                    scanner.close();
                    return;
                default:
                    System.out.println("Invalid command.");
            }
        }

        scanner.close(); // Safe close
    }
} 
*/
```

## Output:
<img width="1215" height="802" alt="image" src="https://github.com/user-attachments/assets/77d1806a-7fe0-4374-b5b1-2dc7d0c45832" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
