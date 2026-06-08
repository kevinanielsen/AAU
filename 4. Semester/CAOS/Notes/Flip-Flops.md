## The State Variables
- **$Q(t)$:** This is your **Current State** (the value currently stored in the flip-flop).
- **$Q(t+1)$:** This is your **Next State** (the value the flip-flop will update to _after_ the clock ticks).
- **$Q$ and $\overline{Q}$ (or $Q'$):** These are the physical output pins. $Q$ outputs the current state, and $\overline{Q}$ always outputs the exact inverse/complement of $Q$.
## The Graphic Symbols
- **The Triangle ($\rhd$):** On circuit diagrams, the input pin marked with a small triangle is the **clock input**. It indicates that the flip-flop is "edge-triggered" (it only reads inputs and changes state when the clock signal transitions).
- **The Bubble ($\circ$):** If the clock triangle has a small circle (a bubble) in front of it, it triggers on the **Negative Edge** (when the clock falls from 1 to 0). If there is no bubble, it triggers on the **Positive Edge** (when the clock rises from 0 to 1).

**The Flip-Flop Types (The Inputs):** The letters naming the flip-flops (D, J-K, T) just represent their specific input pins and how they calculate the Next State.
## D Flip-Flop (Data)
This is a direct assignment. The "Characteristic Equation" is simply **$Q(t+1) = D$**.
- _Developer Translation:_ `nextState = D;` Whatever value is sitting at input pin $D$ gets saved as the new state on the clock tick.

**2. J-K Flip-Flop** This has two inputs ($J$ and $K$), giving you four modes of operation. Its equation is **$Q(t+1) = JQ' + K'Q$**.

- _Developer Translation:_
    - If `J=0, K=0`: **No change** (`nextState = currentState`).
    - If `J=0, K=1`: **Reset** (`nextState = 0`).
    - If `J=1, K=0`: **Set** (`nextState = 1`).
    - If `J=1, K=1`: **Toggle** (`nextState = !currentState`).

**3. T Flip-Flop (Toggle)** This has one input ($T$) and acts as a simple switch. Its equation is **$Q(t+1) = T \oplus Q$** (T XOR Q).

- _Developer Translation:_
    - If `T=0`: **No change** (`nextState = currentState`).
    - If `T=1`: **Toggle** (`nextState = !currentState`).

Whenever the exam asks you to derive a "Next State" for a state table (like in Question 4 of your test exam), you will simply look at the current inputs and the current state $Q(t)$, and plug them into these exact characteristic equations to find out what $Q(t+1)$ will be.
# Analysis of Sequential Circuits
![[analysis of sequential circuits.png|Analysis of Sequential Circuits|600]]
![[state diagram.png|State Diagram|600]]