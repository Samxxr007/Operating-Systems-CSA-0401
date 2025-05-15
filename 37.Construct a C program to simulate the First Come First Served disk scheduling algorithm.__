#include <stdio.h>

#define MAX_REQUESTS 100

int requests[MAX_REQUESTS];
int num_requests;
int head;

void input_requests() {
    printf("Enter the number of disk requests: ");
    scanf("%d", &num_requests);

    printf("Enter the requests (in cylinder numbers): ");
    for (int i = 0; i < num_requests; i++) {
        scanf("%d", &requests[i]);
    }

    printf("Enter initial head position: ");
    scanf("%d", &head);
}

void first_come_first_served() {
    int total_seek_time = 0;

    printf("\nOrder of requests: ");
    for (int i = 0; i < num_requests; i++) {
        printf("%d ", requests[i]);
        total_seek_time += abs(requests[i] - head);
        head = requests[i];
    }

    printf("\nTotal seek time: %d\n", total_seek_time);
    printf("Average seek time: %f\n", (float)total_seek_time / num_requests);
}

int main() {
    input_requests();
    first_come_first_served();

    return 0;
}
