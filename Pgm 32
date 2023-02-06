#include <stdio.h> 
#include <stdlib.h> 

#define MAX_PAGES 100 

int page_faults = 0; 

void printPages(int pages[], int n) 
{ 
    int i; 
    for (i = 0; i < n; i++) 
        printf("%d ", pages[i]); 
} 

int search(int pages[], int n, int x) 
{ 
    int i; 
    for (i = 0; i < n; i++) 
        if (pages[i] == x) 
            return i; 
    return -1; 
} 

void leastRecentlyUsed(int pages[], int n, int capacity) 
{ 
    int i, j = 0; 
    for (i = 0; i < n; i++) { 
        int x = pages[i]; 
        if (search(pages, j, x) == -1) { 
            page_faults++; 
            if (j < capacity) 
                pages[j++] = x; 
            else { 
                int k; 
                for (k = 0; k < j - 1; k++) 
                    pages[k] = pages[k + 1]; 
                pages[j - 1] = x; 
            } 
        } 
    } 
    printf("Pages: "); 
    printPages(pages, j); 
} 

int main() 
{ 
    int pages[] = {7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2}; 
    int n = sizeof(pages) / sizeof(pages[0]); 
    int capacity = 4; 

    leastRecentlyUsed(pages, n, capacity); 

    printf("\nTotal page faults: %d\n", page_faults); 

    return 0; 
}
