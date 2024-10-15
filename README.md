Common elements in all row of a given matrix in C
Here, in this page we will discuss the program to find the common elements in all row of a given matrix in C+Programming language. We will discuss algorithm along it’s code.

Common elements in all row of a given matrix in C
Algorithm :
In this algorithm we will check for every element in first row, if that is present in other rows or not.

For checking the presence, take one variable count.
Now, run a loop from index 1 to M.
Take a variable flag =0;
Now, run a loop from index 0 to N, if (x==mat[i][j]) set flag =1 and break the loop.
After coming out from loop check if(flag==1) set, count++.
At last, check if count == M-1, print that value.
Time and Space Complexity :
Time complexity: O(M*M*N)
Space complexity: O(1)
Code in C
Run
#include <stdio.h>
#define M 4
#define N 5
 
void printCommonElements(int mat[M][N])
{
   
    for (int j = 0; j < N; j++)
    {   
        int x = mat[0][j], count = 0;
        
        for (int i = 1; i < M; i++){
            int flag = 0;
            for(int j = 0; j < N; j++){
                 if(x==mat[i][j]){
                     flag = 1;
                     mat[i][j] = -1;
                     break;
                 }        
            }
            if(flag==1){
                count++;   
            }
        }
        
        if (count==M-1)
            printf("%d ", x);
            
    }
   
}
 
int main()
{
    int mat[M][N] =
    {
        {10, 20, 10, 40, 80},
        {30, 70, 80, 50, 10},
        {80, 70, 70, 30, 10},
        {80, 10, 20, 70, 90},
    };
 
    printCommonElements(mat);
 
    return 0;
}
Output :
10 80
