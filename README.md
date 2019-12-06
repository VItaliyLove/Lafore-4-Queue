# Lafore-4-Queue

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.nio.Buffer;

class Algorithm {

    static class Queue {

        private int[] arr;
        private int front;
        private int rear;
        private int maxSize;
        private int nElems;

        public Queue(int max) {
            maxSize = max;
            front = 0;
            rear = 0;
            arr = new int[maxSize];
            nElems = 0;
        }

        public void push(int number) {
            if (isFull())
                System.out.println("The queue is full");
            else {
                arr[rear] = number;
                rear++;
                if (rear == maxSize)
                    rear = 0;
                nElems++;
            }
        }

        public int pop() {
            if (isEmpty())
                System.out.println("The queue is empty");
            else {
                int temp = arr[front];
                front++;
                if (front == maxSize)
                    front = 0;
                nElems--;
                return temp;
            }
            return -1;
        }

        public boolean isFull() {
            return (nElems == maxSize);
        }

        public boolean isEmpty() {
            return (nElems == 0);
        }

        public void display() {
            for (int x : arr) {
                System.out.print(x);
            }
            System.out.println();
        }
    }

    public static void main(String[] arg) throws IOException {

        Queue myQ = new Queue(5);
        myQ.push(3);
        myQ.push(2);
        myQ.push(1);
        myQ.display();
        System.out.println(myQ.pop());
        System.out.println(myQ.pop());
        System.out.println(myQ.pop());
        System.out.println(myQ.pop());
    }

}
