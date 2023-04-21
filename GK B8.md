#include <iostream>
 #define MAX_SIZE 100

int stack[MAX_SIZE];
int top = -1;

void push(int element) {
    if (top >= MAX_SIZE - 1) {
        printf("Ngan xep day. Khong the them phan tu.\n");
    } else {
        top++;
        stack[top] = element;
    }
}

int pop() {
    int element;
    if (top == -1) {
        printf("Ngan xep rong. Khong the lay phan tu.\n");
        return -1;
    } else {
        element = stack[top];
        top--;
        return element;
    }
}

int peek() {
    if (top == -1) {
        printf("Ngan xep rong. Khong co phan tu nao.\n");
        return -1;
    } else {
        return stack[top];
    }
}

bool isEmpty() {
    if (top == -1) {
        return true;
    } else {
        return false;
    }
}

void printStack() {
    if (isEmpty()) {
        printf("Ngan xep rong. Khong co phan tu nao.\n");
    } else {
        printf("Cac phan tu trong ngan xep la:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    int n;
    printf("Nhap so phan tu cua mang:");
    scanf("%d", &n);
    
    int arr[n];
    printf("Nhap cac phan tu cua mang:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        push(arr[i]);
    }
    
    int topValue = pop();
    printf("Gia tri cua top la: %d\n", topValue);
    
    printStack();
    return 0;
}
