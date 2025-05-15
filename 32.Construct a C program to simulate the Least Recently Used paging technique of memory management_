#include <stdio.h>
#include <stdbool.h>

#define FRAME_SIZE 4
#define PAGE_REFERENCE_LENGTH 10

int page_faults = 0;
int page_hits = 0;
int page_frames[FRAME_SIZE];
bool accessed[FRAME_SIZE];

int search_page_frame(int page_number) {
    for (int i = 0; i < FRAME_SIZE; i++) {
        if (page_frames[i] == page_number) {
            return i;
        }
    }
    return -1;
}

void page_replacement(int page_number) {
    int lru = 0;
    for (int i = 1; i < FRAME_SIZE; i++) {
        if (accessed[i] < accessed[lru]) {
            lru = i;
        }
    }
    page_frames[lru] = page_number;
    accessed[lru] = 0;
}

int main() {
    for (int i = 0; i < FRAME_SIZE; i++) {
        page_frames[i] = -1;
    }

    int page_reference[PAGE_REFERENCE_LENGTH] = {1, 2, 3, 4, 2, 1, 5, 6, 2, 1};

    for (int i = 0; i < PAGE_REFERENCE_LENGTH; i++) {
        int page_number = page_reference[i];
        int page_frame_index = search_page_frame(page_number);

        if (page_frame_index == -1) {
            page_faults++;
            if (page_frames[FRAME_SIZE - 1] != -1) {
                page_replacement(page_number);
            } else {
                for (int j = 0; j < FRAME_SIZE; j++) {
                    if (page_frames[j] == -1) {
                        page_frames[j] = page_number;
                        break;
                    }
                }
            }
        } else {
            page_hits++;
        }

        for (int j = 0; j < FRAME_SIZE; j++) {
            if (page_frames[j] != -1) {
                accessed[j]++;
            }
        }
    }

    printf("Page Faults: %d\n", page_faults);
    printf("Page Hits: %d\n", page_hits);

    return 0;
}
