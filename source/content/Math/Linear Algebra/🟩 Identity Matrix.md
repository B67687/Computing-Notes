In math, multiplying by certain values can leave an object unchanged.  
For example, multiplying by **1** keeps a number the same.

We can do this for matrices too — by multiplying with the constant **1**.  
But is there a **matrix equivalent** of multiplying by 1?  
> A matrix that **doesn’t change** the matrix it multiplies?

Let’s call this the **identity matrix**, since it preserves the identity of whatever it multiplies.

---

## 🎯 Initial Idea

Matrix multiplication is read:
> Row-wise from the **left matrix**  
> Column-wise from the **right matrix**

Then we apply a **sum of paired products**.

To preserve the original matrix, we need a way to **select each element** without altering it.

---

## 🧱 Starting Conditions

Since the identity matrix is meant to behave like a constant,  
it’s natural to first place it on the **right side** of the multiplication.

---

## 📐 Shape Compatibility

For matrix multiplication to work,  
> The identity matrix must have the **same number of rows** as the **columns** in the matrix being multiplied.

We start from the top-left corner and select the first element with a **1**.  
We can’t select the others in the same column — they’d interfere with the sum — so we put **0**s.

Then we move to the next row and next column,  
place a **1** there, and **0**s everywhere else in that column.

We keep doing this — selecting one element per row and column —  
and **end up with a diagonal line of 1s from top-left to bottom-right**

> This means the identity matrix must also have the **same number of columns** as the matrix being multiplied so that there are **enough columns to go through all of the elements in each row**

---

## ✅ Summary of Properties

An identity matrix must be:
- A **square matrix** with side length equal to the number of columns of the matrix being multiplied
- **1s on the main diagonal**
- **0s everywhere else**

---

## 🔁 Commutativity Discovery

> [!tip]
> Since the identity matrix is **square** and **symmetric**,  
we can use it on **either side** — left or right.
>
> That means multiplication with the identity matrix is **commutative**.

This is a nice discovery, because it wasn’t obvious at the start —  
we began by using it as the right matrix
