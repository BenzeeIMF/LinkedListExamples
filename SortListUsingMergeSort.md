This code is little lengthy but is very easy to understand. Go through it step by step.
```
public class SortListUsingMergeSort {

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

    Node mergingOperation(Node a, Node b) {
        Node result = null;
        if (a == null) {
            return b;
        }
        if (b == null) {
            return a;
        }

        if (a.data < b.data) {
            result = a;
            result.next = mergingOperation(a.next, b);
        } else {
            result = b;
            result.next = mergingOperation(a, b.next);
        }
        return result;
    }

    Node mergeSort(Node head) {

        if (head == null || head.next == null) {
            return head;
        }

        Node middle = getMiddle(head);
        Node afterMiddle = middle.next;
        middle.next = null;

        Node a = mergeSort(head);
        Node b = mergeSort(afterMiddle);

        Node finalList = mergingOperation(a, b);
        return finalList;

    }

    Node getMiddle(Node node) {
        if (node.next == null) {
            return node;
        }
        Node n = node;
        Node slow = node;
        Node fast = node;

        while (fast.next != null && fast.next.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }

    void doMergeSort() {
        head = mergeSort(head);
    }

    public static void main(String[] args) {
        SortListUsingMergeSort mergeSort = new SortListUsingMergeSort();
        mergeSort.add(12);
        mergeSort.add(13);
        mergeSort.add(27);
        mergeSort.add(63);
        mergeSort.add(522);
        mergeSort.add(85);
        System.out.print("List before sorting: ");
        mergeSort.displayNodes();
        mergeSort.doMergeSort();
        System.out.print("List After Sorting: ");
        mergeSort.displayNodes();
    }
}

```

Output - 
```
List before sorting: 12 13 27 63 522 85 
List After Sorting: 12 13 27 63 85 522 
```
