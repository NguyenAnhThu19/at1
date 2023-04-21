#include <iostream>
#include <stdio.h>
using namespace std;
void InsertionSort(int a[], int N) {
    int pos, i;
    int x;
    for (int i = 1; i < N; i++) {
        x = a[i];
        pos = i - 1;
        while ((pos >= 0) && (a[pos] > x)) {
            a[pos + 1] = a[pos];
            pos--;
        }
        a[pos + 1] = x;
    }
}
int main() {
    const int size = 6;
    int arr[size];
    printf("Nhap %d phan tu vao mang: ", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }
    InsertionSort(arr, size);
    printf("Mang da sap xep la: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
