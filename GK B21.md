#include <iostream>
#include<math.h>
using namespace std;
int factorial(int n) {
   if (n == 1) { // Dieu kien dung
      return 1;
   } else {
      return n * factorial(n-1); // Cong thuc de quy
   }
}
int main() {
   int n;
   cout << "Nhap vao so nguyen duong n: ";
   cin >> n;
   cout << "T(" << n << ") = " << factorial(n) << endl;
   return 0;
}
