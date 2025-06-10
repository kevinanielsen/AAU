- Also called dictionaries
- A data structure that can map from a key to a value
- An array could be considered a symbol table, where the key is the index and the value is the element on that index.
- Hash tables supports all operations in O(1) time.
# 1 Direct-Address Tables
- Basically an array, where we store elements that all have a unique key associated.
- The keys are in $U=\{0,1,\dots,m-1\}$ 
- We represent the table with an array `T[0:m - 1]`, where we have space for `m` elements.
- The element with key `k` is on space `T[k]`. If `T[k] = NIL`, when the element does not exist in `T`.
- With `m` keys in `U`, and `n` elements in `T` there are `m - n` empty spaces in `T`.
- All operations are trivial and have a runtime complexity of $O(1)$.
# 2 Hash Tables
## 2.1 Hashing
Instead of having space for all $|U|$ keys, we can use a hash function, that maps from a key to a spot in a hash table.
- A hash function $h:U \to \{0,1,2,\dots, m-1\}$ is a function from the universe of keys to a number between 0 and $m-1$.
	- E.g., $h(k)=k\mod m$.
- The hash table `T[0:m - 1]` is an array with space for `m` elements, and we assume that $m \ll |U|$ (that `m` is much smaller than the size of `U`).
- An element with key `k` would be on spot `T[h(k)]`.
### 2.1.1 Collisions
- Two or more keys can risk getting the same hash value, i.e., $h(k_1)=h(k_2)$. This is called a collision, since both keys would have to be in the same spot.
### 2.1.2 Static Hashing
- Uses the same hash-function every time
- We hope that we can hash it in a way that is independent from patterns in the input data.
- Two simple methods:
	- The division method: $h(k)=k\mod m$
		- Fast and efficient
		- Good if `m` is a prime, that is not close to a power of 2.
	- The multiplication method: $h(k)=\lfloor m(kA- \lfloor kA\rfloor)\rfloor$.
		- Where $A$ is a constant between 0 and 1
		- $m$ can be picked independently from $A$ and works well as a power of 2.
- There are no guarantees with static hashing
### 2.1.3 Random Hashing
- We define a family $\mathcal H$ of hash-functions that map $U$ to $\{0,1,\dots,m-1\}$.
- When our program starts, we pick a random hash-function $h\in \mathcal{H}$. 
- This protects against attacks looking for $n$ keys which all hash to the same value.
- The family of $\mathcal H$ hash-functions can be defined with
	- Number theory - using primes and modulus.
	- The multiplication method - a version of the previously mentioned method, guaranteeing that the risk of collision is at most $2/m$.
### 2.1.4 Chaining
When we have collisions, we need a method of handling this. The most common method is called chaining.
- We save a linked list on each spot in `T`. 
- Collisions are just added as an element to the list.
## 2.2 Insert, Search and Delete
### 2.2.1 Insert
- Insert in the start of the list at `T[h(x.key)]`.
- Has a runtime complexity of $O(1)$.
### 2.2.2 Delete
- Delete `x` from list at key `T[h(x.key)]`
- Has runtime complexity of $O(1)$ (for doubly linked lists).
### 2.2.3 Search
- Look for `k` in the list at spot `T[h(k)]`.
- Has a runtime complexity of $O(n)$.
## 2.3 Open Addressing
- A popular alternative to chaining, saves all elements directly in the table and uses probing to solve collisions.
- Every spot in the table has either an element or NIL
- Since the table can get filled, will $n \le m$, meaning our load factor is $\alpha \le 1$.
- Since we are avoiding pointers, the memory is freed and it can be used to make a bigger table and thereby shorter search-times.
### 2.3.1 Probing
- We 'probe' the table for an available spot, one index at a time.
- The 'probe-sequence' is the order in which we check for spots in the table, and is a permutation of $(0,1,\dots,m-1)$.
- The hash function is extended to include the probe-number as input: $h:U \times \{0,1,\dots,m-1\} \to \{0,1,\dots,m-1\}$.
- The probe sequence is a tuple: $\{h(k,0), h(k,1),\dots, h(k,m-1)\}$.
### 2.3.2 Hashing in Open Addressing
- We want independent uniform permutation hashing, meaning that the probe-sequence has an equal probability to generate any of the $m!$ permutations of $(0,1,\dots,m-1)$.
- Since this is difficult to implement and less will do, we primarily use two techniques called $m$ and $m^2$ probe-sequences:
	- Linear Probing
	- Double Hashing
### 2.3.3 Linear Probing
$$h(k,i)=(h'(k)+i)\mod m$$
- We use an 'auxiliary' hash function $h':U \to \{0,1,\dots,m-1\}$.
- The probe-number $i$ is used to skip 1 spot every time
- If $m=8$ and $h'(k)=\lfloor k/3 \rfloor$, we would for $k=10$ get the probe-sequence $(3,4,\dots,7,0,1,2)$.
- It's easy to implement but can only generate $m$ probe-sequences.
- It has a tendency to create primary clustering, meaning long sequences where the spots are taken.
### 2.3.4 Double Hashing
Linear probing is a special case of a more general method called double hashing:
$$h(k,i)=(h_1(k)+ih_2(k)) \mod m$$
- We use 2 auxiliary hash functions, $h_1$ and $h_2$.
- During the first check where $i=0$, we move to spot $T[h_1(k) \mod m]$ and skip $h_2(k)$ spots forward each time, meaning we can interpret $h_2$ as a sort of 'stepper'-function.
- To guarantee that the entire table gets probed, the value of $h_2$ needs to be a prime relative to $m$.
	- Either let $m$ be a power of 2 and make sure that $h_2$ always returns uneven numbers, 
	- or let $m$ be a prime and make sure $h_2$ always returns a number less than $m$.
## 2.4 Operations
### 2.4.1 Hash-Insert
- Initialize the probe to 0
- Hash the key and the probe-number and save the value in a variable `q`.
- If `T[q]` is empty, insert `k` and return `q`.
- Else, increment `i` and repeat until `i = m`.
- If we get past the loop, the table is full.

[[hash_insert_pseudo.png|Hash Insert Pseudo Code]]
### 2.4.2 Hash-Search
- Initialize the probe to 0
- Hash the key and probe-number and save the value in a variable `q`.
- If `T[q]` is empty, we return `q`.
- Else, we increment `i` and repeat until we find an empty spot or `i = m`.
- If we get past the loop, `k` doesn't exist in `T`.

[[hash_search_pseudo.png|Hash Search Pseudo Code]]
### 2.4.3 Deletion
Don't use Open Addressing if deletion is needed, use chaining then.