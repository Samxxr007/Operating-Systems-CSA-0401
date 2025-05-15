#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

void *thread_function(void *arg) {
    int *thread_num = (int *)arg;
    printf("Thread %d: Hello, World!\n", *thread_num);
    pthread_exit(NULL);
}

int main() {
    pthread_t thread1, thread2;
    int thread1_num = 1, thread2_num = 2;
    int comparison;

    if(pthread_create(&thread1, NULL, thread_function, &thread1_num)) {
        printf("Error creating thread 1\n");
        exit(EXIT_FAILURE);
    }

    if(pthread_create(&thread2, NULL, thread_function, &thread2_num)) {
        printf("Error creating thread 2\n");
        exit(EXIT_FAILURE);
    }

    comparison = pthread_equal(thread1, thread2);
    if(comparison == 0) {
        printf("Thread 1 and Thread 2 are different\n");
    } else {
        printf("Thread 1 and Thread 2 are the same\n");
    }
    if(pthread_join(thread1, NULL)) {
        printf("Error joining thread 1\n");
        exit(EXIT_FAILURE);
    }
    
    if(pthread_join(thread2, NULL)) {
        printf("Error joining thread 2\n");
        exit(EXIT_FAILURE);
    }

    printf("Threads have finished.\n");
    exit(EXIT_SUCCESS);
}
