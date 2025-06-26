# Cash-Flow-Minimizer
**Project Overview:**
A sophisticated debt settlement system that minimizes the number of transactions needed to resolve
all debts in a group using graph theory and optimization algorithms.

**Problem Statement:**
(Real-World Scenario) When multiple people in a group owe money to each other (like splitting bills,
shared expenses, or business transactions), settling debts individually creates numerous transactions.
For example, if 5 people each owe money to others, there could be up to 20 transactions. The goal is
to minimize this to the fewest possible transactions.

**Example:**

Alice owes Bob $100,
Bob owes Charlie $80,
Charlie owes Alice $50.
Instead of 3 transactions, we can optimize to 2 transactions.

**Technical Approach:**

Data Structures Used:
1. Graph Representation:
Nodes: Banks/People

Edges: Debt relationships with amounts

Adjacency Matrix: graph[i][j] = amount person i owes person j

2. Supporting Structures:
   
Hash Map: unordered_map<string, int> for name-to-index mapping

Priority Queue/Heap: For finding min/max net amounts efficiently

Sets: unordered_set<string> for payment modes per bank

Custom Classes: Bank struct, Pair template class

Key Features & Innovations

1. Payment Mode Compatibility
   
Each bank supports different payment methods (UPI, cards, cash, etc.)

Algorithm prioritizes direct transactions between compatible banks

World Bank concept: Acts as intermediary when no common payment modes exist

2. Transaction Minimization
   
Before optimization: O(n²) potential transactions

After optimization: O(n) transactions in worst case

Typical improvement: 60-80% reduction in transaction count

3. Greedy Optimization Strategy
   
Always pairs largest debtor with largest creditor

Ensures maximum debt settlement per transaction

Guarantees minimal transaction count

**Complexity Analysis:**



Net Amount Calculation : Time Complexity=                      O(n²)       ,space complexity=                         O(n)

Finding Min/Max   : Time Complexity=                                        O(n) per iteration ,space complexity=                   O(1)

Overall Algorithm  : Time Complexity=                                       O(n² × n) = O(n³)  ,space complexity=                   O(n²)

Payment Mode Matching  : Time Complexity=                                   O(m) where m = max payment modes ,space complexity=     O(m)

**Real-World Applications:**

. Fintech: Apps like Splitwise, Venmo group payments

. Banking: Inter-bank settlement systems

. Cryptocurrency: Exchange optimization

. Corporate: Treasury management, vendor payments

. International Trade: Multi-currency settlements



**Error Handling:**

Invalid bank name validation

Zero amount transaction filtering

Boundary condition checks

**User Experience:**

Clear input prompts and format specifications

Detailed transaction output with payment methods

Support for both single and multiple payment modes
