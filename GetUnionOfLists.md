To solve this problem we have to do one thing. Suppose we have two lists containing some same elements. To get a unionlist of those lists we 
have to consider them as one. 

```
public class GetUnion {

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
            System.out.println("Head is null");
            return;
        }

        Node n = head;
        while (n != null) {
            System.out.print(n.data + " ");
            n = n.next;
        }
        System.out.println("");
    }

    Node getUnionOfList(Node a, Node b) {
        Node finalList = null;
        if (a == null) {
            return b;
        }
        if (b == null) {
            return a;
        }

        if (a.data > b.data) {
            finalList = b;
            finalList.next = getUnionOfList(a, b.next);
        } else if (a.data < b.data) {
            finalList = a;
            finalList.next = getUnionOfList(a.next, b);
        } else {
            finalList = a;
            finalList.next = getUnionOfList(a.next, b.next);
        }
        return finalList;
    }

    public static void main(String[] args) {
        GetUnion list1 = new GetUnion();
        list1.add(12);
        list1.add(13);
        list1.add(27);
        list1.add(522);
        System.out.print("List 1: ");
        list1.displayNodes();

        GetUnion list2 = new GetUnion();
        list2.add(2);
        list2.add(13);
        list2.add(27);
        list2.add(45);
        System.out.print("List 2: ");
        list2.displayNodes();

        GetUnion getUnion = new GetUnion();
        getUnion.head = getUnion.getUnionOfList(list1.head, list2.head);
        System.out.println("UnionList of List1 and List2 is");
        getUnion.displayNodes();
    }
}
```
Output - 
```
List 1: 12 13 27 522 
List 2: 2 13 27 45 
UnionList of List1 and List2 is
2 12 13 27 45 522 
```
