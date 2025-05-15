#include <stdio.h>
#include <stdlib.h>

#define MAX_RECORDS 100

struct Record {
    int id;
    char data[100];
};

struct File {
    struct Record records[MAX_RECORDS];
    int numRecords;
};

void initFile(struct File *file) {
    file->numRecords = 0;
}

void addRecord(struct File *file, struct Record record) {
    file->records[file->numRecords] = record;
    file->numRecords++;
}

void readRecord(struct File *file, int recordId) {
    for (int i = 0; i < file->numRecords; i++) {
        struct Record record = file->records[i];
        printf("Record %d: %s\n", record.id, record.data);
        if (record.id == recordId) {
            printf("Found record with id %d: %s\n", recordId, record.data);
            break;
        }
    }
}

int main() {
    struct File file;
    initFile(&file);

    struct Record record1 = {.id = 1, .data = "Record 1 data"};
    struct Record record2 = {.id = 2, .data = "Record 2 data"};
    struct Record record3 = {.id = 3, .data = "Record 3 data"};

    addRecord(&file, record1);
    addRecord(&file, record2);
    addRecord(&file, record3);

    readRecord(&file, 2);

    return 0;
}
