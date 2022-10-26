
## Solution c++
```c++
 #include<bits/stdc++.h>
#define max_size 20
#include<windows.h>
using namespace std;
char Games[3][3]={'-','-','-','-','-','-','-','-','-'};/* matrix 3 x 3 */
/*stack class*/
class stac {
private:
int items[max_size];
int top;
public:
     stac () { top = -1; }

	void push(int element);
	int pop();
	bool is_empty();
	bool is_full();
	int peek() { return items[top]; }/*return top of stack */
	void print_all_elements();
};
/* Push Function*/
void stac::push(int element) {
if (is_full())
{
	cout << "Stack is overflow";
	return;
} top++;
items[top] = element;
}
/*Pop Function*/
int stac::pop()
{
if (is_empty())
{
	cout << "Stack is underflow";
	return -1;
}
int element= items[top];
top--;
return element;
}
/* Is_empty Function*/
bool stac::is_empty() {
	if (top == -1) return true;
	return false;
}
/*Is_full Function*/
bool stac::is_full() {
if (top == max_size - 1) return 1;
return 0; }
/*print element */
void stac::print_all_elements()
{
	for (int i = 0; i < top - 1; i++)
		cout << items[i] << " ";
}

/*-------------------------------------------------------------------------------------------------------------------------------------*/
void Drow()
{
	system("cls");

	for (int row = 0; row < 3; row++)
	{
		cout << "| ";
		for (int colum = 0; colum < 3; colum++)
		{
			if (Games[row][colum] == 'X' || Games[row][colum] == 'O')
			{
				cout << Games[row][colum] << " | ";
			}
			else
			{
				cout << "-" << " | ";
			}

		}
		cout << endl;
	}

}
 /*-------------------------------------------------------------------------------------------------------------------------------------*/
 void Reblace(char N)
 {

   int position;
   cout<<N<< "please enter row and col to put ( "<<N<<"):"<<endl;
    cin>>position;
    for(int row=0;row<3;row++)
        {
          for(int colum=0;colum<3;colum++)
            {
                if(Games[row][colum]==position)
                {
                   Games[row][colum]=N;
                }
            }
            if(N=='x')
            {
                N='o';
            }
            else
                {
                    N='x';
                }
        }
 }
 /*-----------------------------------------------------------------------------------------------------------------------------------*/
 char check() /* check who is winner */
 {
     int x=0,o=0,counter=0;
      for(int row=0;row<3;row++)
        {
          for(int colum=0;colum<3;colum++)
            {
                /*check in rows*/
                if  (Games[row][colum]='x')
                {
                    x++;
                }
                else if (Games[row][colum]='o')
                {
                    o++;
                }
                if(x==3)
                {
                    return 'x';
                }
                  if(x==3)
                {
                    return 'o' ;
                }
            }
         x=0,o=0;
        }
        //-----------------------------------------------------------------------------------------------------------------------------
       for(int colum=0;colum<3;colum++)
        {
          for(int row=0;row<3;row++)
            {
                /*check in colums*/
                if  (Games[row][colum]='x')
                {
                    x++;
                }
                else if (Games[row][colum]='o')
                {
                    o++;
                }
                if(x==3)
                {
                    return 'x';
                }
                  if(x==3)
                {
                    return 'o' ;
                }
            }
         x=0,o=0;
        }
        //   check the main Diagonal
        if(Games[0][0]=='x' && Games[1][1]=='x' && Games[2][2]=='x')
        {
            return 'x';
        }
        if(Games[0][0]=='o' && Games[1][1]=='o' && Games[2][2]=='o')
        {
            return 'o';
        }
        //check the another Diagonal

        if(Games[0][2]=='x' && Games[1][1]=='x' && Games[2][0]=='x')
        {
            return 'x';
        }
        if(Games[0][2]=='o' && Games[1][1]=='o' && Games[2][0]=='o')
        {
            return 'o';
        }
        /*----------------------------------------------------------------------*/
      /* no winer*/

         for(int row=0;row<3;row++)
        {
          for(int colum=0;colum<3;colum++)
            {
                if(Games[row][colum]!='x' && Games[row][colum]!='o' )
                {
                   counter++;
                }
            }
        }
        if(counter==0)
        {
            return'=';
        }
      return'*';
}
 /*------------------------------------------------------------------------------------------------------------------------------------*/
int main(){
string name1,name2;
int start,choice;
stac n1,n2;
/*----------------------------------------------------------------------------------------*/
cout<<"Enter name the first  player :"<<endl;
cin>>name1;
cout<<"Enter name the first  player"<<endl;
cin>>name2;
cout<<"player one "<<name1<<" will play with 'o' character and player two "
<<name2<<"  will play with 'x'character " <<endl;
cout<<"Which player will start 1( "<<name1<< "  ) 2 ( "<<name2<<" ) : ";
 cin>>start;
 /*--------------------if first name  is start--------------------------------------------*/
  char N ='o';
 if(start==1)
 {
    char N ='o';
          Drow();
  cout<<name1<<"  turn"<<endl;
  cout<<name1 <<"  please enter   1- cell position   2- undo  3- redo :"<<endl;
  cin>>choice;
  if(choice==1)
  {
    Reblace(N);
     Drow();
     check();

     if(check()=='o')
     {
         cout<<"the player "<<name1<<" is winner"<<endl;
     }
      if(check()=='x')
     {
         cout<<"the player "<<name2<<" is winner"<<endl;
     }
      if(check()=='=')
     {
         cout<<"  No winner"<<endl;
     }

  }
  else if (choice==2)
  {

  }
   else if (choice==3)
  {

  }
  else
  {
      cout<<"Invalid input "<<endl;

  }
 }
 /*------------------------------if name two is start-----------------------------*/
 else if(start==2)
  {
       char N='x';
        Drow();
    cout<<name2<<"  turn"<<endl;
    cout<<name2 <<"  please enter   1- cell position   2- undo  3- redo :"<<endl;
    cin>>choice;
  if(choice==1)
  {
while(check()=='*')
{
     Reblace(N);
     Drow();
     check();
}
     if(check()=='o')
     {
         cout<<"the player "<<name1<<" is winner"<<endl;
     }
      if(check()=='x')
     {
         cout<<"the player "<<name2<<" is winner"<<endl;
     }
      if(check()=='=')
     {
         cout<<"  No winner"<<endl;
     }
  }
  else if (choice==2)
  {

  }
   else if (choice==3)
  {

  }

  }
else
{
    cout<<"Invalid input "<<endl;
}

return 0;
}

	
```

