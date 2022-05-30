# sort-0-1-2-of-a-linkedlist
#include<bits/stdc++.h>
using namespace std;
struct Node
{
    int data;
    Node *next;
    Node(int x)
    {
        this->data=x;
        this->next=NULL;
    }
};
Node* sort_0_1_2(Node *head)
{
   Node *curr=head;
   int count_zero=0;
   int count_one=0;
   int count_two=0;
   while(curr!=NULL)
   {
       if(curr->data==0)
       {
           count_zero++;
       }
       else if(curr->data==1)
       {
           count_one++;
       }
       else if(curr->data==2)
       {
           count_two++;
       }
       curr=curr->next;
   }
  // curr=head;
  curr=head;
   while(curr!=NULL)
   {
       if(count_zero!=0)
       {
          curr->data=0;
           count_zero--;
       }
       else if(count_one!=0)
       {
           curr->data=1;
           count_one--;
       }
       else if(count_two!=0)
       {
           curr->data=2;
           count_two--;
       }
       curr=curr->next;
   }
   return head;
}
int main()
{
    Node *head=new Node(2);
    head->next=new Node(0);
    head->next->next=new Node(1);
    head->next->next->next=new Node(2);
    head->next->next->next->next=new Node(0);
    head->next->next->next->next->next=new Node(1); 
    head->next->next->next->next->next->next=new Node(0);
    head->next->next->next->next->next->next->next=new Node(2);
    sort_0_1_2(head);
    for(Node *curr=head;curr!=NULL;curr=curr->next)
    {
    cout<<curr->data<<" ";
    }
       return 0;
}
