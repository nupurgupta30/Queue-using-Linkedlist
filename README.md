# Queue-using-Linkedlist
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
struct queue
{int data;
struct queue *next;
};
struct queue *front=NULL,*rear=NULL;
void enqueue()
{char ch='y';
printf("-------------------------------------------------------------");
do
{struct queue *newQueue;
newQueue=(struct queue*)malloc(sizeof(struct queue));
newQueue->next = NULL;
printf("\nEnter Data :");
scanf("%d",&newQueue->data);
if(front==NULL)
front = newQueue;
else
rear->next = newQueue;
rear = newQueue;
printf("Done");
printf("\tAdd More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y' || ch=='Y');
}
void dequeue()
{int ch='y';
printf("---------------------------------------------------------------");
do
{struct queue *temp = front;
if(front == NULL && rear==NULL)
{printf("\nQueue UNDERFLOW!!");
break;
}
else if (front->next==NULL)
{printf("\nData Deleted : %d",front->data);
front = NULL;
rear = NULL;
}
else
{printf("\nData Deleted : %d",front->data);
front= front->next;
}
printf("\tDelete More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y'||ch=='Y');
}
void display()
{struct queue *d = front;
printf("------------------------------------------------------------\n");
if(rear==NULL)
printf("Empty Queue");
else
{printf("FRONT->");
while(d!=NULL)
{printf("%d ",d->data);
d=d->next;
}
printf("<-REAR");
}
}
int main()
{int c,size,x=1;
do
{printf("\n------------------------------------------------------------\n");
printf("1.ENQUEUE(Add data) \t2.DEQUEUE(delete data) \t3.Display QUEUE");
printf("\n4.Exit");
printf("\n\t\tEnter Choice :");
scanf("%d",&c);
switch(c)
{case 1: {enqueue(); break; }
case 2: {dequeue(); break; }
case 3: {display(); break; }
case 4: {x=0;break;}
default:{printf("\n\n\t\tError!!!!!"); break;}
}
}
while(x);
return 0;
}
