#include <bits/stdc++.h>
using namespace std;

struct kabir {
	int data;
	struct kabir* next;
}*head;

int createList(int n)
{
    int i, data;
    struct kabir *prevNode, *newNode;

    if(n >= 1)
    {

        head = new kabir();

        cout<<"Enter data of 1 node: "<<endl;
        cin>>data;

        head->data = data;
        head->next = NULL;

        prevNode = head;


        for(i=2; i<=n; i++)
        {
            newNode =  new kabir();

            cout<<"Enter data of "<<i<<"node: "<<endl;
            cin>>data;

            newNode->data = data;
            newNode->next = NULL;


            prevNode->next = newNode;


            prevNode = newNode;
        }


        prevNode->next = head;

        cout<<"\nCIRCULAR LINKED LIST CREATED SUCCESSFULLY\n";
    }
}

void displayList()
{
    struct kabir *current;
    int n = 1;

    if(head == NULL)
    {
        cout<<"List is empty.\n";
    }
    else
    {
        current = head;
        cout<<"DATA IN THE LIST:\n";

        do {
            printf("Data %d = %d\n", n, current->data);

            current = current->next;
            n++;
        }while(current != head);
    }
}

struct kabir* emptyspace(struct kabir* last, int data)
{

	if (last != NULL)
		return last;

	struct kabir* temp= new kabir();

	temp->data = data;
	last = temp;

	last->next = last;
	return last;
}

struct kabir* addBegin(struct kabir* last, int data)
{
    struct kabir *k=new kabir();
	if (last == NULL)


		return emptyspace(last, data);

	struct kabir* temp= new kabir();
	temp->data = data;
	temp->next = last->next;
	last->next = temp;
	return last;
}

struct kabir* addEnd(struct kabir* last, int data)
{
    struct kabir *l=new kabir();
	if (last == NULL)

		return  emptyspace(last, data);

	struct kabir* temp= new kabir();

	temp->data = data;
	temp->next = last->next;
	last->next = temp;
	last = temp;

	return last;
}

struct kabir* addAfter(struct kabir* last, int data, int item)
{
	if (last == NULL)
		return NULL;

	struct kabir *temp, *p;
	p = last->next;

	do {
		if (p->data == item) {
			temp= new kabir();
			temp->data = data;
			temp->next = p->next;
			p->next = temp;
			if (p == last)
				last = temp;
			return last;
		}
		p = p->next;
	} while (p != last->next);

	cout << item << " not present in the list." << endl;
	return last;
}

int Length(struct kabir* head)
{
	struct kabir* current = head;
	int count = 0;


	if (head == NULL) {
		return 0;
	}


	else {
		do {
			current = current->next;
			count++;
		} while (current != head);
	}
	return count;
}

void DeleteFirst(struct kabir** head)
{
	struct kabir *previous = *head, *next = *head;


	if (*head == NULL) {
		cout<<"\nList is empty\n";
		return;
	}

	if (previous->next == previous) {
		*head = NULL;
		return;
	}


	while (previous->next != *head) {

		previous = previous->next;
		next = previous->next;
	}


	previous->next = next->next;


	*head = previous->next;
	delete(next);

	return;
}


void DeleteLast(struct kabir** head)
{
	struct kabir *current = *head, *temp = *head, *previous;


	if (*head == NULL) {
		cout<<"\nList is empty\n";
		return;
	}


	if (current->next == current) {
		*head = NULL;
		return;
	}


	while (current->next != *head) {
		previous = current;
		current = current->next;
	}

	previous->next = current->next;
	*head = previous->next;
	delete(current);

	return;
}


void DeleteAtPosition(struct kabir** head, int index)
{

	int len = Length(*head);
	int count = 1;
	struct kabir *previous = *head, *next = *head;


	if (*head == NULL) {
		cout<<"\nDelete Last List is empty\n";
		return;
	}


	if (index >= len || index < 0) {
		cout<<"\nIndex is not Found\n";
		return;
	}


	if (index == 0) {
		DeleteFirst(head);
		return;
	}


	while (len > 0) {


		if (index == count) {
			previous->next = next->next;
			free(next);
			return;
		}
		previous = previous->next;
		next = previous->next;
		len--;
		count++;
	}
	return;
}


void traverse(struct kabir* last)
{
	struct kabir* p;


	if (last == NULL) {
		cout << "List is empty." << endl;
		return;
	}


	p =last->next;


	do {
		cout << p->data << " ";
		p = p->next;
	}
	while (p != last->next);
	cout<<endl;
}


int main()
{
	struct kabir* last = NULL;
    int n;
    cout<<"enter the number of nodes "<<endl;
    cin>>n;
	createList(n);
	displayList();


    cout<<"Initial List after insert in empty space: "<<endl;
	last = emptyspace(last, 6);
    traverse(last);
    cout<<"After insert a value at begin"<<endl;
	last = addBegin(last, 4);
	 traverse(last);

	last = addBegin(last, 2);
	 traverse(last);
	  cout<<"After insert a value at last"<<endl;
	last = addEnd(last, 8);
	 traverse(last);
	last = addEnd(last, 5);
	 traverse(last);

	  cout<<"After insert a value at index "<<endl;
	last = addAfter(last, 10, 8);


    traverse(last);


	cout<<"Initial List: "<<endl;
	traverse(last);





	cout<<"\nAfter Deleting first node: "<<endl;
	DeleteFirst(&last);
	traverse(last);



	cout<<"\nAfter Deleting last node: "<<endl;
	DeleteLast(&last);
	traverse(last);

	cout<<"\nAfter Deleting with value : "<<endl;
	DeleteAtPosition(&last, 2);
	traverse(last);

	return 0;
}
