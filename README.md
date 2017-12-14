# -TechnicalCPP
Advance C++ Programming
#include <iostream>
using namespace std;
class car
{
private:
char *str;
int len;
public:
car();
car(const char *ch);
car(const car &s);
car &operator =(const car &c);
~car();
};
car::car(){}
car::car(const char *ch)
{
len=strlen(ch);
str=new char[len];
strcpy(str,ch);
}
car::car(const car &s)
{
len=s.len;
str=new char[len];
strcpy(str,s.str);
}
car &car::operator=(const car &c)
{
if(this==&c)
return *this;
delete []str;
if(c.str)
{
str=new char[c.len];
strcpy(str,c.str);
}
else
str=NULL;
return *this;
}
car::~car()
{
cout<<"car destructure"<<endl;
}
int main()
{
car aa;
car bb=aa;
car cc;
aa=cc;
return 0;
}
