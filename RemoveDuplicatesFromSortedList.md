Deleting Duplicates from SortedList. You can delete Duplicates from an unsorted list by sort it first using merge Sort.

```
public class RemoveDuplicatesFromSortedList {

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

    void removeDuplicates() {
        Node n = head;

        if (head == null) {
            System.out.println("List has no items");
            return;
        }
        while (n.next != null) {
            if (n.data != n.next.data) {
                n = n.next;
            } else {
                n.next = n.next.next;
            }
        }
    }

    public static void main(String[] args) {
        RemoveDuplicatesFromSortedList removeDuplicatesFromSortedList = new RemoveDuplicatesFromSortedList();
        removeDuplicatesFromSortedList.add(12);
        removeDuplicatesFromSortedList.add(12);
        removeDuplicatesFromSortedList.add(13);
        removeDuplicatesFromSortedList.add(27);
        removeDuplicatesFromSortedList.add(27);
        removeDuplicatesFromSortedList.add(85);
        removeDuplicatesFromSortedList.add(522);
        removeDuplicatesFromSortedList.add(522);
        System.out.print("List before deletion: ");
        removeDuplicatesFromSortedList.displayNodes();

        removeDuplicatesFromSortedList.removeDuplicates();
        System.out.print("List after removing Duplicates: ");
        removeDuplicatesFromSortedList.displayNodes();
    }
}

```
Output - 
```
List before deletion: 12 12 13 27 27 85 522 522 
List after removing Duplicates: 12 13 27 85 522 
```
