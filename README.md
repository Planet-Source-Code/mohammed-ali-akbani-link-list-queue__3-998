<div align="center">

## Link list \(queue\)


</div>

### Description

produces a link list as a queue. it is part of my billing project and so uses order placing. nothing complicated.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mohammed Ali Akbani](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mohammed-ali-akbani.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\), Borland C\+\+
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__3-8.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mohammed-ali-akbani-link-list-queue__3-998/archive/master.zip)





### Source Code

```

//	Author:		Mohammed Ali Akbani
//	E-mail:		duke@samwonline.com
//	Level :		beginner
//		Please do not repost it in you name, and vote for me.
#include <iostream.h>
#include <conio.h>
struct order
{
	char	code[7];
	int   qnty;
	order	*next;
};
order *first, *view, *previous, *neworder; //pointers to keep track of the nodes in the list
void new_order( int &order_no )   //adds a new node in the list
{
		if( order_no > 0 )
		{
			neworder = new order;      //if a order already exists in the list
			previous -> next = neworder;  //previous node now points to the new node
			neworder -> next = NULL;    //the new order now points to NULL meaning
			previous = neworder;      //its the last node
			order_no++;
		}
			else
			{
				neworder = new order;
				neworder -> next = NULL;
				previous = first = neworder;
				order_no++;
			}
}
void delete_bill( int &order_no)   // all the nodes are deleted
{
		previous = first;
		for( int j=0; j<order_no; j++ )
		{
			previous = previous -> next;
			delete first;
			first = previous;
		}
}
void main()
{
	int order_no = 0;
	char choice = 'n';
	first = view = previous = neworder = NULL;
	while( choice == 'n' )
	{
		clrscr();     // comment this line if error generated
			new_order( order_no );
			gotoxy(30,9);
			cout << "Enter item code: ";
			cin >> neworder -> code;
			gotoxy(30,11);
			cout << "Enter number of items: ";
			cin >> neworder -> qnty;
			gotoxy(30,13);
			cout << "Enter choice : ";
			choice = getch();
		}
		view = first;
		clrscr();   // comment this line if error generated
		for( int i=0; i<order_no; i++ ) //shows all the orders placed
		{
			gotoxy(30,i+2);
			cout << view -> code;
			gotoxy(40,i+2);
			cout << view -> qnty;
			view = view -> next;
		}
		getch();
		delete_bill( order_no );
}
```

