#include<iostream>
#include<math.h>
using namespace std;
class NumberSystem
{
private:
int y[100];
public:
void decimalToBinary(int);
void BinaryToDecimal(int);
};
void NumberSystem::decimalToBinary(int p)
{
int i = 0;
while(p>0) 
{
y[i]=p% 2;
p= p/2;
i++;
}
cout<<"Binary of the given number= ";    
for(i=i-1 ;i>=0;i--)    
{    
cout<<y[i];    
}     
}
void NumberSystem::BinaryToDecimal(int l) 
{
int decimalNumber = 0;
int i=0,r;
while(l!=0) 
{
r=l%10;
l=l/10;
decimalNumber+=r*pow(2,i);
++i;
}
cout<<"The decimal number is = "<<decimalNumber<<endl;
}
int main(void)
{
first:
NumberSystem j,*p;
char ch;
p=&j;
int u,m,q;
cout<<"Press 1: for decimal number convert into binary"<<endl;
cout<<"Press 2: for binary number convert into decimal"<<endl;
cin>>q;
if(q==1)
{
cout<<"Enter a decimal number:";
cin>>u;
p->decimalToBinary(u);
}
else if(q==2)
{
cout<<"Enter a binary number:";
cin>>m;
p->BinaryToDecimal(m);/*object pointer pointed address of the object*/
}
cout<<"\nDo you want to close this program (y/n):";
cin>>ch;
while(true)
{
if(ch=='y' || ch=='Y')
{
break;	
}	
else
{
goto first;
}
}
return 0;
}
