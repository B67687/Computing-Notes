## 🧠 Motivation

- Boolean expressions describe the logical relationships between objects  
- When we have a lot of boolean expressions, the relationships become more and more complex  
- Some of these relationships can we grouped together and simplified through the many relationship laws of logical expressions  

> [!info] Simplification Laws  
> There are some laws that help us simplify complex logical relationships. The simplest of these laws are:  
> 
> **Identity**
> > Simplifies relationships with non-contingent logical expressions into just the contingent one  
> 
> **Domination** 
> > Simplifies relationships with non-contingent expressions into just the non-contingent expression
> 
> **Idempotent** 
> > Simplifies repeated relationships into 1  
> 
> **Double Negation**
> > Simplifies double negatives to just the non-negative form  
> 
> **Complement**
> > Simplifies opposite relationships into non-contingent expressions  
> 
> **Absorption**
> > Simplifies relationships that are already covered 
> 
> **Consensus**: 
> > It's absorption but a different more complicated version  
> 
> Check out [[🧮 Boolean Algebra#📏 Fundamental Laws (Logical Form) | Boolean Algebra Laws]]

---

## 🌍 Multivariable Application
In large multivariables, **Identity**, **Domination**, **Idempotency**, **Double Negative** can be easily spotted

Leaving **Complement**, **Absorption** and **Consensus** as the harder ones to spot

---

## 🧽 Laws of Coverage

> [!example] Subset Coverage
> **Absorption** simplifies expressions where one term already **includes** another.
>
> ```
> A + AB = A
> A(A + B) = A
> ```
>
> The logic: if **A is true**, then **AB** is also true whenever B is true—but we don’t need to say both.
>
> So the broader term **A** absorbs the more specific **AB**.

> [!example] Intercept Coverage
> **Consensus** removes a term that is **logically implied** by two others.
>
> ```
> AB + A'C + BC = AB + A'C
> ```
>
> The term **BC** is already covered by the overlap of **AB** and **A'C**.
>
> So it’s redundant and can be removed.

> [!note] Coverage 
>  Both Absorption and Consensus is about that fact that some terms are already covered by other terms when in OR conditions
>  
>  Which allows us to eliminate them

---

## 🧩 Venn Diagrams Visualises Coverage

We already have aa way to see these relationships, using **Venn diagrams** to help us to **see coverage** more easily

---

## 🥨 Complement Law
> [!tip] Spotting Contradictions  
> For complement, actually it's really easy to spot the contradiction case in because they happen only with AND.  
> 
> So we just look for the complement of each individual variable to find contradictions to simplify to 0, **negating entire expressions in one go**  

```
Contradiction Law
	B ⋅ B' = 0

Multivariable Usage
	ABB' = A ⋅ BB' = A ⋅ 0 = 0
```

> [!warning] Tautology Is Harder  
> But for the tautology, it is not nearly as obvious in multivariable situations.  
> Because it simplifies to 1, it leaves more expressions to group still
> 
> It is not as easy to see all the combinations that simplify, and all of the best grouping of combinations (through **Idempotency Law**) that provides the most simplification

```
Tautology Law
	B + B' = 1

Multivariable Usage
	AB + AB' = A ⋅ (B + B') = A ⋅ 1 = A
```

Thus we are to find a systematic way to much more easily observe the tautology groupings between multivariable boolean expressions—which means group those that share the same variables  

> [!tip] Optimal Groups
> To easily find the **most simplified expression** by finding the most optimal groupings that 
> - **Maximises grouping size** 
> - **Minimising number of groups**  

---

## 🧮 Method for Karnaugh Maps

- Tautology works when we have complementary pairs, e.g. A + A'  
- For multivariable expressions that share all variables (complements are included as part of sharing variables), at least 2 variables will be shared—this is what makes it multivariable  

> [!example] Table Construction  
> Instead of comparing many variables at once, we can compare just pairs of variables by:  
> - Listing all of their combinations in axis of a table  
> - Listing combinations of other separate pairs on the other axis  

> [!tip] Gray Code Optimization  
> To easily spot complement differences between multivariables, those multivariables must be represented in a way where each adjacent multivariable state only differs by one bit  
> 
> This can be expressed using **gray code**  

| Binary | Gray Code |
|--------|-----------|
| 00     | 00        |
| 01     | 01        |
| 10     | 11        |
| 11     | 10        |

> Another optimisation is to allow the end state and the start state to also differ by one bit—we use gray code with **wraparound** feature to achieve this——which for 2-bit representations does **naturally wraparound**

> [!question] Why Only Compare 2 at Once?  
> - Comparing fewer variables is simply easier  
> - We can break it apart into the smallest comparison units of pairs instead of bigger groups like triplets or quadruplets because it gets a lot harder the more we add  

> [!question] Why Can't We Use Triplets?  
> - We can only group in $2^n$ sizes starting from the edges of the K-map  
> - Any K-map with axes that exceed 2 variables will not have reliable $2^n$ straight-line groupings that don't include the edges  
> - Rectangle groupings are just the straight line groupings combined on both axes—we can't do this reliably either  
> - For wraparound groupings, its maximum generalisable internal grouping is only 2×2, thus won't work either in larger groups  
> - Corner cells, however, will always work  

| K-map Size        | Valid Groupings | Wraparound Validity |
|------------------|------------------|----------------------|
| 2×2               | All 2ⁿ groups    | Fully valid          |
| 2×3 or larger     | Limited          | Only corners or edges|
| 3×3 or larger     | Unreliable       | Internal wraparound fails |

> Only K-maps with at most 2 variables × 2 variables have the nicety where all power-of-2 groups within it—including wraparound—are valid, thus we can freely group in powers of 2 anywhere on the board

---

### 🔁 Looping Rules and Idempotency

> [!info] Karnaugh maps rely on the **Idempotent Law**  
> - Grouping multiple adjacent 1s into a single term is valid because:  
> ```
> A + A = A
> ```

> [!tip] Valid Group Shapes  
> Groupings must be in powers of 2:  
> - 1×2, 2×1 → two adjacent cells  
> - 1×4 → full row  
> - 4×1 → full column  
> - 2×2 → square block  
> - 4×4 → entire map (if all 1s)  
>
> [[🧠 Karnaugh Map Grouping| Why must it be in powers of 2?]]

> [!tip] Wraparound Variants  
> Wraparound allows grouping across edges  
> 
> Special cases include:  
>   - **Four corners** → valid 2×2 block  
>   - **Non-pure-corner wraparound 2×2** → valid only in 4×4 maps  
>   - **Full row/column wraparound** → valid in any map with 4 cells per row/column  

---

### 🧠 Grouping Preference Heuristics

> [!tip] Prefer larger and more balanced groups  
> - Prefer grouping across **both axes** over just one  
> - Prefer **larger groups** over smaller ones  
> - Prefer **fewer groups** with more coverage  

This ensures the final simplified expression has **fewer terms**, each with **fewer literals**, maximizing the power of tautology and idempotency.



---

## 🧩 Don't Cares

> [!note] Strategic Use of Don't Cares  
> If a particular input combination doesn't affect the final output—meaning it's irrelevant to the logic result—we can mark it as a **don't care**  
> 
> These don't cares can be used to **expand existing groups** to larger power-of-2 blocks, allowing more aggressive simplification of the logic relationships 

| Value | Meaning       | Use in Grouping |
|-------|---------------|-----------------|
| 1     | Must be included | Required       |
| 0     | Must be excluded | Required       |
| X     | Don't care     | Optional—used to expand groups |

- Don't cares are not part of the required output, but they can be treated as either 0 or 1 depending on which choice allows for bigger groupings  
- This helps us form larger rectangles in the Karnaugh map, reducing the number of terms in the final simplified expression  
- They act like wildcards that we can strategically absorb into tautology groupings to maximise simplification

[[🎯 Don't Care Conditions — Karnaugh Maps | A little bit more on Don't Cares]]