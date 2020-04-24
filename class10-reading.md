# Stacks and Queues

- a `Stack` is a data structure that uses nodes

## common terms

  - Push > add a node to the stack
  - pop > remove a node from the stack, exception on an empty stack
  - top > top of stack
  - peek > check value of top node, exception on empty stack
  - isEmpty > true when stack is empty

## stack concepts

- FILO - First In Last Out
- LIFO - Last In First out

### Push O(1)

- Push a node is alwasy 0(1), alwasy same regardless of number of nodes in the stack
- make this new node the new top, it's next is the old top

```javascript
Algorithm push(value)
node = new Node(value)
node.next = top
top = node
```

### Pop o(1)

```javascript
algorithm pop()
Node temp = top
top = top.next
temp.next = null
return temp.value
```

### Peek o(1)

- usually you do a `isEmpty` prior to peek

```javascript
Algorithm peek()
return top.value
```

### IsEmpty o(1)

```javascript
Algorithm isEmpty()
return top === null
```

## Queue

- terms
  - enqueue > nodes or times are added to the queue
  - dequeue > nodes or tiems are removed, exception when empty
  - front > front/first node of queue
  - rear > this is the rear/last node of the queue
  - peek > check value of ront node, exception when empty
  - isEmpty > returns true when queue is empty, otherwise false

- FIFO > First In First Out
- LILO > Last In Last Out

### Enqueue o(1)

- add node to queue

```javascript
Algorithm enqueue(value)
node = newNode(value)
rear.next = node
rear = node
```

### Dequeue o(1)

- remove node from queue

```javascript
Algorithm dequeue()
Node temp = front
front = front.next
temp.next = null
return temp.value
```

### Peek o(1)

- check value of front of queue, usually paired with `isEmpty` first

```javascript
algorithm peek()
return front.value
```

### isEmpty o(1)

```javascript
Algorithm isEmpty()
return front = null
```