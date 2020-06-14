Intersection Node is a node from where both LinkedList contains same elements.

```
public class IntersectionNode {

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

        if (head == null) {
            System.out.println("List is empty");
            return;
        }

        Node n = head;
        while (n != null) {
            System.out.print(n.data + " ");
            n = n.next;
        }
        System.out.println("");
    }

    void getIntersectionPoint(Node a, Node b) {

        Node n = head;
        while (a != null && b != null) {
            if (a.data > b.data) {
                b = b.next;
            } else if (a.data < b.data) {
                a = a.next;
            } else {
                System.out.println("Intersection Node is " + a.data);
                break;
            }
        }

    }

    public static void main(String[] args) {
        IntersectionNode list1 = new IntersectionNode();
        list1.add(12);
        list1.add(13);
        list1.add(27);
        list1.add(522);
        System.out.print("List 1: ");
        list1.displayNodes();

        IntersectionNode list2 = new IntersectionNode();
        list2.add(2);
        list2.add(19);
        list2.add(27);
        list2.add(522);
        System.out.print("List 2: ");
        list2.displayNodes();

        IntersectionNode intersectionNode = new IntersectionNode();
        intersectionNode.getIntersectionPoint(list1.head, list2.head);
    }

}
```

Output - 
```
List 1: 12 13 27 522 
List 2: 2 19 27 522 
Intersection Node is 27
```
