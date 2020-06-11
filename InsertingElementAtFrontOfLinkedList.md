I hope you are following this series sequentially. If not! Kindly follow in sequentially order. Programs are sometimes linked with each other!
In this function I have used mostly the functions used in previous code (Implementaion of LinkedList)

addAtFirst() is the function in this code to insert element at front of the LinkedList


```
public class InsertingElementAtFirst {

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
    }

    void addAtFirst(int data) {
        Node node = new Node();
        node.data = data;

        node.next = head;
        head = node;

    }

    public static void main(String[] args) {
        InsertingElementAtFirst elementAtFirst = new InsertingElementAtFirst();
        elementAtFirst.add(12);
        elementAtFirst.add(13);
        elementAtFirst.add(27);
        elementAtFirst.add(63);
        elementAtFirst.add(522);
        elementAtFirst.add(85);
        elementAtFirst.displayNodes();
        System.out.println("");

        elementAtFirst.addAtFirst(55);
        elementAtFirst.displayNodes();
        System.out.println("");

        elementAtFirst.addAtFirst(110);
        elementAtFirst.displayNodes();
    }
}

```

Output -
```
12 13 27 63 522 85 
55 12 13 27 63 522 85 
110 55 12 13 27 63 522 85 
```
