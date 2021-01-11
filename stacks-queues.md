## Stacks and Queue

notes from [this article](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)

### Stacks
- data structure consisting of Nodes

- `push`--put onto stack.  O(1): assign `new` to `top` and `new.next` to original `top`
**(see visuals)

- `pop`--remove `top` from stack. O(1): reassign `top` to Node below and return `top` to user. Typically check `isEmpty` before popping.
**(error if empty) **(see visuals)

- `top`--top node or item on the stack

- `peek`--view the ***value*** of the `top`. O(1).   Pseudo: `return top.value` Do not reassign `.next` since top remains unchanged
Typically check `isEmpty` before.**(error if empty)

- `isEmpty`--returns boolean.  O(1) `return top = NULL`

>>*** Can be FILO or LIFO

### Push
![Stack Visual](./images/stack-visual.png)

![Stack Visual2](./images/stack-visual2.png)

![Stack Visual3](./images/stack-visual3.png)

### Pop
![Stack Visual4](./images/stack-visual4.png)

![Stack Visual5](./images/stack-visual5.png)

![Stack Visual6](./images/stack-visual6.png)

### Queues

- data structure consisting of Nodes

- `enqueue`--put into queue at `rear`.  O(1): 
**(see visuals)

- `dequeue`--remove `front` from queue. O(1): reassign `front` to Node below and return `front` to user. Typically check `isEmpty` before popping.
**(error if empty) **(see visuals)

- `front`--first node or item in the queue

- `rear`--last Node of the queue

- `peek`--view the ***value*** of `front`. O(1).   Pseudo: `return front.value` Do not reassign `.next` since front remains unchanged
Typically check `isEmpty` before.**(error if empty)

- `isEmpty`--returns boolean.  O(1) `return front = NULL`

>>*** Can be FIFO or LILO

### Enqueue
![Queue Visual1](./images/queue-visual1.png)

![Queue Visual2](./images/queue-visual2.png)
```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node
```
### Dequeue

![Queue Visual3](./images/queue-visual3.png)

![Queue Visual4](./images/queue-visual4.png)

![Queue Visual5](./images/queue-visual5.png)

```
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
```