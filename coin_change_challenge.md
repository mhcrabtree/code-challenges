# Programming Assignment: Coupon‑Optimized Order Splitting

## Overview
Online retailers often offer multiple coupon codes, each with their own minimum order requirement. However:

- Only **one coupon** may be applied per order.
- Each coupon may be used **at most once**.
- Orders that total **$99 or more receive free shipping**.
- Your goal is to **maximize total savings** by splitting a shopping cart into multiple orders.

This assignment asks you to design an algorithm that automatically splits a shopping cart into multiple orders to achieve the greatest possible discount.

---

## Problem Description

You are given:

### 1. A list of items, each with:
- A name  
- A price  

Example items:

| Item | Price |
|------|-------|
| Hobbywing XR10 ESC | 119.99 |
| Hobbywing V10 Motor | 149.99 |
| RC10T7 Stadium Truck Kit | 429.99 |
| Shock Oil 25wt | 9.99 |
| Shock Oil 27.5wt | 9.99 |
| Rear Wheels | 8.99 |
| Front Wheels | 8.99 |
| Rear Tires | 21.75 |
| Front Tires | 21.75 |
| Reedy LiPo Battery | 80.99 |

### 2. A list of coupon codes, each with:
- A minimum order amount  
- A discount amount  
- A unique coupon code (cannot be reused)

Example coupons:

| Coupon Code | Minimum Order | Discount |
|-------------|----------------|----------|
| MAR1026 | 100 | 10 |
| MAR1526 | 125 | 15 |
| MAR3026 | 350 | 30 |
| MAR526 | 50 | 5 |
| MINISLASH | 439.90 | 40 |

### 3. Free Shipping Rule
Any order with a total **before discounts** of **$99 or more** receives free shipping.  
Orders under $99 incur a shipping cost (you may assume a fixed cost, e.g., $10).

---

## Your Task

Write an algorithm that:

1. **Takes the full shopping cart and the list of coupons as input.**
2. **Splits the items into one or more orders.**
3. **Assigns at most one coupon to each order.**
4. **Ensures no coupon is used more than once.**
5. **Ensures each item appears in exactly one order.**
6. **Maximizes total savings**, where savings =  
   - Sum of coupon discounts  
   - Minus any shipping fees for orders under $99

Your algorithm should output:

- The list of orders  
- The items in each order  
- The coupon applied (if any)  
- The subtotal, discount, shipping cost, and final total for each order  
- The total savings across all orders  

---

## Requirements

### 1. Algorithm Design
You must:

- Describe your algorithm in clear English or pseudocode.
- Explain why you believe it produces a good (or optimal) solution.
- Discuss any limitations or assumptions.

### 2. Implementation
You may implement your algorithm in any programming language you choose.

Your program must:

- Read the list of items and coupons.
- Produce the optimized set of orders.
- Print a clear summary of the results.

### 3. Complexity Discussion
In 3–5 sentences, explain:

- Whether your algorithm is greedy, brute‑force, dynamic programming, or hybrid.
- The time complexity in Big‑O notation.
- Why you chose this approach for this assignment.

---

## Hints (Optional for Students)

- This problem is similar to the **coin change problem**, but with two twists:
  - You can only use each “coin” (coupon) once.
  - Items must be grouped into “buckets” (orders) that meet coupon thresholds.
- A greedy approach may work well, but it is **not guaranteed optimal**.
- A dynamic programming or search‑based approach may find better solutions.
- Think carefully about the **free shipping threshold**—sometimes adding a small item to reach $99 saves more than the coupon itself.

---

## Example Output Format (Simplified)

```
Order 1:
Items: [RC10T7 Truck, Motor]
Subtotal: $579.98
Coupon: MAR3026 (-$30)
Shipping: $0
Final Total: $549.98

Order 2:
Items: [ESC, Battery]
Subtotal: $200.98
Coupon: MAR1526 (-$15)
Shipping: $0
Final Total: $185.98

Order 3:
Items: [Shock Oil 25wt, Shock Oil 27.5wt, Wheels, Tires…]
Subtotal: $71.47
Coupon: None
Shipping: $10
Final Total: $81.47

Total Savings: $45 (coupons) - $10 (shipping) = $35
```

