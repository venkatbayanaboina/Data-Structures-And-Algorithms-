# Data Structures and Algorithms (DSA)

Welcome to my repository for tracking my learning journey, implementations, and problem-solving in Data Structures and Algorithms! 🚀

This repository serves as a personal log of conceptual notes, code implementations, and optimal solutions to classic DSA problems. Inside each folder, you'll find a **Question Checklist** (`README.md`) to tick off questions as you solve them.

---

## 🧠 Intuition & Problem-Solving Framework

One of the main goals of this repository is to train the mind to **identify which data structure or algorithmic paradigm fits a given problem**, formulate a solid intuition, and walk through a systematic thinking process to construct optimal solutions.

### 🔍 1. Topic Identification: Finding the Clues
When reading a new problem, certain patterns and keywords point directly to specific topics:

| Clue / Pattern in Problem | Likely Topic / Data Structure | Why / Explanation |
| :--- | :--- | :--- |
| *Find contiguous subarray/substring, window size* | **Sliding Window** | Tracks a running segment of an array/string dynamically without resetting. |
| *Sorted input, search target, optimize value* | **Binary Search** | Divides search space in half. Often used on non-array answer ranges. |
| *Top K, Largest/Smallest K elements, dynamic median* | **Heap (Priority Queue)** | Provides $O(1)$ access to min/max element in a dynamic stream of data. |
| *Min/Max value, choices depend on subproblems* | **Dynamic Programming (DP)** | Combines overlapping subproblems with optimal substructure properties. |
| *Permutations, combinations, explore all paths* | **Backtracking** | Explores a state tree, reverting choices once they reach a dead end. |
| *Frequency map, fast lookup, duplicate detection* | **Hashing (Unordered Map/Set)** | Provides $O(1)$ average time complexity for checking membership. |
| *Unweighted shortest path, level-order traversal* | **BFS (Breadth-First Search)** | Explores nodes layer-by-layer; guarantees shortest path in unweighted graphs. |
| *LIFO (Last In First Out), nested/matching structures* | **Stack** | Perfect for bracket matching, function calls, or Monotonic Stack problems. |

---

### 💡 2. Developing the Intuition (How to Proceed)
Instead of jumping straight to coding, proceed with these steps:
1. **Analyze Constraints**: Check the input size ($N$).
   - If $N \le 10$, $O(N!)$ or $O(2^N)$ backtracking is acceptable.
   - If $N \le 10^3$, $O(N^2)$ DP or nested loops will pass.
   - If $N \le 10^5$, aim for $O(N \log N)$ or $O(N)$ solutions.
   - If $N \ge 10^8$, look for $O(\log N)$ or $O(1)$ math/binary search.
2. **Start with Brute Force**: Explicitly write down or trace the easiest way to solve the problem (usually nested loops or recursion).
3. **Identify Bottlenecks**: Look at the brute force solution. What is making it slow? Can we store previously computed states (DP/Memoization)? Can we look up elements faster (Hashing)? Can we avoid re-evaluating unchanged items (Sliding Window)?

---

### 📝 3. The 5-Step Thinking Process
1. **Understand**: Clarify edge cases (e.g., negative numbers, empty arrays, duplicate inputs) and trace a sample input manually.
2. **Design**: Sketch the algorithm's high-level flow and write pseudo-code or step-by-step logic.
3. **Analyze**: Evaluate time and space complexity before writing any code.
4. **Implement**: Code the solution clearly, keeping variable names meaningful.
5. **Test**: Dry-run your solution with normal inputs, empty inputs, and large inputs to catch bugs early.

---

## 📁 Repository Structure

Click on any topic to view its curated question checklist and start learning:

- 📂 [arrays](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/arrays) - Arrays, Two Pointers, Sliding Window, Kadane's
- 📂 [strings](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/strings) - String manipulation, anagrams, substring searches
- 📂 [searching_sorting](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/searching_sorting) - Binary Search, Merge Sort, Quick Sort
- 📂 [recursion](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/recursion) - Recursive logic, induction, stack recursion
- 📂 [backtracking](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/backtracking) - Exhaustive search, permutations, N-Queens, Sudoku
- 📂 [linked_lists](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/linked_lists) - Singly/doubly linked lists, cycle detection, reversals
- 📂 [stacks_queues](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/stacks_queues) - LIFO/FIFO operations, Monotonic Stack/Queue
- 📂 [trees](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/trees) - Binary Trees, BST, traversals, LCA
- 📂 [graphs](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/graphs) - DFS, BFS, shortest paths, topological sort
- 📂 [heaps](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/heaps) - Priority Queues, K-way merges, top-K elements
- 📂 [greedy](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/greedy) - Locally optimal choices, scheduling, knapsack
- 📂 [dp](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/dp) - Memoization, tabulation, sequence/grid/knapsack DP
- 📂 [bit_manipulation](file:///Users/nanibayanaboina2750/Documents/study%20files/DSA/bit_manipulation) - Bitwise operators, masking, subset generation

---

## 🛠️ Tech Stack & Tools

- **Language:** C++
- **Version Control:** Git & GitHub

---

## 🚀 How to Run the Files

To compile and run any of the C++ files locally, use a compiler like `g++`:

```bash
g++ -std=c++17 topic/filename.cpp -o filename
./filename
```
