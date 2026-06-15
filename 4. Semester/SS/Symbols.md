![[intersection and union of sets.png]]

- **$L_1$** = $\{a, b\}$
- **$L_2$** = $\{b, c\}$

### $L_1 \circ L_2$ : Concatenation

This operation glues the languages together. It creates a new language containing all possible strings formed by taking a string from $L_1$ and appending a string from $L_2$ to the end of it.

- **Meaning:** "Everything in $L_1$ followed immediately by everything in $L_2$."
- **Example Result:** $\{ab, ac, bb, bc\}$
    _(Note: The circle $\circ$ is sometimes omitted, written simply as $L_1L_2$)_.

### $L_1 \cup L_2$ : Union

This is the standard set union. It combines the contents of both languages into a single, larger language.

- **Meaning:** "Strings that are in $L_1$, OR in $L_2$, or in both."
- **Example Result:** $\{a, b, c\}$

### $L_1 \cap L_2$ : Intersection

This looks for the overlap between the two languages. It creates a new language containing only the strings that exist in both sets simultaneously.

- **Meaning:** "Strings that are strictly in BOTH $L_1$ AND $L_2$."
- **Example Result:** $\{b\}$

### $L_1 \setminus L_2$ : Set Difference

As we touched on in your previous question, this operation subtracts one set from another. It keeps everything from the first language, except for the strings that also appear in the second language.

- **Meaning:** "Strings that are in $L_1$, but NOT in $L_2$."
- **Example Result:** $\{a\}$