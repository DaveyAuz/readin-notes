# Reading Notes Class #10

><ol> In the context of stacks and queues, what are the main differences between the terms "FILO" and "LIFO"? How do these concepts affect the order in which items are added and removed from each data structure?

><li> TUTORIAL

Tutorial: Stacks

A stack is a linear data

Stack Operations:

1) Push: Add an element to the top of the stack.
2) Pop: Remove the top element from the stack.
3) Peek: Inspect the value of the top element without removing it.
4) IsEmpty: Check if the stack is empty.

Stack Visualization:

1) Start with an empty stack:

```java
Top -> NULL
```

2) Push elements onto the stack:
Push 10:

```java
Top -> Node(10, NULL)
``````

 Push 20:

```java
Top -> Node(20, Node(10, NULL))
```

Push 30
```java
Top -> Node(30, Node(20, Node(10, NULL)))
```

3) Peek the top element:

Peek:
```java
Top -> Node(30, Node(20, Node(10, NULL)))
Output: 30
```

4) Pop the top element:

Pop
```java
Top -> Node(20, Node(10, NULL))
Popped: 30
```

5) Check if the stack is empty:

IsEmpty:

```java
Top -> Node(20, Node(10, NULL))
Output: Stack is not empty
```

6) Pop remaining elements:

Pop:
```java
Top -> Node(10, NULL)
Popped: 20
```
Pop:
```java
Top -> NULL
Popped: 10
```

7)Check if the stack is empty:

IsEmpty:
```java
Top -> NULL
Output: Stack is empty
```

Let's implement the stack using a linked list in Java:

```JAVA
class Node {
    int value;
    Node next;

    Node(int value) {
        this.value = value;
        this.next = null;
    }
}

class Stack {
    Node top;

    Stack() {
        this.top = null;
    }

    void push(int value) {
        Node newNode = new Node(value);
        newNode.next = top;
        top = newNode;
    }

    int pop() {
        if (isEmpty()) {
            throw new RuntimeException("Stack is empty");
        }
        int poppedValue = top.value;
        top = top.next;
        return poppedValue;
    }

    int peek() {
        if (isEmpty()) {
            throw new RuntimeException("Stack is empty");
        }
        return top.value;
    }

    boolean isEmpty() {
        return top == null;
    }
}
```

Tutorial: Queues

A queue is a linear data structure that follows the First In First Out (FIFO) principle, meaning that the first element added to the queue will be the first one to be removed. Queues are commonly used in scenarios like task scheduling, printer job management, and breadth-first search algorithms.

Queue Operations:

1) Enqueue: Add an element to the rear of the queue.
2) Dequeue: Remove the front element from the queue.
3) Peek: Inspect the value of the front element without removing it.
4) IsEmpty: Check if the queue is empty.

Queue Visualization:
Let's create a queue and perform various operations step by step:

1) Start with an empty queue:

```java
Front -> NULL
Rear -> NULL
```

2)Enqueue elements onto the queue:

Enqueue 10:
```java
Front -> Node(10, NULL)
Rear -> Node(10, NULL)
```
Enqueue 20:
```java
Front -> Node(10, Node(20, NULL))
Rear -> Node(20, NULL)
```
Enqueue 30:
```java
Front -> Node(10, Node(20, Node(30, NULL)))
Rear -> Node(30, NULL)
```

3) Peek the front element:

Peek: 

```java
Front -> Node(10, Node(20, Node(30, NULL)))
Output: 10
```

4) Dequeue the front element:

Dequeue:
```java
Front -> Node(20, Node(30, NULL))
Dequeued: 10
```

5) Check if the queue is empty:

IsEmpty:

```java
Front -> Node(20, Node(30, NULL))
Output: Queue is not empty
```

6) Dequeue remaining elements:

Dequeue:

```java
Front -> Node(30, NULL)
Dequeued: 20
```

Dequeue:
```java
Front -> NULL
Dequeued: 30
```

7) Check if the queue is empty:

IsEmpty:

```java
Front -> NULL
Output: Queue is empty
```

Let's implement the queue using a linked list in Java:

```JAVA
class Node {
    int value;
    Node next;

    Node(int value) {
        this.value = value;
        this.next = null;
    }
}

class Queue {
    Node front;
    Node rear;

    Queue() {
        this.front = null;
        this.rear = null;
    }

    void enqueue(int value) {
        Node newNode = new Node(value);
        if (isEmpty()) {
            front = newNode;
        } else {
            rear.next = newNode;
        }
        rear = newNode;
    }

    int dequeue() {
        if (isEmpty()) {
            throw new RuntimeException("Queue is empty");
        }
        int dequeuedValue = front.value;
        front = front.next;
        if (front == null) {
            rear = null;
        }
        return dequeuedValue;
    }

    int peek() {
        if (isEmpty()) {
            throw new RuntimeException("Queue is empty");
        }
        return front.value;
    }

    boolean isEmpty() {
        return front == null;
    }
}


```

Conclusion:
Stacks and queues are essential data structures that can be used to solve various programming problems efficiently. Understanding their principles, operations, and implementations in Java will greatly enhance your ability to design robust algorithms and handle real-world scenarios. Mastering stacks and queues will lay a solid foundation for dealing with more complex data structures and algorithms in your Java programming journey.

<ol>


[HOME](../README.md)