#include <stdio.h>

void sort_arr(int arr[], int size) {
    int temp,i;
    if (size == 1) {
        return;
    }

    for (int i=0;i<size-1;i++) {
        if (arr[i]>arr[i+1]) {
            int temp = arr[i];
            arr[i] = arr[i + 1];
            arr[i + 1] = temp;
        }
    }

    sort_arr(arr,size-1);
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int size = sizeof(arr) / sizeof(arr[0]);

    printf("Original array:\n");

    for (int i = 0; i <size;i++) {
        printf("%d ", arr[i]);
    }

    sort_arr(arr, size);

    printf("\nSorted array:\n");

    for (int i=0;i<size;i++) {
        printf("%d ", arr[i]);
    }

}
