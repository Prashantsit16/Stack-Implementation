# Stack-Implementation
Aim:
To study and implement stacks using arrays

Theory:
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle, meaning that the last element added is the first one to be removed.

Basic Operations:
Push: Adds an element to the top of the stack.
Pop: Removes and returns the top element from the stack.
Peek/Top: Returns the top element without removing it.
isEmpty: Checks whether the stack is empty.
isFull: Checks whether the stack is full (in the case of array implementation).
Stack Using Array:
Fixed Size: In the array implementation, the size of the stack is fixed, meaning you must predefine the capacity of the stack.
Index Tracking: The stack keeps track of the top of the stack using an index. Initially, this index is set to -1. Every time an element is pushed, the index is incremented, and every time an element is popped, it is decremented.
Advantages:
Simple Implementation: Stack using an array is straightforward and easy to implement.
Fast Access: Accessing an element (top of the stack) is very efficient because it’s a direct array access.
Disadvantages: *Fixed Size: The maximum size of the stack must be defined in advance, which can lead to inefficiency if the stack grows beyond this size (leading to overflow) or underutilized memory if the stack is too large.
Code:
Algorithm:
Define Class Stack:

Attributes: top (tracks the top of the stack) and ar[] (array to store stack elements).
Initialize top to -1 (empty stack) and ar[0] to 0 in the constructor.
Push Operation:

Check if top is equal to size-1 (i.e., stack is full).
If full, print "STACK OVERFLOW" and exit the function.
If not, increment top and add the element (num) at the new top position in ar[].
Pop Operation:

Check if top is -1 (i.e., stack is empty).
If empty, print "STACK UNDERFLOW" and return ERROR.
If not, store and return the value at top, then decrement top.
Peak Operation:

Check if top is -1 (empty stack).
If empty, print "STACK UNDERFLOW" and return ERROR.
If not, return the element at the top of the stack without modifying top.
Display (disp) Operation:

Check if top is -1 (empty stack).
If empty, print "STACK UNDERFLOW".
If not, traverse the stack from index 0 to top and display all elements.
Main Function:

Create an object of the Stack class.
Push elements (7, 10, and 4) onto the stack.
Pop the top element and display it.
Retrieve and display the top element using peak().
Display all elements in the stack using disp().
Code:
//priti
//103
//stack implementation 
#include<iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Stack{
    int top, ar[size];
    public:
    Stack(){
        top=-1;
        ar[0]=0;
    }
    void push(int);
    int pop();
    int peak();
    void disp();
};
void Stack::push(int num){
    if(top==size-1){
        cout<<"STACK OVERFLOW: Stack is full"<<endl;
        return;
    }
    else{
        ar[++top]=num;
    }
}
int Stack::pop(){
    int val;
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        val=ar[top--];
        return val;
    }
}
int Stack::peak(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return ERROR;
    }
    else{
        return ar[top];
    }
}
void Stack::disp(){
    if(top==-1){
        cout<<"STACK UNDERFLOW: Stack is empty"<<endl;
        return;
    }
    else{
        int i=0;
        while(i!=(top+1)){
            cout<<ar[i]<<"  ";
            i++;
        }

    }
}

int main(){
    Stack s1;
    s1.push(7);
    s1.push(10);
    s1.push(4);
    int val=s1.pop();
    cout<<val;
    int top=s1.peak();
    cout<<top;
    s1.disp();
    return 0;
}
Output:

![Screenshot 2024-10-20 195524](https://github.com/user-attachments/assets/cabaa1b4-67af-47e3-913e-81ec02b8e070)

![Screenshot 2024-10-20 195534](https://github.com/user-attachments/assets/9a5421a7-5e96-46be-a898-d8867ed2a35e)

Conclusion:
We learnt about stacks and it's implementation using array.

