#include <stdio.h>
#include<math.h>
using namespace std;
void quick_sort(int arr[], int L, int R){
    if (L < R){
        int pivot = arr[L];
        int i = L;
        int j = R;
        while (i < j){
            while (arr[i] <= pivot && i < R){
                i++;
            }
            while (arr[j] > pivot){
                j--;
            }
            if (i < j){
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[L];
        arr[L] = arr[j];
        arr[j] = temp;
        quick_sort(arr, L, j-1);
        quick_sort(arr, j+1, R);
    }
}

int main(){
    int n;
    printf("Nhap so phan tu cua mang: ");
    scanf("%d", &n);
    int arr[n];
    for (int i=0; i<n; i++){
        printf("Nhap phan tu thu %d: ", i+1);
        scanf("%d", &arr[i]);
    }
    
    printf("Mang truoc khi sap xep: ");
    for (int i=0; i<n; i++){
        printf("%d ", arr[i]);
    }
    printf("\n");
    quick_sort(arr, 0, n-1);
    printf("Mang sau khi sap xep: ");
    for (int i=0; i<n; i++){
        printf("%d ", arr[i]);
    }
    printf("\n");
    return 0;
}
