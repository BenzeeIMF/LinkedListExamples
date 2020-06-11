This is the code to insert element at any particular position!


```
public class InsertingElementAtGivenPosition {

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

    void addAtFirst(int data) {
        Node node = new Node();
        node.data = data;

        node.next = head;
        head = node;

    }

    //THIS FUNCTION ONLY CHECKS IF THE INDEX IS VALID OR NOT ON THE NEGATIVE SIDE!
    // TO CHECK FOR THE POSITIVE SIDE, MEANS IF THE INDEX IS GREATER THAN THE LENGTH OF LINKEDLIST
    // WE ARE NOT CHECKING! IF YOU CAN TRY IT BY YOURSELF THEN IT'S WELL AND GOOD! 
    // OTHERWISE WE''LL SEE IN FUTURE HOW TO CALCULATE LENGTH OF LINKEDLIST
    
    void addAtGivenPosition(int index, int data) {
        if (index <= 0) {
            System.out.println("Can't add element on negative index");
        } else if (index == 1)            // THAT MEANS AT FIRST POSITION - AT HEAD
        {
            addAtFirst(data);
        } else {
            Node node = new Node();
            node.data = data;
            Node n = head;
            for (int i = 1; i < index - 1; i++) {
                                        // INDEX -1 ( BECAUSE IF LOOP RUN FOR 1 TIME THE VALUE
                                        // OF N BECOME 2)
                n = n.next;
            }
            node.next = n.next;
            n.next = node;
        }
    }

    public static void main(String[] args) {
        InsertingElementAtGivenPosition atGivenPosition = new InsertingElementAtGivenPosition();
        atGivenPosition.add(12);
        atGivenPosition.add(13);
        atGivenPosition.add(27);
        atGivenPosition.add(63);
        atGivenPosition.add(522);
        atGivenPosition.add(85);
        atGivenPosition.displayNodes();
        System.out.println("");
        System.out.println("After updating List Elements");
        atGivenPosition.addAtGivenPosition(7, 55);
        atGivenPosition.displayNodes();

        System.out.println();
        atGivenPosition.addAtGivenPosition(1, 1);
        atGivenPosition.displayNodes();

        System.out.println();
        atGivenPosition.addAtGivenPosition(4, 4);
        atGivenPosition.displayNodes();

        System.out.println();
        atGivenPosition.addAtGivenPosition(3, 565);
        atGivenPosition.displayNodes();

        System.out.println();
        atGivenPosition.addAtGivenPosition(5, 79);
        atGivenPosition.displayNodes();
    }
}
```
Output - 
```
12 13 27 63 522 85 
After updating List Elements
12 13 27 63 522 85 55 
1 12 13 27 63 522 85 55 
1 12 13 4 27 63 522 85 55 
1 12 565 13 4 27 63 522 85 55 
1 12 565 13 79 4 27 63 522 85 55 
```

