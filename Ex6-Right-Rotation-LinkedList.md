# Ex6 Right Rotation LinkedList
## DATE: 22/08/2025
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm
1.Traverse the list to find its length and connect the last node to the head (make it circular).

2.Compute k = k % length to adjust rotations.

3.Calculate steps = length - k to locate the new head position.

4.Move steps times to find the new tail.

5.Set newHead = newTail.next and break the circle by making newTail.next = null.

   

## Program:
```
/*
Program to  Right Rotation LinkedList
Developed by: NARRA RAMYA
RegisterNumber:  212223040128

import java.util.Scanner;
public class RotateLinkedList {
    public static Node rotate(Node head, int k) {
        if (head == null || head.next == null || k == 0) {
            return head;
        }
        Node current = head;
        int length = 1;
        while (current.next != null) {
            current = current.next;
            length++;
        }
        current.next = head;
        k = k % length;
        int stepsToNewHead = length - k;
        Node newTail = current;
        while (stepsToNewHead-- > 0) {
            newTail = newTail.next;
        }
        Node newHead = newTail.next;
        newTail.next = null;
        return newHead;
    }
    public static void display(Node head) {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Node head = null, tail = null;
        int n = scanner.nextInt();
        for (int i = 0; i < n; i++) {
            Node newNode = new Node(scanner.nextInt());
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }
        int k = scanner.nextInt();
        head = rotate(head, k);
        display(head);
        scanner.close();
    }
}
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

*/
```

## Output:
<img width="877" height="214" alt="image" src="https://github.com/user-attachments/assets/f794cfb7-7043-49e9-96ef-ae58df87023e" />




## Result:
Thus, the Java program to perfom right rotation on linked list is implemented successfully.
