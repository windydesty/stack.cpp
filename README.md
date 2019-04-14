#include<iostream>
#include<process.h>
 
using namespace std;
 
struct Node
{
	int data;
	Node *next;
}*atas=NULL,*p;
 
Node* nodebaru(int x)
{
	p=new Node;
	p->data=x;
	p->next=NULL;
	return(p);
}
 
void push(Node *q)
{
	if(atas==NULL)
	atas=q;
	else
	{
	q->next=atas;
	atas=q;
	}
}
 
void pop(){
	if(atas==NULL){
	cout<<"Stack kosong!!";
	}
	else{
	cout<<"Hapus Elemen"<<atas->data;
	p=atas;
	atas=atas->next;
	delete(p);
	}
}
 
void showstack()
{
	Node *q;
	q=atas;
 
	if(atas==NULL){
	cout<<"Stack kosong!!";
	}
	else{
	while(q!=NULL)
	{
	cout<<q->data<<" ";
	q=q->next;
	}	
	}
}
 
int main()
{
	int ch,x;
	Node *nptr;
	
	while(1)
	{
	cout<<"\n\n1.Push\n2.Pop\n3.Display\n4.Exit";
	cout<<"\nmasukan pilihan anda(1-4):";
	cin>>ch;
	
	switch(ch){
	case 1: cout<<"\nmasukan data:";
	cin>>x;
	nptr=nodebaru(x);
	push(nptr);
	break;
	
	case 2: pop();
	break;
	
	case 3: showstack();
	break;
	
	case 4: exit(0);
	
	default: cout<<"\npilihan tidak tersedia!!";
	}
	}while (ch!= 4);
	
	
	return 0;
}
