#include <stdio.h>
#include <stdlib.h>

int main() {
    int n1, n2;

    // Read the initial size of the array
    printf("Enter the size of the array (n1): ");
    scanf("%d", &n1);

    // Allocate memory for the array
    int *arr = (int *)malloc(n1 * sizeof(int));

    // Read values for the initial array from the keyboard
    printf("Enter %d values for the initial array:\n", n1);
    for (int i = 0; i < n1; i++) {
        scanf("%d", &arr[i]);
    }

    // Read the new size (n2) and expand the array
    printf("Enter the additional size of the array (n2): ");
    scanf("%d", &n2);

    // Reallocate memory for the expanded array
    arr = (int *)realloc(arr, (n1 + n2) * sizeof(int));

    // Read values for the expanded part of the array
    printf("Enter %d values for the expanded array:\n", n2);
    for (int i = n1; i < n1 + n2; i++) {
        scanf("%d", &arr[i]);
    }

    // Print the state of the array with (n1 + n2) values
    printf("Array with %d values:\n", n1 + n2);
    for (int i = 0; i < n1 + n2; i++) {
        printf("%d ", arr[i]);
    }

    // Free the allocated memory
    free(arr);

    return 0;
}

