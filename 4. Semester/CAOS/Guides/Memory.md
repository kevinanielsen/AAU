When solving these, the most important rule to remember is that **the offset bits never change** between the virtual address and the physical address. The page size dictates the offset, and both addresses share it.
## The Variables
- **$N_{VA}$** = Number of bits in a Virtual Address
- **$N_{PA}$** = Number of bits in a Physical Address
- **$P$** = Page Size (in bytes)
- **$p$** = Number of Page Offset bits
- **$V_{\text{pages}}$** = Total number of Virtual Pages
- **$P_{\text{frames}}$** = Total number of Physical Page Frames
- **$S_{VM}$** = Total Virtual Memory capacity (in bytes)
- **$S_{PM}$** = Total Physical Memory capacity (in bytes)

## 1. Memory Capacities
If you know the number of address bits, you can find the total memory capacity. Conversely, if you know the capacity, you can find the number of address bits using log base 2.

**Total Virtual Memory Size ($S_{VM}$):**
$$S_{VM} = 2^{N_{VA}} \text{ bytes}$$
$$S_{VM} = V_{\text{pages}} \times P$$

**Total Physical Memory Size ($S_{PM}$):**
$$S_{PM} = 2^{N_{PA}} \text{ bytes}$$
$$S_{PM} = P_{\text{frames}} \times P$$

## 2. Page Size and Offset Bits
The page size determines exactly how many bits you need to point to a specific byte _inside_ that page.

**Finding the Offset Bits ($p$):**
$$P = 2^p \iff p = \log_2(P)$$

**Finding Page Size from Pages & Memory:**
$$P = \frac{S_{VM}}{V_{\text{pages}}} = \frac{S_{PM}}{P_{\text{frames}}}$$

## 3. Page Counts and Frame Counts
If you need to figure out how many chunks of memory exist, divide the total memory by the chunk size (the page size).

**Number of Virtual Pages ($V_{\text{pages}}$):**
$$V_{\text{pages}} = \frac{S_{VM}}{P} = 2^{N_{VA} - p}$$

**Number of Physical Frames ($P_{\text{frames}}$):**
$$P_{\text{frames}} = \frac{S_{PM}}{P} = 2^{N_{PA} - p}$$

## 4. Anatomy of the Addresses

Every address is split into two parts: the identifier (which page/frame you are in) and the offset (exactly where you are inside that page/frame).

**Virtual Address Breakdown ($N_{VA}$ bits total):**

- **VPN (Virtual Page Number) bits** = $N_{VA} - p$
    - _(Alternatively: $\text{VPN bits} = \log_2(V_{\text{pages}})$)_
- **Offset bits** = $p$

**Physical Address Breakdown ($N_{PA}$ bits total):**

- **PFN (Physical Frame Number) bits** = $N_{PA} - p$
    - _(Alternatively: $\text{PFN bits} = \log_2(P_{\text{frames}})$)_
- **Offset bits** = $p$

## Quick Power-of-2 Cheat Codes
Since almost all of these problems require moving between exponents and bytes, keep these conversions handy so you don't have to calculate them manually:

- $2^{10} \text{ bytes} = 1 \text{ KB}$
- $2^{20} \text{ bytes} = 1 \text{ MB}$
- $2^{30} \text{ bytes} = 1 \text{ GB}$
- $2^{40} \text{ bytes} = 1 \text{ TB}$

_(Example: If you have a $32$-bit address space, that is $2^{32} = 2^2 \times 2^{30} = 4 \text{ GB}$ of memory)._