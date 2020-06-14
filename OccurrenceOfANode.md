The output will be Zero(0) if the list doesn't contains the element in the list.
```
public class OccurrenceOfAParticularNode {

    class Node {

        Node next, head;
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
        if (n == null) {
            System.out.println("List is empty");
            return;
        }
        while (n != null) {
            System.out.print(n.data + " ");
            n = n.next;
        }
        System.out.println("");
    }

    int countOccurrence(int value) {

        if (head == null) {
            System.out.println("List is empty");
            return 0;
        }
        int counter = 0;
        Node n = head;
        while (n != null) {
            if (n.data == value) {
                counter++;
            }
            n = n.next;
        }
        return counter;
    }

    public static void main(String[] args) {
        OccurrenceOfAParticularNode aParticularNode = new OccurrenceOfAParticularNode();
        aParticularNode.add(12);
        aParticularNode.add(13);
        aParticularNode.add(12);
        aParticularNode.add(27);
        aParticularNode.add(85);
        aParticularNode.add(13);
        aParticularNode.add(522);
        aParticularNode.add(12);
        System.out.print("List: ");
        aParticularNode.displayNodes();

        int value = 134;
        System.out.println("Occurrences of " + value + " are " + aParticularNode.countOccurrence(value));
    }
}
```
Output - 
```
List: 12 13 12 27 85 13 522 12 
Occurrences of 12 are 3
```
