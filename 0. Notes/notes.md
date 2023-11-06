# Equivalent Boolean Expressions

Just like in algebra, we can combine operations in different ways to produce the same outputs. A big part of understanding booleans is being able to identify when expressions are equivalent.

---

## Equivalent Boolean Expressions

How do we determine if boolean expressions are equivalent? The premise is all about checking all possible combinations of boolean input values, which we will use the **truth tables** introduced in Unit 3 Section 5 to do. For example, let's say we want to know if `p` is equivalent to `!p || q`. If we set up a truth table that has both of these expressions as columns, we can compare all the rows to see if they are the same:

| `p` | `q` | `!p` | `!p \|\| q` |
|:---:|:---:|:---:|:---:|
| `true` | `true` | `false` | `true` |
| `true` | `false` | `false` | `true` |
| `false` | `true` | `true` | `true` |
| `false` | `false` | `true` | `true` |

With both `p` and `!p || q` in the truth table, we just compare those columns at every row to see if they match up. In the first and second row, it's looking good and they are both `true`, but the third and fourth rows cause a disagreement. In those rows, `p` is `false`, whereas `!p || q` is `true`. With this mismatch, we can say for certain that `p` and `!p || q` are not equivalent.

Here is another example, comparing `p` and `!(!p)`:

| `p` | `!p` | `!(!p)` |
|:---:|:---:|:---:|
| `true` | `false` | `true` |
| `false` | `true` | `false` |

Using this truth table, we can see that `p` and `!(!p)` must be equivalent boolean expressions, since both rows of the table match up in value!

---

## De Morgan's Laws

Augustus De Morgan (1806 - 1871) was a British Mathematician who introduced a couple of key identities in the fields of propositional logic and **Boolean algebra**. These identities create clear relationships between our **and** and **or** operations using only our other **negation** operation:

- `!(p || q)` is equivalent to `!p && !q`
- `!(p && q)` is equivalent to `!p || !q`

Essentially, the negation of one operation is the negation of the inputs combined with the other operations, an odd, yet satisfying, result.

We can prove these using truth tables:

| `p` | `q` | `p \|\| q` | `!(p \|\| q)` | `!p` | `!q` | `!p && !q`
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `true` | `true` | `true` | `false` | `false` | `false` | `false` |
| `true` | `false` | `true` | `false` | `false` | `true` | `false` |
| `false` | `true` | `true` | `false` | `true` | `false` | `false` |
| `false` | `false` | `false` | `true` | `true` | `true` | `true` |

In this case, the fourth column represents `!(p || q)` and the last column represents `!p && !q`. Comparing them on every row, it is clear they are equivalent, as all the rows are equivalent. Here is the other truth table for the other identity:

| `p` | `q` | `p && q` | `!(p && q)` | `!p` | `!q` | `!p \|\| !q`
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `true` | `true` | `true` | `false` | `false` | `false` | `false` |
| `true` | `false` | `false` | `true` | `false` | `true` | `true` |
| `false` | `true` | `false` | `true` | `true` | `false` | `true` |
| `false` | `false` | `false` | `true` | `true` | `true` | `true` |

In this case, the fourth column represents `!(p && q)` and the last column represents `!p || !q`. Comparing them on every row, it is clear they are equivalent, as all the rows are equivalent.

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `Try.md` and `Try.java` files to try a short assignment using this material.
