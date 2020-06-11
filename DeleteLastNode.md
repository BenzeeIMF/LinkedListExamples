```
public class DeleteLastNode {

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

    void deleteLastNode() {

        if (head.next == null) {
            head = null;
        }

        if (head == null) {
            System.out.println("Cannot delete elements! List is null");
            return;
        }

        Node n = head;
        while (n.next.next != null) {
            n = n.next;
        }
        n.next = null;
    }

    public static void main(String[] args) {
        DeleteLastNode deleteLastNode = new DeleteLastNode();
        deleteLastNode.add(12);
        deleteLastNode.add(13);
        deleteLastNode.add(27);
        deleteLastNode.add(63);
        deleteLastNode.add(522);
        deleteLastNode.displayNodes();
        System.out.println();
        
        deleteLastNode.deleteLastNode();
        deleteLastNode.displayNodes();
        System.out.println();

        deleteLastNode.deleteLastNode();
        deleteLastNode.displayNodes();
        System.out.println();

        deleteLastNode.deleteLastNode();
        deleteLastNode.displayNodes();
        System.out.println();

        deleteLastNode.deleteLastNode();
        deleteLastNode.displayNodes();
        System.out.println();

        deleteLastNode.deleteLastNode();
        deleteLastNode.displayNodes();
        System.out.println();

    }
}
```
output - 
```
12 13 27 63 522 
```
After deleting elements
```
12 13 27 63 
12 13 27 
12 13 
12 
Cannot delete elements! List is null
```

Disclaimer: I am providing these codes for practice. As per my hand, I have tested these on some test cases! They worked fine!
These might can give wrong output! 
