# 📝 Ninja's Training — My Day 1 Experience

- **Difficulty:** Medium
- **Question Link:** [Ninja's Training on TakeUForward](https://takeuforward.org/plus/dsa/problems/ninja's-training?utm=codolio)
- **Topic:** Dynamic Programming (2D DP & Space Optimization)

---

## 🔍 Breaking Down the Problem

We have a ninja who has to train for $N$ days. Every day, they have a choice of 3 activities:
- `0`: Running
- `1`: Stealth training
- `2`: Fighting practice

The main catch is: **the ninja cannot perform the same activity on two consecutive days**. Each activity yields different merit points depending on the day. We need to find the maximum possible merit points the ninja can earn by the end of Day $N$.

### Constraints:
- $1 \le N \le 10^4$
- Each row of the matrix has exactly 3 columns.
- Merit points are positive integers ($0 \le \text{matrix}[i][j] \le 1000$).
- Since $N$ can go up to $10,000$, we need a clean linear time complexity ($O(N)$) to pass the time limits.

---

## 💡 How I Approached the Problem (My Thinking Process)

### Step 1: The Greedy Approach (And why it failed)
My very first thought was simple: *Why not just pick the maximum points possible for today, go to tomorrow, pick the maximum of the remaining two options, and keep going?* 

But as I thought about it, I realized a major flaw: **local choices don't guarantee global optimums**. 
If I choose the maximum points on Day 1, I might block a choice on Day 2 that has a massive payout. In other words, picking the absolute least points on Day 1 could actually be part of the global maximum overall! 

Since my local greedy approach doesn't look ahead and keep track of other possibilities, it won't work here.

---

### Step 2: Formulating a 2D DP State
To solve this, I needed to check all possible combinations without repeating identical subproblems. So I turned to Dynamic Programming.

I defined my state using a 2D DP representation where:
- `dp[i][0]` is the max points up to Day `i` if we perform task `0` (Running) on Day `i`.
- `dp[i][1]` is the max points up to Day `i` if we perform task `1` (Stealth) on Day `i`.
- `dp[i][2]` is the max points up to Day `i` if we perform task `2` (Fighting) on Day `i`.

For the state transition, since we can't repeat the same activity on consecutive days, the max points if we perform task `0` on Day `i` must come from either task `1` or task `2` of Day `i-1`. 

So the formula is:
- `dp[i][0] = max(dp[i-1][1], dp[i-1][2]) + matrix[i][0]`
- `dp[i][1] = max(dp[i-1][0], dp[i-1][2]) + matrix[i][1]`
- `dp[i][2] = max(dp[i-1][0], dp[i-1][1]) + matrix[i][2]`

Finally, the answer is just the maximum value among the three states on the last day: `max(dp[N-1][0], dp[N-1][1], dp[N-1][2])`.
This takes $O(N)$ time and $O(N \times 3)$ space.

---

### Step 3: Space Optimization ($O(N)$ space $\to$ $O(1)$ space)
After getting the 2D DP logic down, I looked at how to optimize it. 

I noticed that to calculate the values for Day `i`, **we only need the values of the previous day (`i-1`)**. We don't need any day's values before that! 

So, I initialized two simple 1D arrays of size 3:
- `prev[3]` to store the previous day's results.
- `current[3]` to compute today's results.

After calculating the values for `current` using `prev`, I just update `prev = current` and move to the next day. This keeps our memory usage constant ($O(1)$ space instead of $O(N)$), which is super clean.

---

## 🛠️ Optimal Code Walkthrough

1. Set up `prev[3]` with Day 0's initial values: `prev[0] = M[0][0]`, `prev[1] = M[0][1]`, `prev[2] = M[0][2]`.
2. Loop through the days from $1$ to $N-1$:
   - `current[0] = max(prev[1], prev[2]) + matrix[i][0]`
   - `current[1] = max(prev[0], prev[2]) + matrix[i][1]`
   - `current[2] = max(prev[0], prev[1]) + matrix[i][2]`
   - `prev = current`
3. Return the maximum element in `prev`.

---

## 🔄 Takeaways & Similar Patterns

- **Similar Problems:**
  - **House Robber (1D DP):** The core constraint is similar (cannot rob adjacent houses). The only difference is in "Ninja's Training" we have 3 choices per step instead of a simple binary choice (rob / don't rob).
- **Key Lessons:**
  - Greedy approaches fail when current choices restrict future choices. That's a huge signpost for DP.
  - Whenever a DP state transitions only using the immediate previous row/state, you can almost always optimize the space from $O(N)$ to $O(1)$ by keeping only a couple of variables or small fixed-size arrays!
