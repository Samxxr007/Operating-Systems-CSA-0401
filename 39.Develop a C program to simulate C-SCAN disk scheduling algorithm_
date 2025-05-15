
#include <stdio.h>

#define MAX_SIZE 200

int main() {
    int queue[MAX_SIZE], head, max, q_size, i, j, seek=0, diff;
    float avg;

    printf("Enter the max range of disk: ");
    scanf("%d", &max);

    printf("Enter the initial head position: ");
    scanf("%d", &head);

    printf("Enter the size of queue: ");
    scanf("%d", &q_size);

    printf("Enter the queue elements: ");
    for(i=0; i<q_size; i++)
        scanf("%d", &queue[i]);

    for(i=0; i<q_size; i++) {
        for(j=i+1; j<q_size; j++) {
            if(queue[i] > queue[j]) {
                int temp = queue[i];
                queue[i] = queue[j];
                queue[j] = temp;
            }
        }
    }

    for(i=0; i<q_size; i++) {
        if(head == queue[i]) {
            diff = i;
            break;
        }
    }

    for(i=diff; i>=0; i--) {
        seek += abs(head - queue[i]);
        head = queue[i];
    }

    seek += max - head;
    head = 0;

    for(i=0; i<diff; i++) {
        seek += abs(head - queue[i]);
        head = queue[i];
    }

    avg = seek/(float)q_size;

    printf("Total seek time: %d\n", seek);
    printf("Average seek time: %f\n", avg);

    return 0;
}
