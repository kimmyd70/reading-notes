## Trees and BST

notes from [this article](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

- Node - A node is the individual item/data that makes up the data structure
- Root - The root is the first/top Node in the tree
- Left Child - The node that is positioned to the left of a root or node
- Right Child - The node that is positioned to the right of a root or node
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not contain any children
- Height - The height of a tree is determined by the number of edges from the root to the bottommost node

- Traversed through recursion

### Traversing Depth First

Prioritizes going through the height of the tree

***** See examples of each in reading doc

1. Pre-order: root >> left >> right
```
ALGORITHM preOrder(root)

  OUTPUT <-- root.value

  if root.left is not NULL
      preOrder(root.left)

  if root.right is not NULL
      preOrder(root.right)
```

2. In-order: left >> root >> right
```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

3. Post-order: left >> right >> root
```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```
### Traversing Breadth First
- iterates through the tree by going through each level of the tree node-by-node

***** See examples of in reading doc
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```


### BST
- Restricted to two children (left and right)

- No specific sorting order and nodes can be added wherever space allows (given the restriction of only 2 children)

- One strategy for adding a new node to a binary tree is to fill all “child” spots from the top down. To do so, we would leverage the use of breadth first traversal. During the traversal, we find the first node that does not have 2 child nodes, and insert the new node as a child. We fill the child slots from left to right.

- structure: all values smaller than the root are `left` and larger are `right`

- structure makes searching quicker: search left or right of the node depending on search value < or > root. Treat each new level as a root and repeat (recursion)

### Big O Trees

- insert node: time = O(n); space = O(w); w = largest width

- perfect tree: every leaf node has exactly 2 children max width = 2^(h-1) where height = log(n)

## Big O BST

- search and insertion: time = O(h); h = log(n) for perfect; h = n for unbalanced
- search: space = O(1)