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
