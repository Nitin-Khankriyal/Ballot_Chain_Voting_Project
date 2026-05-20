# Ballot_Chain_Voting_Project
A secure, console-based election management and voting system implemented in C. The project leverages dynamic memory allocation and linear linked lists to authenticate voters, prevent double-voting, and dynamically tally election results.

## Key Features

- **Pre-Registration Access Control:** Allows an administrator to set a fixed pool of eligible voter IDs prior to opening the polls.
- **Strict Input Validation:** Enforces structural integrity by validating that all Student/Employee SAP IDs are exactly 10 digits long.
- **Double-Voting Prevention:** Utilizes a linked list to cross-reference every new ballot against a real-time ledger of IDs that have already voted.
- **Dynamic Ledger Management:** Dynamically allocates memory for each vote cast, ensuring zero wasted memory footprint during operation.
- **Cross-Platform Support:** Features conditional terminal clearing to seamlessly support both Windows and UNIX-based (Linux/macOS) consoles.

---

## Data Structure Design

The core of the system relies on a self-referential structure (`struct node`) to manage the live voting ledger cleanly without hardcoding an upper limit on votes cast:
struct node { 
    long long sap_id; 
    int vote; 
    struct node* link; 
};
