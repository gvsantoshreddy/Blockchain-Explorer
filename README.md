# Blockchain-Explorer
#include <stdio.h>
#include <string.h>

#define MAX 10

char graph[MAX][MAX][20];
char nodes[MAX][20];
int size = 0;

// find index
int getIndex(char name[]) {
    for(int i=0;i<size;i++) {
        if(strcmp(nodes[i], name)==0)
            return i;
    }
    return -1;
}

// add node
int addNode(char name[]) {
    int idx = getIndex(name);
    if(idx != -1) return idx;

    strcpy(nodes[size], name);
    return size++;
}

// CREATE
void addTransaction(char tx[], char input[], char outputs[][20], int n) {
    int i = addNode(input);
    int t = addNode(tx);

    strcpy(graph[i][0], tx);

    for(int j=0;j<n;j++) {
        int o = addNode(outputs[j]);
        strcpy(graph[t][j], outputs[j]);
    }
}

// READ
void display() {
    for(int i=0;i<size;i++) {
        printf("%s -> ", nodes[i]);
        for(int j=0;j<MAX && strlen(graph[i][j])>0;j++) {
            printf("%s ", graph[i][j]);
        }
        printf("\n");
    }
}

// MAIN
int main() {

    char out1[][20] = {"B","C"};
    char out2[][20] = {"D"};

    addTransaction("tx1","A",out1,2);
    addTransaction("tx2","B",out2,1);

    display();

    return 0;
}
