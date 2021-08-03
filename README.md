# Robo-Aleatorio-C
O Robô representado pelo "@" busca a saída "*" através de movimentos aleatórios

#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <time.h>

int main()
{

      int n1 = 6;
    int n2 = 5;
    int pi;
     time_t t2; // para fazer os passos
     int t5 =1;
    int pj;
    int n =0;
    int r =0;
    int b =0;
    char t;
    char M[6][5];
    char J[1000];
    srand((unsigned) time(&t2));

    M[0][0]= 'x';M[0][1]= 'x';M[0][2]= '*';M[0][3]= 'x';M[0][4]= 'x';
    M[1][0]= 'x';M[1][1]= ' ';M[1][2]= ' ';M[1][3]= ' ';M[1][4]= 'x';
    M[2][0]= 'x';M[2][1]= 'x';M[2][2]= 'x';M[2][3]= ' ';M[2][4]='x';
    M[3][0]= 'x';M[3][1]= ' ';M[3][2]= ' ';M[3][3]= ' ';M[3][4]= 'x';
    M[4][0]= 'x';M[4][1]= '@';M[4][2]= ' ';M[4][3]= ' ';M[4][4]= 'x';
    M[5][0]= 'x';M[5][1]= 'x';M[5][2]= 'x';M[5][3]= 'x';M[5][4]= 'x';
    while(b==0)
    {

        if(t5 == 1){
            printf("\n");printf("\n");
      for(int i = 0; i<n1; i++)
        {
            printf("\n");
            for(int j = 0; j<n2; j++)
            {
                printf("%c ",M[i][j]);
            }
        }
    t5=0;
     }
            for(int i = 0; i<n1; i++)
        {

            for(int j = 0; j<n2; j++)
            {
                if(M[i][j] == '@')
                {
                    pi = i;
                    pj = j;
                }
            }
        }

        r = rand() % 4;

    if(r==0)
    {
        if(M[pi-1][pj] != 'x')
        {
           if(M[pi-1][pj] == '*')
           {
               printf("\n\nAcabou!");
               b=1;
           }

           M[pi-1][pj] = M[pi][pj];
           M[pi][pj] = ' ';
           J[n] = 'N';
           n++;
           t5=1;
        }
    }
     if(r==1)
    {
        if(M[pi][pj+1] != 'x')
        {
            if(M[pi][pj+1] == '*')
           {
               printf("\n\nAcabou!");
               b=1;
           }
           M[pi][pj+1] = M[pi][pj];
           M[pi][pj] = ' ';
           J[n] = 'L';
           n++;
           t5=1;
        }
    }
    if(r==2)
    {
        if(M[pi+1][pj] != 'x')
        {
            if(M[pi+1][pj] == '*')
           {
               printf("\n\nAcabou!");
               b=1;
           }
           M[pi+1][pj] = M[pi][pj];
           M[pi][pj] = ' ';
           J[n] = 'S';
           n++;
           t5=1;
        }
    }
    if(r==3)
    {
        if(M[pi][pj-1] != 'x')
        {
            if(M[pi][pj-1] == '*')
           {
               printf("\n\nAcabou!");
               b=1;
           }
           M[pi][pj-1] = M[pi][pj];
           M[pi][pj] = ' ';
           J[n] = 'O';
           n++;
           t5=1;
        }
    }


      }
        printf("\n\nPassos: %d",n);
        printf("\n\nCaminho:");
        for(int w =0; w<n;w++)
        {
            printf("%c, ",J[w]);
        }


    return 0;
}
