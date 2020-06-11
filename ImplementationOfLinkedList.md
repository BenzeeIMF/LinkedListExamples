Functions have quite long names but they are meaningfull!! 

```
public class LinkedListCreation {

    class Node {

        Node head;
        Node next;
        int data;
    }

    Node head;

    void add(int data) {
        Node node = new Node();
        node.data = data;

        if (head == null) {
            head = node;       //     IF HEAD IS NULL! MEANS IT IS FIRST ELEMENT
        } else {
            Node n = head;      // USED FOR TRAVERSING

            while (n.next != null) {
                n = n.next;
            }
            n.next = node;      // n.next IS ACTUALLY NULL AND N IS THE LAST ELEMENT
        }
    }

    void displayNodes() {
        Node n = head;          // ASSINGING VALUE TO TRAVERSE! OTHERWISE HEAD VALUE WILL BE CHANGED
        while (n != null) {
            System.out.print(n.data + " ");       // PRINT THE ELEMENT FIRST AND THEN MOVING TO NEXT
            n = n.next;             // MOVING TO NEXT ELEMENT
        }
    }

    public static void main(String[] args) {
        LinkedListCreation linkedListCreation = new LinkedListCreation();
        linkedListCreation.add(12);
        linkedListCreation.add(52);
        linkedListCreation.add(653);
        linkedListCreation.add(74);
        linkedListCreation.add(94);
        linkedListCreation.displayNodes();

    }
}

```

Output - 
```
12 52 653 74 94
```
