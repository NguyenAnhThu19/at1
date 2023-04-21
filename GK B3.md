#include <stdio.h>
void interchangeSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[i] > arr[j]) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }
}
int main() {
    const int size = 6;
    int arr[size];
    printf("Nhap %d phan tu vao mang: ", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }
    interchangeSort(arr, size);
    printf("Mang da sap xep la: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
