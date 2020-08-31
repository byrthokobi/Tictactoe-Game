# Tictactoe-Game

#include<bits/stdc++.h>
using namespace std;

char square[12] = {"***********"};


string p1, p2;
int checkwin();
void board();

//checking the result

int checkwin()
{
    if (square[1] == square[2] && square[2] == square[3] && square[1] != '*' && square[2] != '*' && square[3] != '*'){
        return 1;
    }
    else if (square[4] == square[5] && square[5] == square[6] && square[4] != '*' && square[5] != '*' && square[6] != '*'){
        return 1;
    }
    else if (square[7] == square[8] && square[8] == square[9] && square[7] != '*' && square[8] != '*' && square[9] != '*'){
        return 1;
    }
    else if (square[1] == square[4] && square[4] == square[7] && square[1] != '*' && square[4] != '*' && square[7] != '*'){
        return 1;
    }
    else if (square[2] == square[5] && square[5] == square[8] && square[2] != '*' && square[5] != '*' && square[8] != '*'){
        return 1;
    }
    else if (square[3] == square[6] && square[6] == square[9] && square[3] != '*' && square[6] != '*' && square[9] != '*'){
        return 1;
    }
    else if (square[1] == square[5] && square[5] == square[9] && square[1] != '*' && square[5] != '*' && square[9] != '*'){
        return 1;
    }
    else if (square[3] == square[5] && square[5] == square[7] && square[3] != '*' && square[5] != '*' && square[7] != '*'){
        return 1;
    }
    else if (square[1] != '*' && square[2] != '*' && square[3] != '*'
                    && square[4] != '*' && square[5] != '*' && square[6] != '*'
                  && square[7] != '*' && square[8] != '*' && square[9] != '*'){
        return 0;
    }
    else
        return -1;
}

int main()
{
	int player = 1,i,choice;

	    cout << "\n\n\tKadir Bhai er Katakati\n\n";
       string p1, p2;
       cout << "Enter Player 1 Name: ";
       cin >> p1;
       cout << "\nEnter Player 2 Name: ";
       cin >> p2;
    cout << endl;
    char mark;
    int k = 1, f = 2;
    for(int i = 1;;i++, k++)
    {

        //making the board where the game will be played

        system("cls");
        cout << "\nKadir Bhai er Tictactoe\n\n";
       cout << "\n\tGame On\n";
       cout <<"\n" << p1 << " VS " << p2 << endl << endl;
       cout << "     ||     ||     " << endl;
       cout << "  " << square[1] << "  ||  " << square[2] << "  ||  " << square[3] << endl;
       cout << "_____||_____||_____" << endl;
       cout << "     ||     ||     " << endl;
       cout << "  " << square[4] << "  ||  " << square[5] << "  ||  " << square[6] << endl;
       cout << "_____||_____||_____" << endl;
       cout << "     ||     ||     " << endl;
       cout << "  " << square[7] << "  ||  " << square[8] << "  ||  " << square[9] << endl;
       cout << "     ||     ||     " << endl << endl;

       player=(player%2);

        if(player)
            cout << p1 << "'s turn: ";
        else
            cout << p2 << "'s turn: ";
        cin >> choice;

        mark=(player == 1) ? 'X' : 'O';

        if (choice == 1 && square[1] == '*')
            square[1] = mark;
        else if (choice == 2 && square[2] == '*')
            square[2] = mark;
        else if (choice == 3 && square[3] == '*')
            square[3] = mark;
        else if (choice == 4 && square[4] == '*')
            square[4] = mark;
        else if (choice == 5 && square[5] == '*')
            square[5] = mark;
        else if (choice == 6 && square[6] == '*')
            square[6] = mark;
        else if (choice == 7 && square[7] == '*')
            square[7] = mark;
        else if (choice == 8 && square[8] == '*')
            square[8] = mark;
        else if (choice == 9 && square[9] == '*')
            square[9] = mark;
        else
        {
            cout<<"Invalid move ";

            player--;
            //cin.ignore();
            //cin.get();
        }
        player++;
        f = checkwin();
        //cout << f << endl;
        if(f == 1 || f == 0)
            break;
    }
    //cout << "\n\n\tKadir Bhai er Katakati\n\n";
    cout <<"\n" << p1 << " VS " << p2 << " Game result" <<endl << endl;
    cout << "     ||     ||     " << endl;
    cout << "  " << square[1] << "  ||  " << square[2] << "  ||  " << square[3] << endl;

    cout << "_____||_____||_____" << endl;
    cout << "     ||     ||     " << endl;

    cout << "  " << square[4] << "  ||  " << square[5] << "  ||  " << square[6] << endl;

    cout << "_____||_____||_____" << endl;
    cout << "     ||     ||     " << endl;

    cout << "  " << square[7] << "  ||  " << square[8] << "  ||  " << square[9] << endl;

    cout << "     ||     ||     " << endl << endl;
    if(f == 1)
    {
        if(--player)
            cout << "==>\a"<< p1 << " Wins" << endl;
        else
            cout << "==>\a" << p2 << " Wins" << endl;
    }
    else
        cout<<"==>\aGame draw";

    cin.ignore();
    cin.get();
    return 0;
}

