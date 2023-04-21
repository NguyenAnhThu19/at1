#include <stdio.h>

int linearSearch(int arr[], int start, int end, int n) {
    for (int i = start; i <= end; i++) {
        if (arr[i] == n) {
            return i;
        }
    }
    
    return -1;
}

int main() {
    const int size = 5;
    int arr[size];
    printf("Nhap %d phan tu vao mang:\n", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }
    int n = 10;
    int result = linearSearch(arr, 0, size - 1, n);
    if (result == -1)
        printf("Khong tim thay gia tri %d trong mang.", n);
    else
        printf("Tim thay gia tri %d tai chi so %d trong mang.", n, result);
    return 0;
}
