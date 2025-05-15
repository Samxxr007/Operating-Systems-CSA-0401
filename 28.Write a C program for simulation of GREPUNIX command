#include <stdio.h>
#include <string.h>

int main(int argc, char *argv[]) {
    if (argc != 3) {
        printf("Usage: %s [string to search] [file name]\n", argv[0]);
        return 1;
    }

    char *search_string = argv[1];
    char *file_name = argv[2];

    FILE *fp = fopen(file_name, "r");
    if (fp == NULL) {
        printf("Error: Could not open file %s\n", file_name);
        return 1;
    }

    char line[256];
    int line_number = 1;
    while (fgets(line, sizeof(line), fp) != NULL) {
        if (strstr(line, search_string) != NULL) {
            printf("Line %d: %s", line_number, line);
        }
        line_number++;
    }

    fclose(fp);
    return 0;
}
