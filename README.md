#include<bits/stdc++.h>
#include<cstdio>
#include <stdio.h>
#include <stdlib.h>
#include<conio.h>
#include<math.h>
#include<string.h>

using namespace std;

void trace (int arr[][10], int m, int n)
{
    int i, j, trace = 0;
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < n; j++)
        {
            if (i == j)
            {
                trace = trace + arr[i][j];
            }
        }
    }
    printf("Trace of the resultant matrix is = %d\n", trace);
}
int main()
{
    int n;
Home:
    {

        printf("                        \xDB\xDB\xDB\xB2  DIU MATRIX v1.0 \xB2\xDB\xDB\xDB \n");
        printf("\n");
        printf("                  What Operation do you want do?\n");
        printf("\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 1 for Addition / Subtraction of a matrix. \xDB\xDB\xDB\xDB\xB2\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 2 for Multiplication of a matrix.         \xDB\xDB\xDB\xDB\xB2\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 3 for Equality of a matrix.               \xDB\xDB\xDB\xDB\xB2\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 4 for Transpose of a matrix.              \xDB\xDB\xDB\xDB\xB2\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 5 About Developer.                        \xDB\xDB\xDB\xDB\xB2\n");
        printf("        \xDB\xDB\xDB\xDB\xB2 6 Exit.                                   \xDB\xDB\xDB\xDB\xB2\n");
        scanf("%d",&n);
        if(n==1)
            goto Addition_Subtract;
        else if(n==2)
            goto Multiplication;
        else if(n==3)
            goto Equality;
        else if(n==4)
            goto Transpose;
        else if(n==5)
            goto About;
        else if(n==6)
            return 0;
    }
Addition_Subtract:
    {
        if(n==1)
        {
            int array1[10][10], array2[10][10], arraysum[10][10],arraydiff[10][10];
            int i, j, m, n, option;

            printf("Enter the order of the matrix array1 and array2 \n");
            scanf("%d %d", &m, &n);
            printf("Enter the elements of matrix array1 \n");
            for (i = 0; i < m; i++)
            {
                for (j = 0; j < n; j++)
                {
                    scanf("%d", &array1[i][j]);
                }
            }
            printf("MATRIX array1 is \n");
            for (i = 0; i < m; i++)
            {
                for (j = 0; j < n; j++)
                {
                    printf("%3d", array1[i][j]);
                }
                printf("\n");
            }
            printf("Enter the elements of matrix array2 \n");
            for (i = 0; i < m; i++)
            {
                for (j = 0; j < n; j++)
                {
                    scanf("%d", &array2[i][j]);
                }
            }
            printf("MATRIX array2 is \n");
            for (i = 0; i < m; i++)
            {
                for (j = 0; j < n; j++)
                {
                    printf("%3d", array2[i][j]);
                }
                printf("\n");
            }
            printf("Enter your option: 1 for Addition and 2 for Subtraction \n");
            scanf("%d", &option);
            if(option==1)
            {
                for (i = 0; i < m; i++)
                {
                    for (j = 0; j < n; j++)
                    {
                        arraysum[i][j] = array1[i][j] + array2[i][j];
                    }
                }
                printf("Sum matrix is \n");
                for (i = 0; i < m; i++)
                {
                    for (j = 0; j < n; j++)
                    {
                        printf("%3d", arraysum[i][j]) ;
                    }
                    printf("\n");
                }
            }

            else if(option == 2)
            {
                for (i = 0; i < m; i++)
                {
                    for (j = 0; j < n; j++)
                    {
                        arraydiff[i][j] = array1[i][j] - array2[i][j];
                    }
                }
                printf("Difference matrix is \n");
                for (i = 0; i < m; i++)
                {
                    for (j = 0; j < n; j++)
                    {
                        printf("%3d", arraydiff[i][j]) ;
                    }
                    printf("\n");
                }
            }

        }
        goto exit_panel;
    }
Multiplication :
    {

        int m,n,sum=0;
        int first [10][10],second[10][10],multiply[10][10];
        printf("Enter the number of first rows and columns of matrix\n");
        scanf("%d %d",&m,&n);
        int c,d,k;
        printf("Enter the elements of first matrix\n");
        for(c=0; c<m; c++)
            for(d=0; d<n; d++)
                scanf("%d",&first[c][d]);
        int p,q;
        printf("Enter the number of second rows and columns of matrix\n");
        scanf("%d %d",&p,&q);
        if(n!=p)
            printf("Matrix with entered order can't be multiple with each other\n");
        else
        {
            printf("Enter the elements of second matrix\n");
            for(c=0; c<p; c++)
                for(d=0; d<q; d++)
                    scanf("%d",&second[c][d]);
            for(c=0; c<m; c++)
            {
                for(d=0; d<q; d++)
                {
                    for(k=0; k<p; k++)
                    {
                        sum=sum+first[c][k]*second[k][d];
                    }
                    multiply[c][d]=sum;
                    sum=0;
                }
            }
            printf("Product entered matrix: \n");
            for(c=0; c<m; c++)
            {
                for(d=0; d<q; d++)
                    printf("%d\t",multiply[c][d]);
                printf("\n");
            }
        }
        goto exit_panel;
    }
Transpose:
    {

        int m,n,c,d;
        int matrix[100][100],transpose[10][10];
        printf("Enter the number of rows and columns of matrix\n");
        scanf("%d %d",&m,&n);
        printf("Enter the elements of matrix\n");
        for(c=0; c<m; c++)
        {
            for(d=0; d<n; d++)
            {
                scanf("%d",&matrix[c][d]);
            }
        }
        for(c=0; c<m; c++)
        {
            for(d=0; d<n; d++)
            {
                transpose[d][c]=matrix[c][d];
            }
        }
        printf("Transpose of entered matrix:\n");
        for(c=0; c<n; c++)
        {
            for(d=0; d<m; d++)
            {
                printf("%d\t",transpose[c][d]);
            }
            printf("\n");
        }

        goto exit_panel;
    }
Equality:
    {

        int a[10][10], b[10][10];
        int i, j, row1, column1, row2, column2, flag = 1;

        printf("Enter the order of the matrix A \n");
        scanf("%d %d", &row1, &column1);
        printf("Enter the order of the matrix B \n");
        scanf("%d %d", &row2, &column2);
        printf("Enter the elements of matrix A \n");
        for (i = 0; i < row1; i++)
        {
            for (j = 0; j < column1; j++)
            {
                scanf("%d", &a[i][j]);
            }
        }
        printf("Enter the elements of matrix B \n");
        for (i = 0; i < row2; i++)
        {
            for (j = 0; j < column2; j++)
            {
                scanf("%d", &b[i][j]);
            }
        }
        printf("MATRIX A is \n");
        for (i = 0; i < row1; i++)
        {
            for (j = 0; j < column1; j++)
            {
                printf("%3d", a[i][j]);
            }
            printf("\n");
        }
        printf("MATRIX B is \n");
        for (i = 0; i < row2; i++)
        {
            for (j = 0; j < column2; j++)
            {
                printf("%3d", b[i][j]);
            }
            printf("\n");
        }
        if (row1 == row2 && column1 == column2)
        {
            printf("Matrices can be compared \n");
            for (i = 0; i < row1; i++)
            {
                for (j = 0; j < column2; j++)
                {
                    if (a[i][j] != b[i][j])
                    {
                        flag = 0;
                        break;
                    }
                }
            }
        }
        else
        {
            printf(" Cannot be compared\n");
            exit(1);
        }
        if (flag == 1)
            printf("Two matrices are equal \n");
        else
            printf("But, two matrices are not equal \n");
        goto exit_panel;
    }
About:
    {
        printf("\xDB\xDB\xDB\xDB\xB2 About \xDB\xDB\xDB\xDB\xB2\n\n");
        printf("\xDB\xDB\xDB\xDB\xB2  Pritam chandra shil\n");
        printf("@DotTrimatrik, Daffodil International University - DIU\n");
        printf("\xDB\xDB\xDB\xDB\xB2  Md Ariful Islam\n");
        printf("@DotTrimatrik,  DIU\n");
        printf("\xDB\xDB\xDB\xDB\xB2 Sarowar Jahan Shajib\n");
        printf("@DotTrimatrik,  DIU\n");
        printf("\n\n\n");
        printf("If you find any bug or if you want suggest/advice please \n mail us at dottrimatrik@gmail.com\n\n\n\n");

        goto exit_panel;
    }

exit_panel:
    {
        printf("Press 1 for continue or 2 for exit\n");
        int x;
        scanf("%d",&x);
        if(x==1)
            goto Home;
        else if(x==2)
            return 0;
    }
    getch();
    return 0;
}
