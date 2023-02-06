#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp;
    char filename[] = "example.txt";
    char buffer[255];

    // Create a new file
    fp = fopen(filename, "w");
    if (fp == NULL) {
        printf("Could not create file.\n");
        exit(1);
    }
    fprintf(fp, "This is a new file.\n");
    fclose(fp);

    // Open and read the file
    fp = fopen(filename, "r");
    if (fp == NULL) {
        printf("Could not open file.\n");
        exit(1);
    }
    fgets(buffer, 255, fp);
    printf("Content of the file: %s\n", buffer);
    fclose(fp);

    // Open and write to the file
    fp = fopen(filename, "a");
    if (fp == NULL) {
        printf("Could not open file.\n");
        exit(1);
    }
    fprintf(fp, "This is an added line.\n");
    fclose(fp);

    // Open and read the file again
    fp = fopen(filename, "r");
    if (fp == NULL) {
        printf("Could not open file.\n");
        exit(1);
    }
    while (fgets(buffer, 255, fp) != NULL) {
        printf("Content of the file: %s\n", buffer);
    }
    fclose(fp);

    return 0;
}
