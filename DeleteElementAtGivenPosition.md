Delete Element at any given position.

```
public class l6DeleteElementAtGivenPos {

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
    }

    void deleteAtGivenPos(int index) {

        if (head == null || index < 0) {
            System.out.println("");
            System.out.println("Can't delete elements");
            return;
        }
        if (index == 1) {
            head = head.next;
        } else {
            Node n = head;
            for (int i = 1; i < index - 1; i++) {
                n = n.next;
            }
            n.next = n.next.next;
        }
    }

    public static void main(String[] args) {
        l6DeleteElementAtGivenPos deleteElementAtGivenPos = new l6DeleteElementAtGivenPos();
        deleteElementAtGivenPos.add(12);
        deleteElementAtGivenPos.add(13);
        deleteElementAtGivenPos.add(27);
        deleteElementAtGivenPos.add(63);
        deleteElementAtGivenPos.add(522);
        deleteElementAtGivenPos.add(85);
        deleteElementAtGivenPos.displayNodes();

        deleteElementAtGivenPos.deleteAtGivenPos(1);
        System.out.println("");
        deleteElementAtGivenPos.displayNodes();

        deleteElementAtGivenPos.deleteAtGivenPos(5);
        System.out.println("");
        deleteElementAtGivenPos.displayNodes();

        deleteElementAtGivenPos.deleteAtGivenPos(1);
        System.out.println("");
        deleteElementAtGivenPos.displayNodes();

        deleteElementAtGivenPos.deleteAtGivenPos(-1);
        System.out.println("");
        deleteElementAtGivenPos.displayNodes();

    }
}
```

Output - 
```
12 13 27 63 522 85 
13 27 63 522 85 
13 27 63 522 
27 63 522 
Can't delete elements

27 63 522
```
