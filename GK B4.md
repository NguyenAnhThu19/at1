#include<iostream>
#include<math.h>
using namespace std;
void selectionSort(int arr[], int n) {
    for (int a = 0; a < n - 1; a++) {
        int min_index = a;
        for (int b = a + 1; b < n; b++) {
            if (arr[b] < arr[min_index]) {
                min_index = b;
            }
        }
        int temp = arr[a];
        arr[a] = arr[min_index];
        arr[min_index] = temp;
    }
}

int main() {
    const int size = 6;
    int arr[size];
    printf("Nhap %d phan tu vao mang: ", size);
    for (int a = 0; a < size; a++) {
        scanf("%d", &arr[a]);
    }
    selectionSort(arr, size);
    printf("Mang da sap xep la: ");
    for (int a = 0; a < size; a++) {
        printf("%d ", arr[a]);
    }
    return 0;
}
