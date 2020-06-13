You can do this program in other way also but we have make it loosely coupled to make it easy to understand.

```
public class RotateListInAntiClockWise {

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
        System.out.println("");     // TO GET A NEW LINE WHILE PRINTING OUTPUT 
    }

    void rotateBykTimes(int times) {

        for (int i = 0; i < times; i++) {
            rotateByOne();
        }
    }

    void rotateByOne() {
        Node n = head;

        while (n.next != null) {
            n = n.next;
        }
        n.next = head;
        head = head.next;
        n.next.next = null;

    }

    public static void main(String[] args) {
        RotateListInAntiClockWise antiClockWise = new RotateListInAntiClockWise();
        antiClockWise.add(12);
        antiClockWise.add(13);
        antiClockWise.add(27);
        antiClockWise.add(63);
        antiClockWise.add(522);
        antiClockWise.add(85);
        antiClockWise.displayNodes();

        System.out.println("After rotating");
        antiClockWise.rotateBykTimes(1);
        
        antiClockWise.displayNodes();
    }
}

```
Output - 
```
12 13 27 63 522 85 
After rotating
13 27 63 522 85 12 
```
