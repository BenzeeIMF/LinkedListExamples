This is how we calculate the length or size of the LinkedList.

```
public class GetSizeOfList {

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

    int getSize() {
        Node n = head;
        int counter = 0;

        while (n != null) {
            counter++;
            n = n.next;
        }
        return counter;
    }

    public static void main(String[] args) {
        GetSizeOfList sizeOfList = new GetSizeOfList();
        sizeOfList.add(12);
        sizeOfList.add(13);
        sizeOfList.add(27);
        sizeOfList.add(63);
        sizeOfList.add(522);
        sizeOfList.add(85);
        sizeOfList.displayNodes();
        System.out.println("");
        System.out.println("Size of the list is " + sizeOfList.getSize());
    }
}
```
Output - 
```
12 13 27 63 522 85 
Size of the list is 6
```
