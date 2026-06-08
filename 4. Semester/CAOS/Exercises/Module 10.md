1. **A memory system has 2048 words, each 32 bits wide.**
	**a) What is the total memory capacity in bits and bytes?**
$$2048 \times 32 = 65.536\text{ bits}$$
$$65.536 / 8=8192=8\text{K bytes}$$
	**b) How many address lines are required to address each word?**
$$2^{11}=2048 \Rightarrow n=11$$
2. **Consider a machine with 64 MB physical memory and a 32-bit virtual address space. If the page size is 4KB, what is the approximate size of the page table?**
32-bit virtual address space means $2^{32}$ bytes of virtual memory
Page size is 4KB, which is $2^{12}$ bytes.
The total number of pages: $$\dfrac{2^{32}}{2^{12}}=2^{20} \text{ pages}$$
$2^{20}$ is the number of Page Table Entries (PTEs) that the page table will have.
To find the Physical Frame Number (PFN):
- Physical Memory: 64 MB, which is $2^{26}$ bytes.
- Number of physical frames: $\dfrac{2^{26} \text{ bytes}}{2^{12} \text{ bytes per page}}=2^{14} \text{ frames}$.
Since there are $2^{14}$ physical frames, we need 14 bites to store the frame number. This fits within a standard 32-bit (4-byte) integer. Unless stated otherwise, assume 4 bytes for the PTE size.

Total Page Table Size is calculated by multiplying the number of entries by the size of each entry:
$$2^{20} \text{ entries} \times 4 \text{ bytes}/\text{entry}=4,194,304 \text{ bytes}$$
Therefore, the approximate size of the page table is **4 MB**.

3. **Given the following instruction sequence:**
	**a) Explain the data flow between memory and registers.**

	**b) Discuss how temporal and spatial locality apply to these operations and how the memory hierarchy affects execution time.**

4. **Suppose that a memory system has the following**
- **10-bit virtual addresses**
- **There are 16 pages of virtual memory**
- **There are 8 page frames of physical memory**
- **The memory is byte-addressable**
	**a) What is the page size in bytes?**
$$
S_{VM}=2^{10}=1KB
$$
$$
P=\dfrac{2^{10}}{2^4}=2^6=64\text{ bits}=\underline{\underline{4\text{ bytes}}}
$$
	**b) How many bits are needed for the physical address?**
$$64\text{ bits} \times 8 = 512 \text{ bits}$$
	**c) What is the total virtual memory size and the total physical memory size?**
