#include <iostream>
using namespace std;
 char grid[10] = { 'o', '1', '2', '3', '4', '5', '6', '7', '8', '9' };
 /*******************************************************************
DRAW SQUAREBOARD OF TIC TAC TOE WITH PLAYERS' SPOT
 ********************************************************************/
 void display(){
    
     cout<<"\n \t \t Tic Tac Toe \n \n \n";
     cout<<" \t Player1 (X)  -  Player2 (O) \n \n";



     cout<<"       |       |     \n";
    cout<<"  "<<grid[1]   <<"    |"<<"  "<<grid[2]  <<"    |"<<"  "<<grid[3]   <<"    \n";
    cout<<"_______|_______|_______\n";
    cout<<"       |       |     \n";
    cout<<"       |       |     \n";
    cout<<"  "<<grid[4]   <<"    |"<<"  "<<grid[5]  <<"    |"<<"  "<<grid[6]   <<"    \n";
    cout<<"_______|_______|_______\n";
    cout<<"       |       |     \n";
    cout<<"       |       |     \n";
    cout<<"  "<<grid[7]   <<"    |"<<"  "<<grid[8]  <<"    |"<<"  "<<grid[9]   <<"    \n";
    cout<<"       |       |     \n";
     }
     /*********************************************
FUNCTION TO GIVE GAME STATUS
1 FOR THE GAME IS OVER WITH THE RESULT
-1 FOR THE GAME IS IN PROGRESS
O GAME IS OVER, AND NO RESULT
 **********************************************/
     
 int findwinner(char grid[])
{
    if (grid[1] == grid[2] && grid[2] == grid[3])
        return 1;
        
    else if (grid[4] == grid[5] && grid[5] == grid[6])
        return 1;
        
    else if (grid[7] == grid[8] && grid[8] == grid[9])
        return 1;
        
    else if (grid[1] == grid[4] && grid[4] == grid[7])
        return 1;
        
    else if (grid[2] == grid[5] && grid[5] == grid[8])
        return 1;
        
    else if (grid[3] == grid[6] && grid[6] == grid[9])
        return 1;
        
    else if (grid[1] == grid[5] && grid[5] == grid[9])
        return 1;
        
    else if (grid[3] == grid[5] && grid[5] == grid[7])
        return 1;
        
    else if (grid[1] != '1' && grid[2] != '2' && grid[3] != '3' &&
        grid[4] != '4' && grid[5] != '5' && grid[6] != '6' && grid[7] 
        != '7' && grid[8] != '8' && grid[9] != '9')


        return 0;
    else
        return  - 1;
}


 int main(){


     int player = 1, check, wish;
     char spot;


    do
    {
        display();
        player = (player % 2) ? 1 : 2;


        cout<<" Player"<<player<<" enter a digit ";
        cin>>wish;


        spot = (player == 1) ? 'X' : 'O';


       if (wish == 1 && grid[1] == '1')
            grid[1] = spot;
            
        else if (wish == 2 && grid[2] == '2')
            grid[2] = spot;
            
        else if (wish == 3 && grid[3] == '3')
            grid[3] = spot;
            
        else if (wish == 4 && grid[4] == '4')
            grid[4] = spot;
            
        else if (wish == 5 && grid[5] == '5')
            grid[5] = spot;
            
        else if (wish == 6 && grid[6] == '6')
            grid[6] = spot;
            
        else if (wish == 7 && grid[7] == '7')
            grid[7] = spot;
            
        else if (wish == 8 && grid[8] == '8')
            grid[8] = spot;
            
        else if (wish == 9 && grid[9] == '9')
            grid[9] = spot;
            
        else
        {
            cout<<"Invalid move by the player";


            player--;
          
        }
        check = findwinner(grid);


        player++;
    }while (check ==  - 1);
    
    display();
    
    if (check == 1)
        cout<<"==>\aPlayer"<< -- player<<" win. Congratulations!";
    else
        cout<<"==>\aGame draw! Better luck next time!";
        
    return 0;
    
 }
