# Highest-Sum-Square-Matrix
Consider a 2D matrix of numbers from 0 to 9 with variable width and height. Find the square sub-matrix with the highest sum of boundary elements.
 ```
 
 #include <stdio.h>

int main()
{
   int width=0,height=0,arr[100][100],k=0;
   int i,j,a,b,tempSum=0,tempElement,maxTempSum=0, maxtempElement, maxI, maxJ;
   printf("Enter the width:");
   scanf("%d",&width);
   printf("\nEnter the height:");
   scanf("%d",&height);
   printf("\nEnter the elements of matrix...\n");
   for(int x=0;x<=height-1;x++)
   {
       for(int y=0;y<=width-1;y++)
       {
          scanf("%d",&arr[x][y]) ;
       }
   }
    for(int x=0;x<=height-1;x++)
   {
       for(int y=0;y<=width-1;y++)
       {
          printf("%d",arr[x][y]) ;
       }
       printf("\n");
   }
   printf("\nInput maximum width of square submatrix (for square submatrix height and width are same) :");
   scanf("%d",&k);
   for(i=0;i<=height-k;i++)
   {
       for(j=0;j<=width-k;j++)
       {
           tempElement=arr[i][j];
           for(a=j;a<j+k;a++)
           {
               tempSum=arr[i][a]+tempSum;
               tempSum=arr[i+k-1][a]+tempSum;
           }
           for(b=i+1;b<i+k-1;b++)
           {
               tempSum=arr[b][j]+tempSum;
               tempSum=arr[b][j+k-1]+tempSum;
           }
           if(maxTempSum < tempSum)
           {
               maxTempSum = tempSum;
               maxtempElement = tempElement;
               maxI = i;
               maxJ = j;
           }
           tempSum = 0;
           //printf("\n%d %d %d %d",tempSum,tempElement, i, j);
       }
       //printf("\n%d %d %d %d",tempSum,tempElement, i, j);
   }
   //printf("\n%d %d %d %d",maxTempSum,maxtempElement, maxI, maxJ);
  for(i = maxI; i< maxI+k; i++)
   {
       for(j = maxJ; j< maxJ+k; j++)
       {
            printf("%d ", arr[i][j]);
       }
       printf("\n");
   }
    return 0;
}

```
