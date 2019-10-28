#include"iostream"
#include"string"
using namespace std;
struct student
{
	char name[50];
	char num[12];
	int age;
	struct student *next;
};

int main()
{
	struct student *p,*q,*head;
	string  s;
	p=new student;
	q=p;
	head=p;
	cout<<"请输入学生数据："<<endl;
	cout<<"姓名：";
	cin>>p->name;
	cout<<"学号:";
	cin>>p->num;
	cout<<"年龄：";
	cin>>p->age;
	while(cout<<"是否继续添加学生信息 "<<"Y or N? ",cin>>s,s=="Y")
	{
		p=new student;
		cout<<"姓名：";
		cin>>p->name;
		cout<<"学号:";
		cin>>p->num;
		cout<<"年龄：";
		cin>>p->age;
	    if(head==NULL)
	    {
	    	head=p;
	    }
	    else
	    {
	    	q->next=p;
	    }
	    q=p;
	    p->next=NULL;
	}
	p=head;
	while(p!=NULL)
	{
		cout<<p->num<<" "<<p->name<<" "<<p->age<<endl;
		p=p->next;
	}
	return 0;
}
