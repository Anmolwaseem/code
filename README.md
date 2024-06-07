# code
code of virtual function
include<iostream>
using namespace std;
class course{
    public:
    string coursetitle;
    int coursefee;
    int courseduration;
course(string ct ,int cf,int cd){
    coursetitle= ct;
    coursefee=cf;
    courseduration=cd;
}
 virtual void display(){
    cout<<"the course title:"<<coursetitle<<endl;
    cout<<"the course fee:"<<coursefee<<endl;
    cout<<"the course duration:"<<courseduration<<endl;
}
};
class onnlineclass:public course{
    public:
    int videolength;
    onnlineclass(string ct, int cf, int cd,int vd):course(ct,cf,cd){
        videolength=vd;
    }
void display(){
    display();
    cout<<"course discription:"<<videolength<<endl;
}
    };
class offline:public course{
  public:
   int numofclass;
   offline(string ct, int cf, int cd, int nc) : course(ct, cf, cd){
      numofclass=nc;
   }
   void display(){
     display();
     cout<<"the num of clases are:"<<numofclass<<endl;
   }
};

int main()
{
    course* courses[2];
   courses[0]=online("oop",2300,233,20);
 courses[1]= off("oop",3333,222,89,21);
   for (int i = 0; i < courses; i++)
   {
    courses[i]->display()<<endl;
   }
  
return 0;
}
