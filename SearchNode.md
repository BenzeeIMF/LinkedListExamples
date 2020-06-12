This code will tell you that if a particular node containing particular data is avaialble or not. We are not searching the node, as to search node, we need to pass the hashcode of the object, which we do not want!

      ```
      public class SearchNode {

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

    boolean isNodeAvailable(int data) {
        boolean available = false;

        Node n = head;
        while (n != null) {
            if (n.data == data) {
                available = true;
            }
            n = n.next;
        }

        return available;

    }

    public static void main(String[] args) {
        SearchNode searchNode = new SearchNode();
        searchNode.add(12);
        searchNode.add(13);
        searchNode.add(27);
        searchNode.add(63);
        searchNode.add(522);
        searchNode.add(85);
        searchNode.displayNodes();
        System.out.println("");
        System.out.println("Element founded " + searchNode.isNodeAvailable(522));
        System.out.println("Element founded " + searchNode.isNodeAvailable(100));

    }
}
      ```
Output - 
```
12 13 27 63 522 85 
Element founded true
Element founded false
```
