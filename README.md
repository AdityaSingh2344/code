#include <stdio.h>
#include<stdlib.h>
int main() {
    char pc, cc;
    int cnum;
    do {
        printf("Enter your choice (R for rock, P for paper, S for scissors): ");
        scanf(" %c", &pc);
        if (pc != 'R' && pc != 'P' && pc != 'S') {
            printf("Invalid choice. Try again.\n");
            continue;
        }
        cnum = rand() % 3;
        switch (cnum) {
            case 0:
                cc = 'R';
                break;
            case 1:
                cc = 'P';
                break;
            case 2:
                cc = 'S';
                break;
        }
        printf("Computer's choice: %c\n", cc);
        if (pc == cc) {
            printf("It's a tie!\n");
        } else if (pc == 'R' && cc == 'S'
                   || pc == 'P' && cc == 'R'
                   || pc == 'S' && cc == 'P') {
            printf("You win!\n");
        } else {
            printf("You lose!\n");
        }
        printf("Do you want to play again? (Y/N): ");
        scanf(" %c", &pc);
    } while (pc == 'Y');
    return 0;
}
