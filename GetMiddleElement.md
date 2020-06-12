In this code, we have found the middle element of the linked list.
Don't worry, if a list contains even number of elements suppose a list containing 1- 10 elements then 5 and 6 both are middle elements.

```
public class GetMiddleElement {

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

    int MiddleElement() {
        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow.data;
    }

    public static void main(String[] args) {
        GetMiddleElement middleElement = new GetMiddleElement();
        middleElement.add(12);
        middleElement.add(13);
        middleElement.add(27);
        middleElement.add(63);
        middleElement.add(522);
        middleElement.add(85);
        middleElement.displayNodes();
        System.out.println("");
        System.out.println("Middle Element is " + middleElement.MiddleElement());
    }
}
```
Output - 
```
12 13 27 63 522 85 
Middle Element is 63
```
