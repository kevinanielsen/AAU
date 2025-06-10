# 1 Stacks
Can be compared to a stack of plates and follows the LIFO-principle: "Last In, First Out".
- Insertion and deletion are called Push and Pop
- For a stack with room for `n` elements, we use an array `S[1:n]` 
- `S.top` is the index pointing at the latest inserted element.
- `S.size` tells us the size of the stack (i.e., `n`). 
- `S.peek` tells us the value of the element at `S.top`.
## 1.1 Operations
We have 3 different operations, Stack-Empty, Push, Pop:
[[stack_empty_pseudo.png|Stack-Empty Pseudo Code]]
[[stack_push_pseudo.png|Push Pseudo Code]]
[[stack_pop_pseudo.png|Pop Pseudo Code]]

The pop operation does not actually remove an element from the underlying array, it simply decreases the index of `S.top` by 1. 
# 2 Queues
Can be compared to a queue at a restaurant and follows the FIFO-principle: "First In, First Out".
- Insertion and deletion are called Enqueue and Dequeue.
- For a queue with room for `n-1` elements, we use an array `Q[1:n]`
- `Q.head` is defined as the index of the "front" element in the queue
- `Q.tail` is defined as the index of the back of the queue (where the next element will be inserted).
- The queue has the wrap-around property, meaning that if `Q.tail == Q.size` after we insert an element, we set `Q.tail = 1`.
## 2.1 Operations
[[queue_enqueue_pseudo.png|Enqueue Pseudo Code]]
[[queue_dequeue_pseudo.png|Dequeue Pseudo Code]]
# 3 Linked Lists
- Each element in a linked list `L` is an object `x` with the following attributes:
	- `x.key` stores the value of the element.
	- `x.next` is a pointer to the next element in the list.
	- `x.prev` is a pointer to the previous element in the list (For double linked lists)
- The list itself has a single attribute `L.head` which points to the first element in the list.
- If `L.head == nil` the list is empty.
- If `x.next == nil` then `x` is the last element in the list
## 3.1 Operations
### 3.1.1 List-Search
- List-Search takes a list `L` and a value `k` as the inputs
- Finds the first element in the list with key `k`.
- Returns a pointer to this element (NIL if the element does not exist).
- The worst case runtime is $\Theta(n)$ since all `n` elements has to be looked through.
[[list_search_pseudo.png|List-Search Pseudo Code]]
### 3.1.2 List-Prepend
- Takes a list `L` and an element `x` as inputs.
- The element `x` is placed as the first in the list.
- `L.head` is updated and the pointer from the old `L.head` is transferred to `x`.
- It runs in $\Theta(1)$ time

[[list_prepend_pseudo.png|List-Prepend Pseudo Code]]
### 3.1.3 List-Insert
- Takes in two elements `x`, `y`.
- Element `x` is inserted after `y` in the list.
- The pointers from `y` are transferred to `x` and `x.next` should point to `y`.
- It runs in $\Theta(1)$ time

[[list_insert_pseudo.png|List-Insert Pseudo Code]]
### 3.1.4 List-Delete
- Takes in a list `L` and an element `x`.
- Deletes `x` from the list and updates pointers
- Runs in $\Theta(1)$ time

[[list_delete_pseudo.png|List-Delete Pseudo Code]]
# 4 Priority Queues
Priority Queues is an abstract data structure. It is a dynamic queue, where the order is not determined by the order of insertion, but by a given key. It can be compared to an emergency room, where the person with the sprained angle came in first, but the person with a punctured lung is still in the front of the queue.
## 4.1 Operations
### 4.1.1 Insert
- Takes in a heap `A` and an element `x`.
- We increase `A.heap-size` by 1 to make space (Making sure that `A.heap-size < A.length`).
- We insert `x` at the back of the heap and lets it rise up by switching it with every parent while it is bigger.

Has a runtime complexity of $\Theta (\log n)$. 

[[priority_queue_insert_pseudo.png|Insert Pseudo Code]]
### 4.1.2 Heap-Extract-Max
- Saves the biggest (and first) element in a variable, `max`.
- Moves the last element to index 1.
- Decrease `A.heap-size` by 1.
- Call `Max-Heapify(A, 1)`.
- Return max.

Has a runtime complexity of $\Theta (\log n)$. 

[[heap_extract_max_pseudo.png|Heap-Extract-Max Pseudo Code]]
