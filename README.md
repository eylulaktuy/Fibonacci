#include <iostream>
#include <cstring>
using namespace std;
class Fibonacci{
private:
    int *numbers;
    int length;
public:
    Fibonacci(int length){
        Fibonacci::length=length;
        numbers=new int[length];
    }
    Fibonacci(const Fibonacci &obj){
        length=obj.length;
        numbers= new int [length];
        memcpy(numbers,obj.numbers,length*sizeof(int));
    }
    void generate(){
        numbers[0]=1;
        numbers[1]=1;
        for(int i=2;i<length;i++){
            numbers[i]=numbers[i-2]+numbers[i-1];
        }
    }
    void print(){
        for(int i=0;i<length;i++){
            cout<<numbers[i]<<" ";
        }
    }
    ~Fibonacci(){
        delete[] numbers;
    }
};
int main() {
    int length2;
    cout<<"enter length:"<<endl;
    cin>>length2;
    Fibonacci obj(length2);
    obj.generate();
    obj.print();
    return 0;
}

