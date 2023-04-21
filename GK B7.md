#include <iostream>
#include<math.h>
using namespace std;

struct Node{
    int key;
    Node* left;
    Node* right;
};

Node* create_node(int key){
    Node* node = new Node;
    node->key = key;
    node->left = NULL;
    node->right = NULL;
    return node;
}

Node* insert(Node* node, int key){
    if (node == NULL){
        return create_node(key);
    }
    if (key < node->key){
        node->left = insert(node->left, key);
    }
    else if (key > node->key){
        node->right = insert(node->right, key);
    }
    return node;
}

void in_order(Node* node){
    if (node != NULL){
        in_order(node->left);
        cout << node->key << " ";
        in_order(node->right);
    }
}

int main(){
    int n;
    cout << "Nhap so phan tu cua mang: ";
    cin >> n;

    int arr[n];
    cout << "Nhap cac phan tu cua mang: ";
    for (int i=0; i<n; i++){
        cin >> arr[i];
    }

    Node* root = NULL;
    for (int i=0; i<n; i++){
        root = insert(root, arr[i]);
    }

    cout << "Mang sau khi sap xep: ";
    in_order(root);
    cout << endl;

    return 0;
}
