# Lebanese Chart of Accounts Management System

##  Objective

The project focuses on using a ForestTree structure to simulate and manage a Lebanese Chart of Accounts.

---

##  Language Used

This project is written in **C++**.

---

##  Description

This project uses a custom `ForestTree` class to represent a hierarchy of accounts and subaccounts, modeled after the Lebanese Chart of Accounts. Each account has a unique ID, description, balance, and a list of transactions.

The structure simulates a general tree using a binary tree, where:
- One pointer is used for the **first child**,
- The other is used to link **next siblings**.

---

##  Key Components

### 🔹 Account
- Unique number (1 to 5 digits)
- Description
- Balance
- List of Transactions
- Hierarchically related to parent accounts by most significant digits (e.g., `111` is a child of `11`, which is a child of `1`)

### 🔹 Transaction (Journal Voucher)
- Account number it belongs to
- Positive amount
- `D` or `C` for debit or credit
- Applying a transaction updates:
  - The target account’s balance
  - All its ancestor accounts' balances recursively

---

##  Functionalities

The program includes at least 7 major functionalities:

1. **Initialize an empty forest tree**
2. **Build the chart of accounts** from a provided `.txt` file
3. **Add an account** if it doesn't already exist
4. **Add or delete a transaction** through user interaction
5. **Print detailed account report** into a file:
   - File is named using the account number + the first 10 characters of its description
   - Includes subaccounts, transactions, and balances
6. **Search for an account** by its number
7. **Print the full forest tree** structure into a file

---

##  Files

- `main.cpp` — Main program logic
- `ForestTree.h / ForestTree.cpp` — Tree structure and manipulation
- `Account.h / Account.cpp` — Account class
- `Transaction.h / Transaction.cpp` — Transaction class with overloaded `>>` and `<<` operators
- `accounts.txt` — Input file containing account data
- Output reports — Generated `.txt` files with account details and tree structure

---

##  How to Run

1. Clone or download the repository.
2. Ensure your `accounts.txt` file is present in the root directory.
3. Compile using a C++ compiler:
   ```bash
   g++ main.cpp ForestTree.cpp Account.cpp Transaction.cpp -o chart
   ```

