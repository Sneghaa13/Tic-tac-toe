#include <stdio.h>
#include <stdbool.h>

void print_board(char board[3][3]) {
    printf("\n");
    printf(" %c | %c | %c\n", board[0][0], board[0][1], board[0][2]);
    printf("-----------\n");
    printf(" %c | %c | %c\n", board[1][0], board[1][1], board[1][2]);
    printf("-----------\n");
    printf(" %c | %c | %c\n", board[2][0], board[2][1], board[2][2]);
    printf("\n");
}

bool check_win(char board[3][3], char mark) {
    for (int i = 0; i < 3; i++) {
        if ((board[i][0] == mark && board[i][1] == mark && board[i][2] == mark) ||
            (board[0][i] == mark && board[1][i] == mark && board[2][i] == mark)) {
            return true;
        }
    }
    if ((board[0][0] == mark && board[1][1] == mark && board[2][2] == mark) ||
        (board[0][2] == mark && board[1][1] == mark && board[2][0] == mark)) {
        return true;
    }
    return false;
}

bool check_tie(char board[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j] == ' ') {
                return false;
            }
        }
    }
    return true;
}

int main() {
    char board[3][3];
    int row, col;
    int player = 1;
    char mark;

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            board[i][j] = ' ';
        }
    }

    printf("Welcome to Tic Tac Toe!\n");

    while (true) {
        print_board(board);
        printf("Player %d, enter row (0-2) and column (0-2) to place your mark: ", player);
        scanf("%d %d", &row, &col);

        if (row >= 0 && row < 3 && col >= 0 && col < 3 && board[row][col] == ' ') {
            mark = (player == 1) ? 'X' : 'O';
            board[row][col] = mark;

            if (check_win(board, mark)) {
                printf("Player %d wins!\n", player);
                break;
            }

            if (check_tie(board)) {
                printf("It's a tie!\n");
                break;
            }

            player = (player == 1) ? 2 : 1;
        } else {
            printf("Invalid move. Please try again.\n");
        }
    }

    print_board(board);

    return 0;
}
