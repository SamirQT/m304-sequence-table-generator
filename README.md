## M304: Sequence Table Generator – Dynamic Width Formatting

**Assignment Overview:**
In this project, you will implement three Python functions—`fib(n)`, `factorial(n)`, and `generate_sequence_table(n)`—that together produce a neatly aligned table of values for `i`, its Fibonacci number, and its factorial, for `i` from 1 to `n`. All column widths must be computed on the fly (no lists or dictionaries), and the entire table is returned as a single multi-line string. This reinforces your skills in loops, arithmetic operations, string formatting, and function composition.

---

**Objectives:**
By completing this assignment, you will:

* Compute the nth Fibonacci number using only loops and arithmetic.
* Compute factorial of n using a loop.
* Determine column widths dynamically by inspecting string lengths in a preliminary pass.
* Build a formatted table string with headers, separators, and right-justified columns.
* Encapsulate all logic into reusable functions without using lists or dictionaries.

> **Note:** You may use multiple functions. **Do not** use lists, dictionaries, or helper methods like `.split()`.

---

**Instructions:**

1. **`fib(n)` Function**

   * Signature:

     ```python
     def fib(n):
         """
         Returns the nth Fibonacci number (1 → 1, 2 → 1, 3 → 2, ...).
         Uses only loops and integer arithmetic.
         """
         # your implementation
     ```

2. **`factorial(n)` Function**

   * Signature:

     ```python
     def factorial(n):
         """
         Returns n! computed via a loop (1! = 1, 2! = 2, ...).
         """
         # your implementation
     ```

3. **`generate_sequence_table(n)` Function**

   * Signature:

     ```python
     def generate_sequence_table(n):
         """
         Generates a formatted table string for i = 1..n:
             i | fib(i) | i!
         with columns right-justified to the widest entry.
         Returns: multi-line string containing header, separator, and each row.
         If n < 1, returns an empty string.
         """
         # your implementation
     ```
   * Within this function:

     * **First pass**: loop i = 1 to n to compute and track:

       * `w_i` = max width of `i` as string
       * `w_fib` = max width of `fib(i)` as string
       * `w_fac` = max width of `factorial(i)` as string
     * **Build header**:

       ```
        { 'i'.rjust(w_i) } | { 'fib(i)'.rjust(w_fib) } | { 'i!'.rjust(w_fac) }
       ```
     * **Build separator**: a line of hyphens matching each column width and separators (`-+-`).
     * **Second pass**: loop i = 1 to n, compute values again, and append each row with right-justified fields and newline.
     * Return the concatenated string (header + newline + separator + newline + rows).

---

**Technical Requirements:**

* **Data Types:** Only integers and strings.
* **Loops:** Use `for` or `while` for all iterations.
* **Conditionals:** Use `if` to handle `n < 1`.
* **Functions:** Exactly three: `fib`, `factorial`, `generate_sequence_table`.
* **String Operations:** Concatenation, slicing, `str().rjust()`—no complex built-ins.

---

**Deliverables:**

* **Python Script:**

  * File name: `M304_seq_table.py`
  * Contains only the three function definitions as specified.

---

**Example of Usage:**

```python
table = generate_sequence_table(5)
print(table)
```

Expected output:

```
 i | fib(i) | i!
---+--------+----
 1 |      1 |  1
 2 |      1 |  2
 3 |      2 |  6
 4 |      3 | 24
 5 |      5 |120
```

---

**Evaluation Criteria:**

* **Correctness (50%)**

  * Accurate Fibonacci and factorial computations.
  * Correct dynamic width calculations.
  * Proper formatting of header, separator, and rows.
* **Code Quality (30%)**

  * Clear, well-commented functions with meaningful names.
* **Edge-Case Handling (20%)**

  * Returns an empty string when `n < 1`.

---

**Tip for Success:**
Perform your width-calculation pass first, storing only integer values and width metrics. Then build the table string in a second pass—this separation keeps your logic clear and bug-free.

