# 3-tacos-de-asada
Sudoku


#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main(){
    
    int input[100];
    int a [10][10][10] = {0}; // a [fila][columna][cuadrante]
    int otro [91] = {0};
    int de [91] = {0};
    int lengua [91] = {0};
    int col = 0, filete = 1, num, u = 1, uu, ll, filete_de_asada, cebollita, colcol, ans, k = 0, x = 0, j = 0;
    
    fstream textfile;
    
    textfile.open("sudoku01.txt");
    
    for(int i = 0; i<=81; i++){
        
        textfile >> input[i];
        if(i == 9 || i == 18 || i == 27 || i == 36 || i == 45 || i == 54 || i == 63 || i == 72 || i == 81){
            
            filete = filete + 1;
            
        }
        
        if(i == 9 || i == 18 || i == 27 || i == 36 || i == 45 || i == 54 || i == 63 || i == 72 || i == 81){
            
            col = 0;
            
        }
        
        col = col + 1;
        
        
        if(((3>=filete)&&(filete>=1)) && ((3>=col)&&(col>=1))){// 1 cuadrantes

            u = 1;
            
        }
        
        if(((3>=filete)&&(filete>=1)) && ((6>=col)&&(col>=4))){// 2 cuadrantes

            u = 2;

        }
        
        if(((3>=filete)&&(filete>=1)) && ((9>=col)&&(col>=7))){// 3 cuadrante
            
            u = 3;
            
        }
        
        if(((6>=filete)&&(filete>=4)) && ((3>=col)&&(col>=1))){// 4 cuadrante

            u = 4;

            
        }
        
        if(((6>=filete)&&(filete>=4)) && ((6>=col)&&(col>=4))){// 5 cuadrante

            u = 5;

            
        }
        
        if(((6>=filete)&&(filete>=4)) && ((9>=col)&&(col>=7))){// 6 cuadrante

            u = 6;

        }
        
        if(((9>=filete)&&(filete>=7)) && ((3>=col)&&(col>=1))){// 7 cuadrante

            u = 7;

        }
        
        if(((9>=filete)&&(filete>=7)) && ((6>=col)&&(col>=4))){// 8 cuadrante

            u = 8;

        }
        
        if(((9>=filete)&&(filete>=7)) && ((9>=col)&&(col>=7))){// 9 cuadrante
            
            u = 9;
        }
     
        
        a [filete][col][u] = input[i];
        
        if(a [filete][col][u] != 0){
            
            otro [j] = filete;
            de [j] = col;
            lengua [j] = u;
            
            j = j + 1;
            
        }
        
    }
    
    //\033[1;31mQWERT\033[0m
     
     do{
     
     cout <<"  |  \033[1;31m1\033[0m  |  \033[1;31m2\033[0m  |  \033[1;31m3\033[0m  ||  \033[1;31m4\033[0m  |  \033[1;31m5\033[0m  |  \033[1;31m6\033[0m  ||  \033[1;31m7\033[0m  |  \033[1;31m8\033[0m  |  \033[1;31m9\033[0m  |  "<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m1\033[0m |  "<<a [1][1][1]<<"  |  "<< a [1][2][1] <<"  |  "<< a [1][3][1] <<"  ||  "<< a [1][4][2] <<"  |  "<< a [1][5][2] <<"  |  "<< a [1][6][2] <<"  ||  "<< a [1][7][3] <<"  |  "<< a [1][8][3] <<"  |  "<< a [1][9][3] <<"  | \033[1;31m1\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m2\033[0m |  "<< a [2][1][1] <<"  |  "<< a [2][2][1] <<"  |  "<< a [2][3][1] <<"  ||  "<< a [2][4][2] <<"  |  "<< a [2][5][2] <<"  |  "<< a [2][6][2] <<"  ||  "<< a [2][7][3] <<"  |  "<< a [1][8][3] <<"  |  "<< a [1][9][3] <<"  | \033[1;31m2\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m3\033[0m |  "<< a [3][1][1] <<"  |  "<< a [3][2][1] <<"  |  "<< a [3][3][1] <<"  ||  "<< a [3][4][2] <<"  |  "<< a [3][5][2] <<"  |  "<< a [3][6][2] <<"  ||  "<< a [3][7][3] <<"  |  "<< a [1][8][3] <<"  |  "<< a [1][9][3] <<"  | \033[1;31m3\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m4\033[0m |  "<< a [4][1][4] <<"  |  "<< a [4][2][4] <<"  |  "<< a [4][3][4] <<"  ||  "<< a [4][4][5] <<"  |  "<< a [4][5][5] <<"  |  "<< a [4][6][5] <<"  ||  "<< a [4][7][6] <<"  |  "<< a [4][8][6] <<"  |  "<< a [4][9][6] <<"  | \033[1;31m4\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m5\033[0m |  "<< a [5][1][4] <<"  |  "<< a [5][2][4] <<"  |  "<< a [5][3][4] <<"  ||  "<< a [5][4][5] <<"  |  "<< a [5][5][5] <<"  |  "<< a [5][6][5] <<"  ||  "<< a [5][7][6] <<"  |  "<< a [5][8][6] <<"  |  "<< a [5][9][6] <<"  | \033[1;31m5\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m6\033[0m |  "<< a [6][1][4] <<"  |  "<< a [6][2][4] <<"  |  "<< a [6][3][4] <<"  ||  "<< a [6][4][5] <<"  |  "<< a [6][5][5] <<"  |  "<< a [6][6][5] <<"  ||  "<< a [6][7][6] <<"  |  "<< a [6][8][6] <<"  |  "<< a [6][9][6] <<"  | \033[1;31m6\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m7\033[0m |  "<< a [7][1][7] <<"  |  "<< a [7][2][7] <<"  |  "<< a [7][3][7] <<"  ||  "<< a [7][4][8] <<"  |  "<< a [7][5][8] <<"  |  "<< a [7][6][8] <<"  ||  "<< a [7][7][9] <<"  |  "<< a [7][8][9] <<"  |  "<< a [7][9][9] <<"  | \033[1;31m7\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m8\033[0m |  "<< a [8][1][7] <<"  |  "<< a [8][2][7] <<"  |  "<< a [8][3][7] <<"  ||  "<< a [8][4][8] <<"  |  "<< a [8][5][8] <<"  |  "<< a [8][6][8] <<"  ||  "<< a [8][7][9] <<"  |  "<< a [8][8][9] <<"  |  "<< a [8][9][9] <<"  | \033[1;31m8\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"\033[1;31m9\033[0m |  "<< a [9][1][7] <<"  |  "<< a [9][2][7] <<"  |  "<< a [9][3][7] <<"  ||  "<< a [9][4][8] <<"  |  "<< a [9][5][8] <<"  |  "<< a [9][6][8] <<"  ||  "<< a [9][7][9] <<"  |  "<< a [9][8][9] <<"  |  "<< a [9][9][9] <<"  | \033[1;31m9\033[0m"<< endl;
     cout <<"--+-----+-----+-----++-----+-----+-----++-----+-----+-----+--"<< endl;
     cout <<"  |  \033[1;31m1\033[0m  |  \033[1;31m2\033[0m  |  \033[1;31m3\033[0m  ||  \033[1;31m4\033[0m  |  \033[1;31m5\033[0m  |  \033[1;31m6\033[0m  ||  \033[1;31m7\033[0m  |  \033[1;31m8\033[0m  |  \033[1;31m9\033[0m  |  "<< endl;
     
     cout << "1. Write, 2. Erease, 3. Off" << endl;
     cin >> ans;
     
     switch (ans) {
     case (1):
     k = 0;
     x = 0;
     cout << "Columna" << endl;
     cin >> col;
     cout << "Fila (numero)" << endl;
     cin >> filete;
     cout << "Numero" << endl;
     cin >> num;
             
             system("Clear");

             
     if(((3>=filete)&&(filete>=1)) && ((3>=col)&&(col>=1))){// 1 cuadrantes
     
     ll = 1;
     uu = 1;
     u = 1;
     cebollita = colcol = 1;
     filete_de_asada = 1;
     
     }
     
     if(((3>=filete)&&(filete>=1)) && ((6>=col)&&(col>=4))){// 2 cuadrantes
     
     ll = 2;
     uu = 1;
     u = 2;
     cebollita = colcol = 4;
     filete_de_asada = 1;
     }
     
     if(((3>=filete)&&(filete>=1)) && ((9>=col)&&(col>=7))){// 3 cuadrante
     
     ll = 3;
     uu = 1;
     u = 3;
     cebollita = colcol = 7;
     filete_de_asada = 1;
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((3>=col)&&(col>=1))){// 4 cuadrante
     
     ll = 1;
     uu = 4;
     u = 4;
     cebollita = colcol = 1;
     filete_de_asada = 4;
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((6>=col)&&(col>=4))){// 5 cuadrante
     
     ll = 2;
     uu = 4;
     u = 5;
     cebollita = colcol = 4;
     filete_de_asada = 4;
     
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((9>=col)&&(col>=7))){// 6 cuadrante
     
     ll = 3;
     uu = 4;
     u = 6;
     cebollita = colcol = 7;
     filete_de_asada = 4;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((3>=col)&&(col>=1))){// 7 cuadrante
     
     ll = 1;
     uu = 7;
     u = 7;
     cebollita = colcol = 1;
     filete_de_asada = 7;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((6>=col)&&(col>=4))){// 8 cuadrante
     
     ll = 2;
     uu = 7;
     u = 8;
     cebollita = colcol = 4;
     filete_de_asada = 7;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((9>=col)&&(col>=7))){// 9 cuadrante
     
     ll = 3;
     uu = 7;
     u = 9;
     cebollita = colcol = 7;
     filete_de_asada = 7;
     
     }
     
             for(int j = 0; j < 91; j++){
                 
                 if( otro [j] == filete && de [j] == col && lengua[j] == u){
                     
                     x = 1;
                     cout << "Los numeros dados no se pueden cambiar" << endl;
                     
                 }
                 
             }

             if( x == 0){
                 
                 a[filete][col][u] = num;

     
     for(int i = 0; i < 10; i++){//fila
     
     if(i == 3 || i == 6){
     
     uu = uu + 1;
     }
     
     if(a[filete][i][uu] == a[filete][col][u]){
     
     if(i != col){
     cout << "Numero invalido, el numero se repite en la fila" << endl;
     i = 10;
     k = k + 1;
     }
     }
     }
     
     for(int i = 0; i < 10; i++){//Columna
     
     if(i == 3 || i == 6){
     
     ll = ll + 3;
     }
     
     if(a[i][col][ll] == a[filete][col][u]){
     
     if(i != filete){
     cout << "Numero invalido, el numero se repite en la columna" << endl;
     i = 10;
     k = k + 2;
     }
     }
     }
     
     for(int i = 0; i < 10; i++){//cuadrante
     
     if(i == 3 || i == 6){
     
     filete_de_asada = filete_de_asada + 1;
     colcol = cebollita;
     
     }
     
     
     if(a[filete_de_asada][colcol][u] == a[filete][col][u]){
     
     if(filete != filete_de_asada){
     cout << "Numero invalido, el numero se repite en el cudrante" << endl;
     i = 10;
     k = k + 3;
     }
     }
     colcol = colcol + 1;
     
     }
     
     if(k != 0){
     
     a[filete][col][u] = 0;
     
     }
     }

     
     break;
     
     case(2):
     
     cout << "Columna" << endl;
     cin >> col;
     cout << "Fila (numero)" << endl;
     cin >> filete;
     
     if(((3>=filete)&&(filete>=1)) && ((3>=col)&&(col>=1))){// 1 cuadrantes
     
     ll = 1;
     uu = 1;
     u = 1;
     cebollita = colcol = 1;
     filete_de_asada = 1;

     }
     
     if(((3>=filete)&&(filete>=1)) && ((6>=col)&&(col>=4))){// 2 cuadrantes
     
     ll = 2;
     uu = 1;
     u = 2;
     cebollita = colcol = 4;
     filete_de_asada = 1;
     }
     
     if(((3>=filete)&&(filete>=1)) && ((9>=col)&&(col>=7))){// 3 cuadrante
     
     ll = 3;
     uu = 1;
     u = 3;
     cebollita = colcol = 7;
     filete_de_asada = 1;
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((3>=col)&&(col>=1))){// 4 cuadrante
     
     ll = 1;
     uu = 4;
     u = 4;
     cebollita = colcol = 1;
     filete_de_asada = 4;
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((6>=col)&&(col>=4))){// 5 cuadrante
     
     ll = 2;
     uu = 4;
     u = 5;
     cebollita = colcol = 4;
     filete_de_asada = 4;
     
     }
     
     if(((6>=filete)&&(filete>=4)) && ((9>=col)&&(col>=7))){// 6 cuadrante
     
     ll = 3;
     uu = 4;
     u = 6;
     cebollita = colcol = 7;
     filete_de_asada = 4;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((3>=col)&&(col>=1))){// 7 cuadrante
     
     ll = 1;
     uu = 7;
     u = 7;
     cebollita = colcol = 1;
     filete_de_asada = 7;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((6>=col)&&(col>=4))){// 8 cuadrante
     
     ll = 2;
     uu = 7;
     u = 8;
     cebollita = colcol = 4;
     filete_de_asada = 7;
     }
     
     if(((9>=filete)&&(filete>=7)) && ((9>=col)&&(col>=7))){// 9 cuadrante
     
     ll = 3;
     uu = 7;
     u = 9;
     cebollita = colcol = 7;
     filete_de_asada = 7;
     

     }
             for(int j = 0; j < 91; j++){
                 
                 if( otro [j] == filete && de [j] == col && lengua[j] == u){
                     
                     x = 1;
                     
                     cout << "Los numeros dados no se pueden cambiar" << endl;
                     
                 }
                 
             }

             if(x == 0){
             
             a[filete][col][u] = 0;
             }
     
     break;
     
     case(3):
     cout << "BYE" << endl;
     break;
     
     default:
     ans = 1;
     break;
     }
     
     }while(ans == 1 || ans == 2);
     
     cout << "Hello world" << endl;
    
    return 0;
}
