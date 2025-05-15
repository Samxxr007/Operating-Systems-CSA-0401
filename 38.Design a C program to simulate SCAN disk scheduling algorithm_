#include <stdio.h>

#define MAX_REQUESTS 25
#define MAX_CYLINDERS 200

int requests[MAX_REQUESTS];
int request_count;
int head;
int total_movement = 0;

void scan(int start) {
    int i, j;
    printf("\nServicing requests in SCAN order: ");
    if (start < requests[0]) {
        for (i = start; i >= 0; i--) {
            printf("%d ", i);
            total_movement += abs(i - head);
            head = i;
        }
    } else if (start > requests[request_count - 1]) {
        for (i = start; i < MAX_CYLINDERS; i++) {
            printf("%d ", i);
            total_movement += abs(i - head);
            head = i;
        }
    } else {
        for (i = 0; i < request_count; i++) {
            if (requests[i] > start) {
                for (j = i; j >= 0; j--) {
                    printf("%d ", requests[j]);
                    total_movement += abs(requests[j] - head);
                    head = requests[j];
                }
                break;
            }
        }
        for (i = request_count - 1; i >= j; i--) {
            printf("%d ", requests[i]);
            total_movement += abs(requests[i] - head);
            head = requests[i];
        }
    }
}

int main() {
    int i, start;
    printf("Enter the number of disk requests: ");
    scanf("%d", &request_count);
    printf("Enter the requests: ");
    for (i = 0; i < request_count; i++) {
        scanf("%d", &requests[i]);
    }
    printf("Enter the initial head position: ");
    scanf("%d", &start);
    head = start;
    scan(start);
    printf("\nTotal head movement: %d\n", total_movement);
    return 0;
}
