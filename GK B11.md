#include <iostream>
using namespace std;
int countPositive(int arr[], int n)
{
    if (n <= 0)
        return 0;
    int count = countPositive(arr, n-1);
    if (arr[n-1] > 0)
        count++;
    return count;
}
int main() {
    int arr[] = size;
    int n = sizeof(arr)/sizeof(arr[0]);
    int count = countPositive(arr, n);
    cout << "So luong gia tri duong trong mang la: " << count;
    return 0;
}
*OR
#include<stdio.h>
#include<math.h>
#define MAX 100
void nhap (float a[], int &n)
{
    do
    {
        printf("Nhap so phan tu: ");
        scanf("%d", &n);
        if(n <= 0 || n > MAX)
        {
            printf("\nSo phan tu khong hop le. Xin kiem tra lai !");
        }
    }while(n <= 0 || n > MAX);
    for(int i = 0; i < n; i++)
    {
        printf("\nNhap a[%d]: ", i);
        scanf("%f", &a[i]);
    }
}
void xuat(float a[], int n)
{
    for(int i = 0; i < n; i++)
    {
        printf("%8.3f", a[i]);
    }
}
int demDuong(float a[], int n)
{
    if(n == 0)
        return 0;
    if(a[n - 1] > 0)
        return 1 + demDuong(a, n - 1);
    return demDuong(a, n - 1);
}
int main()
{
    int n;
    float a[MAX];
    nhap(a, n);
    xuat(a, n);
    int dem = demDuong(a, n);
    printf("\nCo %d so duong ", dem);
    return 0;
}
