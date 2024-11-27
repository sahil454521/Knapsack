# Knapsack
#include <stdio.h>


void knapsack(int m, int n, int p[], int w[]) {
    float x[n]; 
    int freecapacity = m; 
    int i;

  
    for (i = 0; i < n; i++) {
        x[i] = 0.0;
    }

    for (i = 0; i < n; i++) {
        if (w[i] > freecapacity) {
            break;
        }
        x[i] = 1.0; 
        freecapacity -= w[i];
    }

  
    if (i < n) {
        x[i] = (float)freecapacity / w[i]; 
    }


    printf("Fractions of items in the knapsack:\n");
    for (i = 0; i < n; i++) {
        printf("Item %d: %f\n", i + 1, x[i]);
    }
}

int main() {
    int m = 50; 
    int n = 3;  
    int p[] = {60, 100, 120}; 
    int w[] = {10, 20, 30};   

    knapsack(m, n, p, w);

    return 0;
}
