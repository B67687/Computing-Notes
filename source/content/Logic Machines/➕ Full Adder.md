
Full Adders are the simplest forms of general adder circuits that are able to add a lot of numbers together

## 🍕 Sum Logic

Given **place-values** `A`, `B`, and the **carry-in** `C_in`

Through knowledge of [[🔢 Adders — Half and Full | half adders]] we would add `A` and `B` first then add the carry-in, `C_in` through `XOR`

$$
(A \oplus B) \oplus C_{in}
$$

But since `XOR` is associative, the sequence or grouping of addition doesn't matter

> [!tip] General Formula for Sum
> $$
> \text{Sum} = A \oplus B \oplus C_{in}
> $$

## 🏋️ Carry Logic

Carry is a little harder to find a general form so we start from an exhaustive form, where **any pair produces a carry**
> `A` and `B` produces a carry
>
> **OR**
>
> `A` and `C_in` produces a carry
>
> **OR**
>
> `B` and `C_in` produces a carry

> [!example] Why we find pairs
> Pairs are the simplest constructs of condition, we can **construct sums of more summands through sums of less**, and 2 is the least amount
>
> > i.e. We don't have to find if any 3 produces a carry, as that would be under satisfied under a simpler condition of **2 pairs**

Thus, we get the first Exhaustive Form:

> [!note] Exhaustive Form
> $$
> C_{out} = A \cdot B + A \cdot C_{in} + B \cdot C_{in}
> $$

We can factor the expression a bit more once we realise that 2 terms share `C_in` as a factor

> [!note] Intermediate Simplified Form
> $$
> C_{out} = A \cdot B + (A + B) \cdot C_{in}
> $$

But `A` and `B` cant be both true at the same time——a condition that is included with `inclusive OR`——so we have to use `exclusive OR`

> [!tip] General Formula for Sum
> $$C_{out} = A \cdot B + (A \oplus B) \cdot C_{in}$$
