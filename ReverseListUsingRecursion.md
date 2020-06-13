This code has a time complexity of O(n) and space complexity of O(1).
```
public class ReverseLinkedList {

    class Node {

        Node head, next;
        int data;
    }
    Node head;

    void add(int data) {
        Node node = new Node();
        node.data = data;

        if (head == null) {
            head = node;
        } else {
            Node n = head;
            while (n.next != null) {
                n = n.next;
            }
            n.next = node;
        }

    }

    void displayNodes() {
        Node n = head;
        while (n != null) {

            System.out.print(n.data + " ");
            n = n.next;
        }
        System.out.println("");
    }

    void reverse() {

        Node n = head;
        Node current = head;
        Node previous = null;

        while (n != null) {
            n = n.next;
            current.next = previous;
            previous = current;
            current = n;
        }
        head = previous;
    }

    public static void main(String[] args) {
        ReverseLinkedList reverseLinkedList = new ReverseLinkedList();
        reverseLinkedList.add(12);
        reverseLinkedList.add(13);
        reverseLinkedList.add(27);
        reverseLinkedList.add(63);
        reverseLinkedList.add(522);
        reverseLinkedList.add(85);
        reverseLinkedList.displayNodes();
        reverseLinkedList.reverse();
        System.out.println("After reversing");
        reverseLinkedList.displayNodes();

    }
}

```

Output - 
```
12 13 27 63 522 85 
After reversing
85 522 63 27 13 12 
```
