#include <stdio.h>
#include <stdlib.h>

struct block {
    int data;
    int next;
};

struct file {
    int first;
    int last;
};

struct directory {
    struct file files[10];
};

int main() {
    struct directory dir;
    struct block blocks[100];
    int i;

    // initialize blocks
    for (i = 0; i < 100; i++) {
        blocks[i].data = i;
        blocks[i].next = -1;
    }

    // create file
    int fileIndex = 0;
    dir.files[fileIndex].first = 0;
    dir.files[fileIndex].last = 4;
    for (i = 0; i < 4; i++) {
        blocks[i].next = i + 1;
    }

    // print file
    int currentBlock = dir.files[fileIndex].first;
    while (currentBlock != -1) {
        printf("%d ", blocks[currentBlock].data);
        currentBlock = blocks[currentBlock].next;
    }

    return 0;
}
