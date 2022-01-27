#include <stdio.h>
#include <time.h> 
#include <unistd.h>
#include <stdlib.h>
 
int main()
{
    int hour, minute, second;
    printf("Enter Hour, Minute and Second\n");
    scanf("%d%d%d",&hour,&minute,&second); 
    if(hour>=24 || minute>=60 || second>=60)
    {
        printf("Error Data\n");
        exit(0);
    }
 
    while(1)
    {
        system("clear");
         
        printf("%02d : %02d : %02d ",hour,minute,second);
         
        fflush(stdout);
         
         second++;
 
        if(second==60)
        {
            minute++;
            second=0;
        }
        if(minute==60)
        {
            hour++;
            minute=0;
        }
        if(hour==24)
        {
            hour=0;
            minute=0;
            second=0;
        }
         
        sleep(1);  
    }
 
    return 0;
}
