# Quick-Update
Wish that u could see my changes
/* Name: Akarsh Singh
   Reg No. : 20212030
   Binary search */
#include<stdio.h>
int binarysearch(int arr[],int value,int low ,int high)
{
  int mid =(low +high)/2;
  if (low>high)
   {
    return -1;
   }
  else if(arr[mid]==value)
   {
     return mid;
   }
  else if(arr[mid]<value)
   {
     low=mid+1;
    return binarysearch(arr,value,low,high);
   }
  else 
   {
    high=mid-1;
    return binarysearch(arr,value,low,high);
   }
  return 0;
}

int main()
{
 int n=0;
 int value;
 
 printf("enter the size of the array:\n");
 scanf("%d",&n);
 int arr[n];
 printf("enter the elements of the array:\n");
 for(int i=0;i<n;i++)
 { 
  scanf("%d",&arr[i]);
 }
 int temp=0;
 for (int i = 0; i < n; i++) 
 {     
        for (int j = i+1; j <n; j++)
         {     
           if(arr[i] > arr[j]) 
           {    
               temp = arr[i];    
               arr[i] = arr[j];    
               arr[j] = temp;
           }
         }
 }              
 printf("the elements of the array are:\n");
 for(int i=0;i<n;i++)
 {
  printf("%d\n",arr[i]);
 }
 printf("enter the element you want to search:");
 scanf("%d",&value);
 int pos=binarysearch(arr,value,0,n);
 if(pos==-1)
 {
  printf("element is not present");
 }
 else
 {
  printf("element is present at position:%d",pos+1);
 }
 return 0;
}  
/*
OUTPUT:
 enter the size of the array:
5
enter the elements of the array:
1 4 7 2 5
the elements of the array are:
1
2
4
5
7
enter the element you want to search:1
element is present at position:1akarsh@akarsh-mint:~$ ./a.out
enter the size of the array:
5 
enter the elements of the array:
2 7 4 6 9
the elements of the array are:
2
4
6
7
9
enter the element you want to search:8
element is not present
*/
