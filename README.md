⛓️ Blockchain Transaction Relationship Graph
📌 Project Title

Blockchain Explorer Transaction Relationship CRUD Graph using C (DSA Project)

👥 Team Members
SANTOSH REDDY
❗ Problem Statement

To develop a blockchain transaction explorer system that models transaction relationships between users using a graph data structure and performs CRUD operations (Create, Read, Update, Delete) through a C program.

🧠 Data Structure Used
Graph (Adjacency Matrix Representation)
Nodes represent blockchain users/accounts
Edges represent transactions between users
2D Array
Used to represent the adjacency matrix
String Arrays
Used to store usernames/accounts
⚙️ Algorithm Explanation
1. Graph Representation
The blockchain transaction network is represented using an adjacency matrix.
Each row and column represent users.
If a transaction exists from one user to another:
Alice → Bob

then:

graph[Alice][Bob] = 1;
2. CRUD Operations
✅ Create
Add new blockchain users
Add transaction relationships between users
✅ Read
Display complete blockchain transaction graph
✅ Update
Modify existing transaction relationships
✅ Delete
Remove transaction relationships from the graph
3. Search Operation
Search for a user in the blockchain network using linear search.
4. Working Principle
Users are added into the blockchain network
Transactions are created between sender and receiver
Graph updates dynamically
Transactions can be updated or deleted
System displays complete transaction relationship graph
▶️ Compilation Instructions
Using GCC Compiler:
gcc main.c -o blockchain
./blockchain
For Windows:
gcc main.c -o blockchain.exe
blockchain.exe
📊 Sample Output
User Alice added successfully.
User Bob added successfully.
User Charlie added successfully.
User David added successfully.

Transaction added: Alice -> Bob
Transaction added: Bob -> Charlie
Transaction added: Charlie -> David

Transaction Graph:

         Alice     Bob Charlie   David
Alice       0       1       0       0
Bob         0       0       1       0
Charlie     0       0       0       1
David       0       0       0       0

Transaction updated successfully.

Transaction Graph:

         Alice     Bob Charlie   David
Alice       0       1       0       0
Bob         0       0       0       1
Charlie     0       0       0       1
David       0       0       0       0

Transaction deleted successfully.

Transaction Graph:

         Alice     Bob Charlie   David
Alice       0       0       0       0
Bob         0       0       0       1
Charlie     0       0       0       1
David       0       0       0       0
🔧 Functions Used
1. getUserIndex()
Finds the index of a user
Returns index position
2. createUser()
Adds a new blockchain user
Prevents duplicate users
3. addTransaction()
Creates transaction relationship between users

Example:

Alice → Bob
4. displayGraph()
Displays adjacency matrix transaction graph
5. updateTransaction()
Updates existing transaction relationships

Example:

Before:

Bob → Charlie

After:

Bob → David
6. deleteTransaction()
Removes transaction relationship from graph
📈 Time Complexity
Operation	Complexity
Search User	O(n)
Add Transaction	O(1)
Update Transaction	O(1)
Delete Transaction	O(1)
Display Graph	O(n²)
🌐 Applications
Blockchain Transaction Explorer
Cryptocurrency Network Analysis
Fraud Detection Systems
Digital Wallet Relationship Mapping
Transaction Monitoring Systems
🚀 Future Enhancements
Weighted Transactions
Transaction Amount Tracking
Hash-based Blockchain Integration
File Handling Support
Dynamic Graph Visualization
GUI-based Blockchain Explorer
Real-time Transaction Monitoring
📚 Learning Outcomes

After completing this project, you will understand:

Graph Data Structures
Adjacency Matrix Representation
CRUD Operations in Graphs
Blockchain Transaction Relationships
Graph Traversal Concepts
Data Management in C
📷 Project Screenshots

Add screenshots of:

User Creation
Adding Transactions
Graph Display
Updating Transactions
Deleting Transactions
Final Output
🎥 Demo Video Link

Add your Google Drive or YouTube video link here.

Example:

https://drive.google.com/your-demo-link
🛠️ Technologies Used
C Programming Language
GCC Compiler
Graph Data Structure
Adjacency Matrix
📄 License

This project is open-source and free to use for educational purposes.

👨‍💻 Author

Santosh Reddy
