$$T(n)=aT(n/b)+f(n)$$
Hvor $a$ og $b$ er konstanterne, og vi kræver, at $a \ge 1, b > 1$. Vi kalder $f(n)$ **the driving function**, og kræver at den er en asymptotisk positiv funktion.

---
> For a recurrence of the form $T(n)=aT(n/b)+f(n)$, the asymptotic behavior of $T(n)$ can be characterized as follows:
> 1. If there exists a constant $\epsilon \gt 0$ such that $f(n)=O(n^{\log_ba-\epsilon})$, then $T(n)=\Theta (n^{\log_ba})$.
> 2. If there exists a constant $k \ge 0$ such that $f(n)=\Theta(n^{\log_ba}\lg^kn)$ then $T(n)=\Theta(n^{\log_ba}\lg^{k+1}n)$.
> 3. If there exists a constant $e \gt 0$ such that $\Omega (n^{\log_ba+e})$ and if $f(n)$ additionally satisfies the regularity condition $af(n/b)\le cf(n)$ for some constant $c \lt 1$ and all sufficiently large $n$, then $T(n)=\Theta(f(n))$.

Hvordan bruges det?
1. Identificer om rekursionen har formen $T(n)=aT(n/b)+f(n)$.
2. Gør udtrykket $n^{\log_ba}$ simplere ved at indsætte $a$ og $b$. 
3. Undersøg hvilket af de 3 cases der holder, altså
	1. $f(n)=O(n^{\log_ba-\epsilon})=O(n^{\log_ba}/n^\epsilon)$, hvor $\epsilon \gt 0$. 
	2. $f(n)=\Theta(n^{\log_ba}\lg^kn)$, for $k\ge 0$
	3. $f(n)=\Omega(n^{\log_ba+\epsilon})=\Omega(n^{\log_ba} * n^\epsilon)$, hvor $\epsilon \gt 0$. 
4. Konklusionen kan stadig se kompliceret ud så reducer yderligere

| Case       | If f(n) is...                   | Use This Rule                                                         | Then...                      |
| ---------- | ------------------------------- | --------------------------------------------------------------------- | ---------------------------- |
| **Case 1** | **smaller** than $n^{\log_b a}$ | $f(n) = O(n^{\log_b a - \epsilon})$                                   | $\Theta(n^{\log_b a})$       |
| **Case 2** | **same** as $n^{\log_b a}$      | $f(n) = \Theta(n^{\log_b a})$                                         | $\Theta(n^{\log_b a} \lg n)$ |
| **Case 3** | **larger** than $n^{\log_b a}$  | $f(n) = \Omega(n^{\log_b a + \epsilon})$ **and** satisfies regularity | $\Theta(f(n))$               |

A master recurrence describes the running time of a divide-and-conquer algorithm that divides a problem of size $n$ into $a$ subproblems, each of size $n/ b < n$

## Eksempler
**Merge-Sort**
Merge-Sorts køretid kan skrives op som rekursionen $T(n)=2T(n/2)+\Theta(n)$.
$$
\begin{aligned}
a&=2 &b=2 &&f(n)=\Theta(n)
\end{aligned}
$$
$$n^{\log_ba}=n^{\log_22}=n^1=n$$
Derefter tjekkes om den passer på nogen af teoremets cases:
- Er $f(n)=O(n^{1-\epsilon})$ for nogen $\epsilon \gt 0$?
- Er $f(n)=\Theta(n^1\lg^kn)$ for nogen $k \ge 0$?
	- Ja - For $k=0$ har vi $\Theta(n^1\lg^0n)=\Theta(n)=f(n)$. 
	- Dette er case 2 i teoremet, som fortæller os at $T(n)=\Theta(n^{\log_ba}\lg^{k+1}n)$, hvilket for $a=2,b=2,$ og $k=0$ giver at $T(n)=\Theta(n\lg n)$.

**Eksempel 2**
$T(n)=3T(n/4)+n\lg n$
$$
\begin{aligned}
a=3, &&b=4, &&f(n)=n\lg n
\end{aligned}
$$
Vi indsætter og forenkler: $n^{\log_ba}=n^{\log_43} \approx n^{0.792}$.
Og så tjekker vi cases:
1. Er $f(n)=O(n^{0.792-\epsilon})$ for nogen $\epsilon \gt 0$?
	1. Nej, for $n^{0.792} \lt n$, hvilket stadig må gælde hvis vi fratrækker en positiv konstant i eksponenten, og da $f(n)=n\lg n$ kan $n^{0.792-\epsilon}$ altså ikke være et upper bound.
	2. Er $f(n)=\Theta(n^{0.792}\lg^kn)$ for nogen $k \ge 0$?
		1. Nej, for hvis $k \le 1$ vokser $n^{0.792}\lg^kn$ for langsomt, og hvis $k \gt 1$ vokser det for hurtigt.
	3. Er $f(n)=\Omega(n^{0.792+\epsilon})$ for nogen $\epsilon \gt 0$?
		1. Ja, $n^x$ er et lower bound for $n\lg n$ så længe $x$ er mindre end $1$
		2. Case 3 giver os at $T(n)=\Theta(f(n))=\Theta(n \lg n)$.