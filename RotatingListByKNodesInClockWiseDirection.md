```
public class RotatiingLinkedListByKNodes {

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

    void rotateByKNodes(int times) {

        if (head.next == null) {
            return;
        }

        for (int i = 0; i < times; i++) {
            rotateByOne();
        }
    }

    void rotateByOne() {
        Node n = head;
        Node prev = null;
        while (n.next != null) {
            prev = n;
            n = n.next;
        }
        prev.next = null;
        n.next = head;
        head = n;
    }

    public static void main(String[] args) {
        RotatiingLinkedListByKNodes rotateList = new RotatiingLinkedListByKNodes();
        rotateList.add(12);
        rotateList.add(13);
        rotateList.add(27);
        rotateList.add(63);
        rotateList.add(522);
        rotateList.add(85);

        rotateList.displayNodes();
        rotateList.rotateByKNodes(4);

        System.out.println("After Rotating");
        rotateList.displayNodes();
    }
}

```

Output - 
```
12 13 27 63 522 85 
After Rotating
27 63 522 85 12 13 
```
