#include <stdio.h>
#include <stdlib.h>

#define BLOCK_SIZE 1024
#define NUM_BLOCKS 1000

struct file {
    int size;
    int blocks[NUM_BLOCKS];
};

struct file files[100];
int index_block[NUM_BLOCKS];

void init_file_system() {
    int i;
    for (i = 0; i < NUM_BLOCKS; i++) {
        index_block[i] = -1;
    }
}

int allocate_block(int file_index, int block_index) {
    if (index_block[block_index] != -1) {
        printf("Error: block already in use\n");
        return -1;
    }
    index_block[block_index] = file_index;
    files[file_index].blocks[files[file_index].size++] = block_index;
    return 0;
}

int main() {
    init_file_system();
    int file_index = 0;
    int block_index = 0;
    allocate_block(file_index, block_index);
    allocate_block(file_index, block_index + 1);
    allocate_block(file_index, block_index + 2);
    //Simulate file operations
    return 0;
}
