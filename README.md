# higher-lower
Its basically a game to expect whether the new no will be greater or lesser than existing no. If you expect it correctly the game will continued, otherwise it will be end and at the last your toatal score will be displayed . 
#include<stdio.h>
#include<time.h>
#include<stdlib.h>
int main()
{
    int no,lower=1,upper=100,t=1,lastno,cnt=0;
    char expt,decision;
    printf("       \n\n\n\n\t\t\t\t\t\t::::::::::::::::: Game  ::::::::::::::::::\n\n\n \t\t\t\t\t\t\t\t\t\t\t\t //  Abbrevations: H/h=greater;L/l=lower;Y/y=Yes;N/n=No;E/e=Equal \n\n");
    srand(time(0));
    lastno=(rand()%(upper-lower+1)) + lower;
    while(t==1)
    {   printf("Last no: %d\n",lastno);
        printf("Enter your expectation:\n");
        scanf("%c",&expt); 
        getchar();
        if(expt!='H' && expt!='h' && expt!='L' && expt!='l' && expt!='E' && expt!='e' )
        {
            printf("Entered wrong value. Again enter\n");
            continue;
        }
        srand(time(0));
        no=(rand()%(upper-lower+1)) + lower;
        if((lastno<no && expt=='H' )  || (lastno<no && expt=='h' ) )
        {
            printf("Correct expectation\n\n");
            cnt++;
        }
        else if((lastno==no && expt=='E' ) || (lastno==no && expt=='e') )
         {
            printf("Correct expectation\n\n");
        }
        else if((lastno>no && expt=='L') ||  (lastno>no && expt=='l'))
        {
            cnt++;
            printf("Correct expectation\n\n");
        }
        else{
            printf("Incorrect expactation\n");
            printf("Your total score is: %d\n",cnt);
            break;
        }
        lastno=no;
       
    }
    return 0;
}
