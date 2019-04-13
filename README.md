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
