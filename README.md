# DSA-Lab-1
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <unistd.h>

void sequential_search(int array[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (array[i] == target) {
            printf("Element %d found at index %d", target, i);
            return;
        }
    }
    printf("Element not found\n");
}

int main() {
    const int size = 5;
    int numbers[size];
    int target;
    srand(time(NULL));

    clock_t clock_start = clock();
    time_t time_start = time(NULL);

    printf("Generated Array:\n");
    for (int i = 0; i < size; i++) {
        numbers[i] = rand() % 1000 + 1;
        printf("[%d] = %d\n", i, numbers[i]);
    }

    target = numbers[rand() % size];
    printf("\nSearching for: %d\n", target);

    sequential_search(numbers, size, target);

    clock_t clock_end = clock();
    time_t time_end = time(NULL);

    double cpu_time = ((double)(clock_end - clock_start)) / CLOCKS_PER_SEC;
    double wall_time = difftime(time_end, time_start);
    
    printf("\nTiming Information:\n");
    printf("Start Time: %s", ctime(&time_start));
    printf("End Time: %s", ctime(&time_end));
    printf("CPU Time: %.6f seconds\n", cpu_time);
    printf("Real Time: %.2f seconds\n", Real_time);

    return 0;
}
