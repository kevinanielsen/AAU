# 1 Heaps
- For a queue with room for `n` elements, we use an array `A[1:n]`.
- The actual amount of elements can be accessed with the attribute `A.heap-size`.
- A heap can be represented as an almost complete tree, where all levels are filled out except maybe the last, which although is filled out from left to right.
- We say that an element in place `A[i]` is a parent node to the elements in place `A[2i]` and `A[2i+1]`, which are the left- and right children.
- A node has the height of the number of edges from the root to the node. The height of the entire heap is height of the root. Since a heap is an (almost) complete binary tree, its height is $\Theta(\log n)$. 

There are two types of heaps, Max-Heaps and Min-Heaps. Each need to fulfill their respective heap-property.

The Max-Heap property states: For all nodes `i > 1`, `A[Parent(i)] >= A[i]` needs to hold, i.e., the parent node needs to have a higher value than its children.

Likewise, the Min-Heap property states: For all nodes `i > 1`, `A[Parent(i)] <= A[i]` needs to hold, i.e., the parent node needs to have a lower value than its children.
## 1.1 Operations
### 1.1.1 Parent, Right and Left
The parent, right and left elements of a node can be accessed using simple calculations:
```pseudo
Parent(i)
  return floor(i / 2)

Left(i)
  return 2i

Right(i)
  return 2i+1
```

### 1.1.2 Max-Heapify
- The purpose is to uphold the max-heap property
- Takes in an array `A` and an index `i`, where `Left(i)` and `Right(i)` are max-heaps, but where `A[i]` might not be less than `Left(i)` and `Right(i)`
- The output is a reorganized array, which now fulfills the max-heap property for `A[i]`.
It works by
1. Comparing `A[i]` with `A[Left(i)]` and `A[Right(i)]` to find out what is the highest value.
2. Moves `A[i]` down the tree by switching it with its biggest child.
3. Continues recursively until `A[i]` is the biggest value or a leaf.

[[max_heapify_pseudo.png|Max-Heapify Pseudo Code]]

The worst case is that the last level of the tree is half filled, because then the biggest sub-tree will have a max of $2n/3$ nodes, meaning that the size of the biggest sub-problem is $T(2n/3)$, giving a recursion of $T(n)=T(2n/3)+\Theta(1)$. 

The runtime of Max-Heapify is $\Theta(\log n)$.
### 1.1.3 Build-Max-Heap
- Is used for constructing a heap from an unorganized array `A`.
- The last half of `A` can be thought of as leaves on the tree, and are therefore trivially correct max-heaps.
- Therefore, we only call max-heapify on the elements from spot $n/2$ down to 1 to fulfill the heap property on the whole array.

[[build_max_heap_pseudo.png|Build-Max-Heap Pseudo Code]]

It has a total runtime of $O(n \log n)$.
### 1.1.4 Heapsort
1. To sort `A`, we start off by converting it to a max-heap
2. Now, we know that the first element is the largest, and that it should be last in the sorted array. 
3. We then switch it with the last element and decrease `A.heap-size` by 1, we then call Max-Heapify on the new first element and continue until the heap is empty, but the underlying array is sorted in ascending order.

[[heapsort_pseudo.png|Heapsort Pseudo Code]]

The runtime is of $O(n\log n)$. It sorts in-place and therefore only takes up $\Theta (1)$ extra space.
# 2 Binary Search Trees
Is represented using pointers instead of an array, meaning we do not need to know the size of the tree when initializing it.
- Every node `x` is an object with 4 attributes.
	- `x.key` stores the value/key of the node.
	- `x.p` points to the parent node.
	- `x.left`, `x.right` points to the left and right children.
- `T.root` points to the root of the tree. `x.p = NIL` if and only if `x = T.root`.

We can extend the tree so it does not only have 2 children for each node, we do this by replacing `x.left`, `x.right` with `x.left-child` and `x.right-sibling`, in this way we can still traverse the whole tree, but there is no limitation on the amount of children each node can have. (This would not be called a binary tree.)

A valid binary search tree fulfills the Binary-Search-Tree property, stating that: For two nodes `x,y` in a binary search tree:
- If `y`is a node of the left sub-tree of `x`, then `y.key <= x.key`.
- If `y`is a node of the right sub-tree of `x`, then `y.key >= x.key`.

So, for a heap the children must have lower values than the parents, in a binary search tree everything to the left must be lower than or equal, while everything on the right must be bigger than or equal.
## 2.1 Operations
### 2.1.1 Inorder-Tree-Walk
We can use the BST-property to print all keys in order.
- It takes a node `x`and prints first all keys in the left subtree, then `x.key`, and lastly all keys in the right subtree

[[inorder_tree_walk_pseudo.png|Inorder-Tree-Walk Pseudo Code]]

It has a runtime complexity of $\Theta(n)$ (for a tree with `n` nodes).
### 2.1.2 Iterative-Tree-Search
- A while-loop tests if `x` is NIL or if `x.key = k`.
- If `k` is less than `x.key`, we look in the left subtree, otherwise we look in the right subtree.
- It ends once we have found the right element or `x` is set to NIL.

[[iterative_tree_search_pseudo.png|Iterative-Tree-Search Pseudo Code]]

Since every iteration moves down a level in the tree, the algorithm has a runtime complexity of $O(h)$.
### 2.1.3 Tree-Minimum & Tree-Maximum
[[tree_minimum_pseudo.png|Tree-Minimum Pseudo Code]]
[[tree_maximum_pseudo.png|Tree-Maximum Pseudo Code]]

Both run in $O(h)$. 
### 2.1.4 Tree-Successor
- Given a node `x` in a BST `T`, Tree-Successor finds the node that has the smallest key that is bigger than `x.key`.
- Either the successor is the smalles element in the right subtree of `x`, or
- We need to crawl up the tree until we find the first node that has `x` in its left subtree.

[[tree_successor_pseudo.png|Tree-Successor Pseudo Code]]

Runs in $O(h)$.
### 2.1.5 Tree-Insert
- Takes in a tree `T` and a node `z`.
- We define `x` to be the node, which we compare with `z` (starting off by using `T.root`), and `y` as the parent to `x`.
- As long as `x` is not NIL, we compare `z.key` with `x.key` and move either left or right in the tree.
- When `x` is NIL, we set `z`'s parent to be `y`.
- If `y` is NIL, then the tree is empty, and `z` is the new root. Otherwise, we insert `x`as either the left of right child of `y`.

[[tree_insert_pseudo.png|Tree-Insert Pseudo Code]]

The worst case scenario is if the insertion data is sorted, then we will basically get a linked list and the operations will have a runtime complexity of $O(n)$. If the data is in a random order instead, then the runtime will be the expected height of the tree, $O(\log n)$.
### 2.1.6 Tree-Delete
Deleting a node from a BST requires that we take account for the scenario that it might have two children. If that is the case, we take the left-most node of the right subtree, and set it as the new element.
- First, we cover the scenario where `z` only has a single child, in which case we just move the child up.
- If `z` has two children, we find its successor `y`.
- If `y` is not its right child, we
	- replace `y` with `y`'s right child and
	- move pointers so `y`'s right child is now `z`'s right child.
- We then know that `y` is the right child of `z` and we can then just replace `z` with `y`.

[[tree_delete_pseudo.png|Tree-Delete Pseudo Code]]
[[transplant_pseudo.png|Transplant Pseudo Code]]

It has a runtime complexity of $O(h)$.
# 3 Red-Black Trees
The downside of BST's are that if the tree is unbalanced, we have a worst case where the height of the tree equals the amount of entires, meaning that all our operations have a runtime of $O(n)$ (because $h=n$).

Red-Black Trees are a modified version of BST's where:
- All nodes include an attribute, $color \in \{RED, BLACK\}$.
- We represent leafs as NIL-pointers.
- A red-black tree is a BST that fulfills the red-black properties:
	1. All nodes are either red or black
	2. The root is black.
	3. All leafs are black.
	4. If a node is red, then its children are black.
	5. All simple paths from a node to a leaf in one of its subtrees contain the same amount of black nodes.
- We call the amount of black nodes on a simple path from a node `x` (not including `x` itself) to a leaf, the 'black height', `bh(x)`.

With these properties, we can guarantee that the height of a RBT with `n` internal nodes has a height of at most $2\log(n+1)$, which is in $O(\log n)$. 
## 3.1 Operations
### 3.1.1 Left-Rotate
- Is used for fixing possible breaks in the RBT-properties

[[rbt_left_rotate_pseudo.png|Left-Rotate Pseudo Code]]
### 3.1.2 RB-Insert-Fixup
- If `z` is red, then we enter a while-loop if its parent is also red.
- We check if `z`'s parent is a left child.
- If the sibling of `z`'s parent is red, then both it and the parent of `z` is changed to black, while the grandparent of `z` is changed to red, and we continue from the grandparent.
- If the sibling of the parent was not red, and `z` is a right child, then we do a Left-Rotate.
- If `z` is a left child, then we do a Right-Rotate (the inverse of Left-Rotate).

[[rb_insert_fixup_pseudo.png|RB-Insert-Fixup Pseudo Code]]
### 3.1.3 RB-Insert
- Starts off with Tree-Insert from BST's, then sets the value of `z.left`, `z.right` to NIL pointers, and the color of `z` to RED.
- The "danger" with this, is that it can break a few of the RBT-properties.
	- Root must be black - if the tree was empty before the insert, and the new note is set to RED, then this property is no longer fulfilled
	- If a node is red, then both its children must be black - if the new nodes parent is red, then this property is broken as well.
- This is why the last thing RB-Insert does, is running RB-Insert-Fixup.

[[rb_insert_pseudo.png|RB-Insert Pseudo Code]]
### 3.1.4 RB-Delete
- We check if `z` only has 1 child, then replace `z` with that child. 
- If `z` has 2 children, we find its successor `y`.
- If `y` is below in the tree, we replace `y`with its right child and let it point to `z`'s right child.
- Now, we can replace `z` and `y` with each other and give `z`'s left child to `y`.
- Lastly, we check if the color of the node we adjusted (either `z` or its successor `y`) was black, then we need to fix the tree.

For this procedure, the same things can go wrong as in RB-Insert, but now, we can also break the fifth property of RBT's, the fact that all simple paths from a node to a leaf in one of its subtrees must contain the same amount of black nodes, as we have removed a black node.

We then run RB-Delete-Fixup, which consists of a while loop, which runs as long as `x`is not the root and `x` is not black.

[[rb_delete_fixup_pseudo.png|RB-Delete-Fixup Pseudo Code]]
[[rb_delete_pseudo.png|RB-Delete Pseudo Code]]