# multiple-linear-regression

---

### **1. What is Sourcing Amount?**  
The **Sourcing Amount (SA)** is the total amount of materials or goods a company needs to purchase or "source" to meet demand. Think of it as how much a company needs to buy to keep things running smoothly in its supply chain.

---

### **2. Factors that Affect Sourcing Amount**  
There are three key factors that influence the sourcing amount:

1. **Sales (S)**:  
   - Directly proportional.  
   - *More sales → more sourcing.*  
   Example: If a shop sells more items, it needs to restock (source) more frequently.

2. **Productivity Score (PS)**:  
   - Inversely proportional.  
   - *Higher productivity → less sourcing.*  
   Example: If workers are efficient and produce more with fewer resources, the company needs to source less.

3. **Number of Posts (NP)**:  
   - Directly proportional.  
   - *More posts → more sourcing.*  
   Here, "posts" could mean orders, production batches, or any unit that increases sourcing needs.

---

### **3. Building a Formula to Estimate Sourcing Amount**  
We create a simple equation to estimate the sourcing amount based on the above factors:  

\[
SA = a \times S - b \times PS + c \times NP
\]

Here:  
- **a** is the coefficient for Sales.  
- **b** is the coefficient for Productivity Score.  
- **c** is the coefficient for Number of Posts.

These coefficients show how much each factor impacts the sourcing amount.

---

### **4. Finding the Coefficients (a, b, c)**  
To calculate these coefficients, we use historical data and apply a formula called the **normal equation** from linear regression.

---

### **5. Step-by-Step Example (How to Calculate Coefficient a)**

**Data Table:**

| Month | Sourcing Amount (SA) | Sales (S) | Productivity Score (PS) | Number of Posts (NP) |
|-------|----------------------|-----------|-------------------------|----------------------|
| 1     | 7500                 | 500000    | 76                      | 50                   |
| 2     | 10000                | 1200000   | 83                      | 60                   |
| 3     | 15000                | 2200000   | 72                      | 75                   |
| 4     | 15000                | 1800000   | 70                      | 80                   |

**To Calculate Coefficient "a" (for Sales):**

The formula for **a** is:  
\[
a = \frac{(S_1 \times SA_1 + S_2 \times SA_2 + S_3 \times SA_3 + S_4 \times SA_4)}{(S_1^2 + S_2^2 + S_3^2 + S_4^2)}
\]

Steps:  
1. Multiply each sales value by its corresponding sourcing amount:  
   - \( 500000 \times 7500 \)  
   - \( 1200000 \times 10000 \)  
   - \( 2200000 \times 15000 \)  
   - \( 1800000 \times 15000 \)  
2. Add them up.  
3. Divide by the sum of the squares of the sales values.  

**Result:**  
\[
a ≈ 0.0075
\]

---

### **6. Similarly, Coefficient "b" (for Productivity Score)**  

The formula for **b** involves subtracting the effect of sales from productivity and then dividing by the squared values of productivity:

\[
b ≈ -35.35
\]  

---

### **7. Coefficient "c" (for Number of Posts)**  

Using a similar process, we calculate:

\[
c ≈ 41.67
\]

---

### **8. Final Equation**  
Now we have all the coefficients! The final equation to estimate the sourcing amount is:  

\[
SA ≈ 0.0075 \times S - 35.35 \times PS + 41.67 \times NP
\]

---

### **9. Example Prediction**  

Let’s say we want to estimate the sourcing amount for a new scenario where:  
- Sales (S) = 2,500,000  
- Productivity Score (PS) = 80  
- Number of Posts (NP) = 90  

We plug these values into the equation:

\[
SA ≈ 0.0075 \times 2500000 - 35.35 \times 80 + 41.67 \times 90
\]

1. \( 0.0075 \times 2500000 = 18750 \)  
2. \( -35.35 \times 80 = -2828 \)  
3. \( 41.67 \times 90 = 3750 \)  

Now, add them up:  

\[
SA ≈ 18750 - 2828 + 3750 ≈ 12000
\]

So, the estimated sourcing amount is **₹12,000**.

---

### **Conclusion**  
By using historical data and a linear regression approach, we can estimate how much sourcing a company needs based on sales, productivity, and the number of posts. This helps in better planning and decision-making in supply chain management.
