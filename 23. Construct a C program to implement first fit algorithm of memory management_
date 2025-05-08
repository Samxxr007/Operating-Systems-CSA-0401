#include <stdio.h>

#define BLOCK_SIZE 100 // size of memory blocks

int main() {
    int memory[BLOCK_SIZE]; // array to represent memory blocks
    int allocation[BLOCK_SIZE]; // array to track allocation status of blocks (0 = free, 1 = allocated)
    int size[BLOCK_SIZE]; // array to store size of free blocks
    int process_size; // size of process to be allocated memory
    int first_fit_block; // block with first fit for process
    int i, j;

    // initialize memory and allocation arrays
    for (i = 0; i < BLOCK_SIZE; i++) {
        memory[i] = 0;
        allocation[i] = 0;
        size[i] = 0;
    }

    // get size of process to be allocated memory
    printf("Enter the size of the process: ");
    scanf("%d", &process_size);

    // find first fit block for process
    first_fit_block = -1;
    for (i = 0; i < BLOCK_SIZE; i++) {
        if (allocation[i] == 0 && size[i] >= process_size) {
            first_fit_block = i;
            break;
        }
    }

    // allocate memory to process
    if (first_fit_block != -1) {
        for (j = 0; j < process_size; j++) {
            memory[first_fit_block + j] = 1;
        }
        allocation[first_fit_block] = 1;
        size[first_fit_block] = process_size;
        printf("Memory allocated to process at block %d\n", first_fit_block);
    } else {
        printf("Error: Not enough memory for process\n");
    }

    return 0;
}
