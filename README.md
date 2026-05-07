#include <stdio.h>
#include <string.h>

#define MAX 20


char users[MAX][20];
int graph[MAX][MAX];
int totalUsers = 0;


int getUserIndex(char name[]) {
    for (int i = 0; i < totalUsers; i++) {
        if (strcmp(users[i], name) == 0) {
            return i;
        }
    }
    return -1;
}


void createUser(char name[]) {
    if (getUserIndex(name) != -1) {
        printf("User already exists!\n");
        return;
    }

    strcpy(users[totalUsers], name);

    for (int i = 0; i <= totalUsers; i++) {
        graph[totalUsers][i] = 0;
        graph[i][totalUsers] = 0;
    }

    totalUsers++;
    printf("User %s added successfully.\n", name);
}


void addTransaction(char sender[], char receiver[]) {
    int s = getUserIndex(sender);
    int r = getUserIndex(receiver);

    if (s == -1 || r == -1) {
        printf("Invalid users!\n");
        return;
    }

    graph[s][r] = 1;

    printf("Transaction added: %s -> %s\n", sender, receiver);
}


void displayGraph() {
    printf("\nTransaction Graph:\n\n");

    printf("      ");
    for (int i = 0; i < totalUsers; i++) {
        printf("%8s", users[i]);
    }
    printf("\n");

    for (int i = 0; i < totalUsers; i++) {
        printf("%8s", users[i]);

        for (int j = 0; j < totalUsers; j++) {
            printf("%8d", graph[i][j]);
        }
        printf("\n");
    }
}


void updateTransaction(char sender[], char oldReceiver[], char newReceiver[]) {
    int s = getUserIndex(sender);
    int oldR = getUserIndex(oldReceiver);
    int newR = getUserIndex(newReceiver);

    if (s == -1 || oldR == -1 || newR == -1) {
        printf("Invalid users!\n");
        return;
    }

    if (graph[s][oldR] == 0) {
        printf("Old transaction does not exist!\n");
        return;
    }

    graph[s][oldR] = 0;
    graph[s][newR] = 1;

    printf("Transaction updated successfully.\n");
}


void deleteTransaction(char sender[], char receiver[]) {
    int s = getUserIndex(sender);
    int r = getUserIndex(receiver);

    if (s == -1 || r == -1) {
        printf("Invalid users!\n");
        return;
    }

    if (graph[s][r] == 0) {
        printf("Transaction does not exist!\n");
        return;
    }

    graph[s][r] = 0;

    printf("Transaction deleted successfully.\n");
}

int main() {

    createUser("Alice");
    createUser("Bob");
    createUser("Charlie");
    createUser("David");

    addTransaction("Alice", "Bob");
    addTransaction("Bob", "Charlie");
    addTransaction("Charlie", "David");

    displayGraph();

    updateTransaction("Bob", "Charlie", "David");

    displayGraph();
    
    deleteTransaction("Alice", "Bob");

    displayGraph();

    return 0;
}
