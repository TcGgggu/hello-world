#include<stdio.h>
#define N 20
void Readnum(int num[],int n);
int Getmax(int count[],int n);
int main()
{
    int num[N],count[10],i,m,n,ret;
    printf("Input 20 feedbacks:\n");
    Readnum(num,N);
    for(i=0;i<10;i++)
        count[i]=0;
    for(m=1;m<=10;m++)
    {
        for(n=0;n<20;n++)//数组中等于1—10的数依次读出
        {
            if(num[n]==m)
                count[m-1]++;
        }
    }
    ret=(Getmax(count,10))+1;
    printf("Mode value=%d\n",ret);
    return 0;
}
void Readnum(int num[],int n)
{
    int i;
    for(i=0;i<n;i++)
    {
        scanf("%d",&num[i]);
    }
}
int Getmax(int count[],int n)
{
    int i,max=count[0],k;
    for(i=1;i<n;i++)
    {
        if(count[i]>max)
        {
            max=count[i];
            k=i;
        }
    }
    return k;
}
