# Tic-Tac-Toe
#include "stdafx.h"
#include <iostream>
using namespace std;

const int row = 3;
const int col = 3;

void player1Turn(char board[3][3])
{
	int row, col;
	char player = 'X';

	// Ask for the position to place an X.
	cout << "Player 1 turn 'X'" << endl;
	cout << "Which Row would you like?" << endl;
	cin >> row;
	cout << "Which Col would you like?" << endl;
	cin >> col;


	while (row < 0 || row > 2 || col < 0 || col > 2 || board[row][col] != ' ')
	{
		cout << "Illegal Move" << endl;
		cin >> row;
		cin >> col;

	}
	// set the position on the board to X
	board[row][col] = 'X';
}


void player2Turn(char board[3][3])
{
	int row, col;
	char player = 'O';

	// Ask for the position to place an X.
	cout << "Player 2 turn 'O'" << endl;
	cout << "Which Row would you like?" << endl;
	cin >> row;
	cout << "Which Col would you like?" << endl;
	cin >> col;


	while (row < 0 || row > 2 || col < 0 || col > 2 || board[row][col] != ' ')
	{
		cout << "Illegal Move" << endl;
		cin >> row;
		cin >> col;
	}

	// set the position on the board to O
	board[row][col] = 'O';
}


bool CheckWinner(char board[3][3])
{
	bool isWinner;

		//check to see if player1 won   
		{
		if (board[0][0] == board[0][1] && board[0][1] == board[0][2] && board[0][2] != ' ')
			isWinner = true;
		return true;

		if (board[1][0] == board[1][1] && board[1][1] == board[1][2] && board[1][2] != ' ')
			isWinner = true;
		return true;

		if (board[2][0] == board[2][1] && board[2][1] == board[2][2] && board[2][2] != ' ')
			isWinner = true;
		return true;


		if (board[0][0] == board[1][0] && board[1][0] == board[2][0] && board[2][0] != ' ')
			isWinner = true;
		return true;


		if (board[0][1] == board[1][1] && board[1][1] == board[2][1] && board[2][1] != ' ')
			isWinner = true;
		return true;


		if (board[0][2] == board[1][2] && board[1][2] == board[2][2] && board[2][2] != ' ')
			isWinner = true;
		return true;

		if (board[2][0] == board[1][1] && board[1][1] == board[0][2] && board[0][2] != ' ')
			isWinner = true;
		return true;

		if (board[0][0] == board[0][1] && board[0][1] == board[0][2] && board[0][2] != ' ')
			isWinner = true;
		return true;
	}
	return false;
}


void PrintBoard(char board[3][3])
{

	cout << board[0][0] << "|" << board[0][1] << "|" << board[0][2] << " \n";

	cout << "-----\n";
	cout << board[1][0] << "|" << board[1][1] << "|" << board[1][2] << " \n";

	cout << "-----\n";
	cout << board[2][0] << "|" << board[2][1] << "|" << board[2][2] << " \n";
}

void InitializeBoard(char board[3][3])
{
	for (int i = 0; i < 3; i++)
	{
		for (int j = 0; j < 3; j++)
		{
			board[i][j] = ' ';
		}
	}
}

// Main should be used to call the functions above to complete the tic-tac-toe game.
int main()
{
	const int row = 3;
	const int col = 3;
	char board[row][col] = { ' ' };

	

	cout << "Welcome to Tic-Tac-Toe" << endl;
	cout << "======================" << endl;
	InitializeBoard(board);
	PrintBoard(board);
	while (CheckWinner(board))
	{
		player1Turn(board);
		PrintBoard(board);
		player2Turn(board);
		PrintBoard(board);
	}

	
	return 0;
	system("PAUSE");
}

