# trees

- terms
  1. node - item that makes up tree
  1. root - first node
  1. left child - 
  1. right child
  1. edge - link between pareny and child nodes
  1. leaf - node without children
  1. height - number of edges from root to bottom

- traversals
  - depth first - go all the way down
  - breadth first - go across

- Depth First
  - pre-order : root >> left >> right
  - in-order: left >>root>> right
  - post-order: left>>right>>root
  - go all the way down left, then across, then up to next node and then down left
  - recursion is the most common way (and cleanest) way to do this

### pre order

```javascript
output <- root.value
if root.left is not null
  preOrder(root.left)
if root.right is not null
  preorder(root.right)
```

- recursion manipulates the call stack to self-terminate when the stopping action is met
- the code for pre/in/post order is the same, just move where the output of root is placed

### breadth first

- go through each level of tree in sequence (utilize a queue)

```javascript
queue breadth <- new Qeueue()
breadth.enqueue(root)

while breadth.peek()
  node front = breadth.dequeue()
  output <- front.value

  if front.left is not null
    breadth.enqueue(front.left)

  if front.right is not null
    breadth.enqueue(front.right)
```

- all code so far is for `binary` trees

- when adding to a binary tree, no strict rule on where, but common for "first available child on tree, from top down"
- requires traversal to pull this off
- O(n) to insert a new node. Searching is also O(n)
- space complexity is O(w), W is width of tree
- max width for binary tree is 2^(h-1). h is height, and is log n, n being nodes

### binary search trees

- BST, all values less than the root are to the left, higher to the right
- searching is best done with a while loop, cycling until we hit a leaf or match we are looking for
- big O: time complecity is O(h). In a balanced tree, the height is log(n), in unbalanced the worst case is n
- space complexity is o(1)



