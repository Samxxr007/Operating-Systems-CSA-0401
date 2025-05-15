#include <stdio.h>
#include <string.h>

#define MAX_PAGES 100
#define MAX_FRAMES 10

int pages[MAX_PAGES];
int frames[MAX_FRAMES];
int used_frames[MAX_FRAMES];

int find_optimal_frame(int current_page) {
    int i, j, max_used = -1, optimal_frame = -1;
    for (i = 0; i < MAX_FRAMES; i++) {
        if (used_frames[i] == -1) {
            return i;
        }
    }

    for (i = 0; i < MAX_FRAMES; i++) {
        int found = 0;
        for (j = current_page; j < MAX_PAGES; j++) {
            if (frames[i] == pages[j]) {
                if (j > max_used) {
                    max_used = j;
                    optimal_frame = i;
                }
                found = 1;
                break;
            }
        }
        if (!found) {
            if (max_used == -1) {
                max_used = 0;
                optimal_frame = i;
            }
        }
    }
    return optimal_frame;
}

int main() {
    int i, j, num_pages, num_frames, page_faults = 0;
    memset(used_frames, -1, sizeof(used_frames));

    printf("Enter number of pages: ");
    scanf("%d", &num_pages);

    printf("Enter page numbers: ");
    for (i = 0; i < num_pages; i++) {
        scanf("%d", &pages[i]);
    }

    printf("Enter number of frames: ");
    scanf("%d", &num_frames);

    for (i = 0; i < num_pages; i++) {
        int found = 0;
        for (j = 0; j < num_frames; j++) {
            if (frames[j] == pages[i]) {
                found = 1;
                break;
            }
        }
        if (!found) {
            int optimal_frame = find_optimal_frame(i);
            frames[optimal_frame] = pages[i];
            used_frames[optimal_frame] = i;
            page_faults++;
        }
    }

    printf("Number of page faults: %d\n", page_faults);

    return 0;
}
