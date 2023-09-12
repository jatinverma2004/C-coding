# C-coding
#Casino Game Project
#
This C++ code is a simple casino game program that allows users to play three different games (slot game, number guessing, and roulette) with a starting balance of Rs. 10,000, where they can place bets and potentially win or lose money based on the outcomes of these games.

#include <iostream>
#include <ctime>
#include <cstdlib>
#include <unistd.h>
#include <algorithm>
#include <iterator>  

using namespace std;
int main()
{
    int balance = 10000;
    cout << "**************** WELCOME TO JATIN CASINO GAME ************************" << endl;

    while (true)
    {
        cout << "You currently have Rs." << balance << endl;
        cout << "Which game would you like to play? : " << endl;
        cout << "                                         " << endl;
        cout << "1. Casino --> Slot Game " << endl;
        cout << "2. Guess The Number Between [1 - 5] " << endl;
        cout << "3. Roulette :- Bet On Your Numbers " << endl;
        cout << "                                     " << endl;
        cout << "Press [1] , [2] , [3]" << endl;
        int a, b, check;
        cin >> a;

        if (a == 1)
        {
            srand(time(0));
            cout << "BET On Your Money" << endl;
            cin >> b;

            if (b <= balance && b > 0)
            {
                cout << "LETS SEE YOUR LUCK!!" << endl;
                cout << "                     " << endl;
                usleep(2000000);

                int num1 = (rand() % 10);
                int num2 = (rand() % 10);
                int num3 = (rand() % 10);
                cout << num1 << "   " << num2 << "   " << num3 << "   " << endl;

                if (num1 % 2 == 0 && num2 % 2 == 0 && num3 % 2 == 0)
                {
                    cout << "    " << endl;
                    cout << " Woohoo CONGRATULATIONS!!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + b * 2;
                    cout << "You Have Won: Rs." << b * 2 << endl;
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }

                else if (num1 % 2 != 0 && num2 % 2 != 0 && num3 % 2 != 0)
                {
                    cout << "    " << endl;
                    cout << "  Yoooo CONGRATULATIONS!!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + b * 2;
                    cout << "You Have Won: Rs." << b * 2 << endl;
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }

                else if (num1 == num2 && num2 == num3 && num3 == num1)
                {
                    cout << "    " << endl;
                    cout << "CONGRATULATIONS!!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + b * 5;
                    cout << "You Have Won: Rs." << b * 5 << endl;
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }
                else if (num1 == 7 && num2 == 7 && num3 == 7)
                {
                    cout << "    " << endl;
                    cout << "CONGRATULATIONS!!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + b * 10;
                    cout << "You Have Won: Rs." << b * 10 << endl;
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }

                else
                {
                    cout << "    " << endl;
                    cout << "Better Luck Next Time!!  You Have Won Nothing !!" << endl;
                    cout << "     " << endl;
                    balance = (balance - b);
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }

                cout << endl;
                cout << endl;
                cout << "[Press 1] :--> If You Like To Try Another Game" << endl;
                cout << "[Press 2] :--> To QUIT" << endl;
                cout << endl;
                cin >> check;
                if (check == 2)
                {
                    cout << "Adios Amigo !!!" << endl;
                    break;
                }
                else
                {
                    if (balance > 0)
                    {
                        cout << "LETS PLAY !!!!" << endl
                            << endl;
                    }
                    else
                    {
                        cout << " SORRY YOU HAVE NO BALANCE " << endl;
                        break;
                    }
                }
            }

            else if (b < 0)
            {
                cout << "You Cannot Place A Bet in Negative" << endl;
            }
            else
            {
                cout << "You Cannot PLace A Bet More Than Your Current Balance " << endl;
            }
        }

        if (a == 2)
        {
            srand(time(0));
            cout << "BET Your Money" << endl
                << endl;
            cin >> b;

            if (b <= balance && b > 0)
            {
                cout << "Choose a Number Between [1-5] :- ";
                int c;
                cin >> c;

                cout << "LETS SEE YOUR LUCK !!" << endl;
                cout << "                     " << endl;
                usleep(2000000); // 1sec = 1000000 microsec
                int num = (rand() % 5);
                cout << "The Number Choosen By Computer :- " << num << endl;

                if (num == c)
                {
                    cout << endl;
                    cout << "CONGRATULATIONS !!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + b * 2;
                    cout << "You Have Won : Rs." << b * 2 << endl;
                    cout << "YOUR CURRENT BALANCE IS: Rs." << balance << endl;
                }

                else
                {
                    cout << "    " << endl;
                    cout << "OOPS ! You Have Won Nothing !!" << endl;
                    cout << "     " << endl;
                    balance = (balance - b);
                    cout << "YOUR CURRENT BALANCE: Rs." << balance << endl;
                }

                cout << endl;
                cout << endl;
                cout << "[Press 1] :--> If You Like To Try Another Game" << endl;
                cout << "[Press 2] :--> To QUIT" << endl;
                cout << endl;
                cin >> check;
                if (check == 2)
                {
                    cout << "Adios Amigo Bro !!!" << endl;
                    break;
                }
                else
                {
                    if (balance > 0)
                    {
                        cout << "LETS PLAY !!!!" << endl
                            << endl;
                    }
                    else
                    {
                        cout << " SORRY YOU HAVE NO BALANCE " << endl;
                        break;
                    }
                }
            }

            else if (b < 0)
            {
                cout << "You Cannot Place A Bet in Negative" << endl;
            }
            else
            {
                cout << "You Cannot PLace A Bet More Than Your Current Balance " << endl;
            }
        }

        if (a == 3)
        {
            cout << endl;
            cout << "Bet On Your Money" << endl << endl;

            cin >> b;
            if (b <= balance)
            {
                cout << "On how many numbers do you want to place your bet [1 - 36] :- ";
                int f;
                cin >> f;
                int moneynum = b / f;
                cout << "Bet on EACH Number :- $" << moneynum << endl;
                int number[f];
                for (int i = 0; i < f; i++) {
                    cout << "On Which Number Do You Want To Place Your Bet :- ";
                    cin >> number[i];

                }
                cout << endl << "Lets See Your Luck !!! " << endl << endl;
                usleep(2000000);
                srand(time(0));
                int random = 1 + (rand() % 36);
                cout << "The Number Choosen By Computer :- " << random << endl;
                int z = 0;
                for (int i = 0; i < f; i++)
                {
                    if (number[i] == random)
                    {
                        z = z + 1;
                    }
                }
                if (z > 0) {
                    cout << endl;
                    cout << "CONGRATULATIONS !!!!" << endl;
                    cout << "     " << endl;
                    balance = balance + (moneynum * 36);
                    cout << "You Have Won :--> Rs." << moneynum * 36 << endl;
                    cout << "YOUR CURRENT BALANCE --> Rs." << balance << endl;

                }
                else {
                    cout << "    " << endl;
                    cout << "OOPS ! You Have Won Nothing !!" << endl;
                    cout << "     " << endl;
                    balance = (balance - b);
                    cout << "YOUR CURRENT BALANCE --> $" << balance << endl;

                }
                cout << endl;
                cout << endl;
                cout << "[Press 1] :--> If You Like To Try Another Game" << endl;
                cout << "[Press 2] :--> To QUIT" << endl;
                cout << endl;
                cin >> check;
                if (check == 2)
                {
                    cout << "GOODBYE !!!" << endl;
                    break;
                }
                else
                {
                    if (balance > 0)
                    {
                        cout << "LETS PLAY !!!!" << endl
                            << endl;
                    }
                    else
                    {
                        cout << " SORRY YOU HAVE NO BALANCE " << endl;
                        break;
                    }
                }
            }
            else if (b < 0)
            {
                cout << "You Cannot Place A Bet in Negative" << endl;
            }
            else
            {
                cout << "You Cannot PLace A Bet More Than Your Current Balance " << endl;
            }
        }
    }
    return 0;
}

