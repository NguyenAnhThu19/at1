#include <iostream>
using namespace std;
#define MAX_SIZE 100

class Queue {
private:
  int arr[MAX_SIZE];
  int front, rear;

public
  Queue() {
    front = rear = -1;
  }

  void enqueue(int x) {
    if (rear == MAX_SIZE - 1) {
      cout << "Hang doi da day." << endl;
      return;
    }

    if (front == -1) {
      front = rear = 0;
    } else {
      rear++;
    }

    arr[rear] = x;
    cout << "Them phan tu: " << x << endl;
  }

  void dequeue() {
    if (front == -1) {
      cout << "Hang doi da rong." << endl;
      return;
    }

    cout << "Lay ra phan tu: " << arr[front] << endl;

    if (front == rear) {
      front = rear = -1;
    } else {
      front++;
    }
  }

  void remove(int x) {
    if (front == -1) {
      cout << "Hang doi da rong." << endl;
      return;
    }

    int index = -1;
    for (int i = front; i <= rear; i++) {
      if (arr[i] == x) {
        index = i;
        break;
      }
    }

    if (index == -1) {
      cout << "Khong tim thay phan tu trong hang doi." << endl;
      return;
    }

    for (int i = index; i < rear; i++) {
      arr[i] = arr[i + 1];
    }

    rear--;

    cout << "Da xoa phan tu: " << x << endl;
  }

  void display() {
    if (front == -1) {
      cout << "Hang doi d? rong." << endl;
      return;
    }

    cout << "Cac phan tu trong hang doi: ";
    for (int i = front; i <= rear; i++) {
      cout << arr[i] << " ";
    }
    cout << endl;
  }
};

int main() {
  Queue q;
  int n;
  cout << "Nhap so luong phan tu: ";
  cin >> n;

  cout << "Nhap cac phan tu: ";
  for (int i = 0; i < n; i++) {
    int x;
    cin >> x;
    q.enqueue(x);
  }

  q.display();
  
  q.enqueue(55);
  q.display();
  
  q.display();

  return 0;
} 
