# [Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)

* What is a linked list? a series of `Nodes` that reference each other

* Terms
  * Linked List - data structure that links/points to next node in list
  * Singly - `node` with only 1 reference, to the next node
  * Doubly - two links, next and previous
  * node - individual item, has the data for each link
  * Next - each node has this property
  * head - reference to first node in linked list
  * current - reference to the current `node` looked at. usually this is reset during traversal, set the head to the current

- when traversing, can't use `foreach` or `for`, you need to use `next`
- best to use a `while()` for traversal, can keep seeing if next node is `null`. if you go to a null node, `NullReferenceException` gets thrown and program will crash
- `current` is the most useful to help show where you are in list
- BigO time of `includes` is O(n), becaus the last node is what we want. `n` is the number of nodes in list
- BigO space of `includes` is O(1), no additional space is used

## [What’s a Linked List, Anyway? Part 1](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)

* think of a 'linear datat structure'
* arrays are a linear structure
  * when using that data, we need the ENTIRE object in memory
  * with a linked list, we can retrieve just the CURRENT node and it's information, they don't need to be contiguous either
* linked lists are `[chunk of data] link to next node ->`
* singly lists just know their next item
* doubly lists no next and previous
* a circularly linked list is also possible by having a later node reference an earlier node in a loop


## [What’s a Linked List, Anyway? Part 2](https://medium.com/basecs/whats-a-linked-list-anyway-part-2-131d96f71996)

- `Big O Notation` is about efficiency and tradeoffs.
  - how much time and how much memory
- O(1) is constant
- O(n) is linear growth
- O(n^2) is exponential growth

- adding to a list we need to find the head, make a new node, set pointer to `current`, change `head` pointer to `new Node`
- adding a node at the head is always O(1);
- adding to the end is O(n)

- array vs linked list
insert/delete > slow vs fast
serach > fast vs slow
size > static vs dynamic
memory > fully allocated vs only neccessary allocation
finding > fast vs requires traversal
size > good if you know size of list VS don't know size