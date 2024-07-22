# lecture-61
#include <iostream>
using namespace std;
class Queue{
    public:
    int queue[1000];
    int max_capacity;
    int front;
    int rear;
    int capacity;
    Queue(){
       this->front = 0;
       this->rear = -1;
       this->max_capacity=1000;
       this->capacity=0;
    }
    void enqueue(int data){
        if(capacity == max_capacity){
            cout<<"Maximum capacity has been reached .";
        }
        rear = (rear+1)%max_capacity;
        queue[rear]=data;
        capacity++;
    }
    void dequeue(){
        if(capacity==0){
            cout<<"THere is no more elements. "<<endl;
        }
        cout<<"The element to be dequeues is "<<queue[front];
        front++;
        capacity--;
        
    }
    void peekqueue(){
        cout<<"The element at the front  is "<<queue[front]<<endl;
    }
    void sizeofqueue(){
        cout<<"The queue currently has "<<capacity<<"elements in it "<<endl;
    }
};
int main(){
    Queue q;
    q.enqueue(5);
    q.enqueue(4);
    q.enqueue(10);
    q.enqueue(15);
    q.enqueue(22);
    q.dequeue();
    q.peekqueue();
    q.dequeue();

    return 0;

}
