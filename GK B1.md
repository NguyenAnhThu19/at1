#include <iostream>
using namespace std;
int binarySearch(int arr[], int l, int r, int n) {
    if (r>=l) {
        int mid = 1 + ( r - l ) / 2;
        if (arr[mid] == n) 
            return mid;
        if (arr[mid] > n) 
          return binarySearch(arr, l, mid-l, n);
     return binarySearch (arr, mid+1, r, n);
 }
    return -1;
}
int main() {
    const int size = 5;
    int arr[size];
    cout << "Nhap " << size << " phan tu vao mang: " << endl;
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
    }
    int n = 10;
    int result = binarySearch(arr, 0, size - 1, n);
    if (result == -1)
        cout << "Khong tim thay gia tri " << n << " trong mang.";
    else
        cout << "Tim thay gia tri " << n << " tai chi so " << result << " trong mang.";
    return 0;
