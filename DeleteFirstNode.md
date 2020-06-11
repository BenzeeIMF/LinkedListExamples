This code can help you to delete front Node of the list!

```
public class DeleteFrontNode {

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
        while (n != null) {
            System.out.print(n.data + " ");
            n = n.next;
        }
    }

    void deleteFirstNode() {

        if (head == null) {
            System.out.println("No more items to delete");
        } else if (head.next == null) {
            head = null;
        } else {
            head = head.next;
        }

    }

    public static void main(String[] args) {
        DeleteFrontNode deleteFrontNode = new DeleteFrontNode();
        deleteFrontNode.add(12);
        deleteFrontNode.add(13);
        deleteFrontNode.add(27);
        deleteFrontNode.add(63);
        deleteFrontNode.add(522);
        deleteFrontNode.add(85);
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");

        deleteFrontNode.deleteFirstNode();
        deleteFrontNode.displayNodes();
        System.out.println("");
    }
}

```
Output - 
```
12 13 27 63 522 85 
13 27 63 522 85 
27 63 522 85 
63 522 85 
522 85 
85 

No more items to delete
```
