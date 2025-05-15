#include <stdio.h>
#include <stdlib.h>

#define FRAME_SIZE 4
#define PAGE_SIZE 10

int main() {
    int frames[FRAME_SIZE];
    int page_requests[PAGE_SIZE] = {1, 2, 3, 4, 2, 1, 5, 6, 2, 1};
    int page_faults = 0;
    int i, j, k;

    for (i = 0; i < FRAME_SIZE; i++) {
        frames[i] = -1;
    }

    for (i = 0; i < PAGE_SIZE; i++) {
        int page_request = page_requests[i];
        int page_found = 0;

        for (j = 0; j < FRAME_SIZE; j++) {
            if (frames[j] == page_request) {
                page_found = 1;
                break;
            }
        }

        if (!page_found) {
            page_faults++;

            for (j = 0; j < FRAME_SIZE; j++) {
                if (frames[j] == -1) {
                    frames[j] = page_request;
                    break;
                }
            }

            if (j == FRAME_SIZE) {
                for (j = 0; j < FRAME_SIZE - 1; j++) {
                    frames[j] = frames[j + 1];
                }
                frames[FRAME_SIZE - 1] = page_request;
            }
        }
    }

    printf("Number of page faults: %d\n", page_faults);

    return 0;
}
