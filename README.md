#include <stdio.h>

int roll_one_die() {
    return rand() % 6 + 1; 
}

int main() {
    int i, die1, die2, sum;
    int count[13] = {0}; 
    int rolls = 1000000;

    srand(time(0)); 

    for (i = 0; i < rolls; i++) {
        die1 = roll_one_die();
        die2 = roll_one_die();
        sum = die1 + die2;
        count[sum]++;
    }

    printf("Sum\tCount\tProbability(%%)\n");
    for (i = 2; i <= 12; i++) {
        printf("%d\t%d\t%.2f%%\n", i, count[i], (count[i] * 100.0) / rolls);
    }

    return 0;
}# coc-project-ludo-dice-analyzer
