In this code, we have to delete M number of Nodes after reaching to Nth Node.
```
public class DeleteMNodesAfterNNodes {

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

    void deleteMAfterN(int position, int noOfNodes) {

        if (position < 1) {
            System.out.println("Position should be greater than 1");
            return;
        }

        Node n = head;
        int i = 1;
        while (i < position) {
            n = n.next;
            i++;
        }
        if (n == null || n.next == null) {
            return;
        }

        for (i = 0; i < noOfNodes; i++) {
            if (n.next != null) {
                n.next = n.next.next;
            } else {
                System.out.println("Reached at the end of list");
                break;
            }
        }

    }

    public static void main(String[] args) {
        DeleteMNodesAfterNNodes deleteMNodesAfterNNodes = new DeleteMNodesAfterNNodes();
        deleteMNodesAfterNNodes.add(12);
        deleteMNodesAfterNNodes.add(13);
        deleteMNodesAfterNNodes.add(27);
        deleteMNodesAfterNNodes.add(522);
        deleteMNodesAfterNNodes.add(85);
        System.out.print("List before: ");
        deleteMNodesAfterNNodes.displayNodes();

        System.out.print("After Deleting: ");
        deleteMNodesAfterNNodes.deleteMAfterN(1, 2);
        deleteMNodesAfterNNodes.displayNodes();

    }
}
```
Output - 
```
List before: 12 13 27 522 85 
After Deleting: 12 522 85 
```
