#include <stdio.h>
#include <sys/stat.h>
#include <unistd.h>

int main() 
{
    char file_path[] = "example.txt";

    chmod(file_path, S_IRUSR | S_IWUSR | S_IRGRP | S_IWGRP | S_IROTH);

    struct stat file_stat;
    stat(file_path, &file_stat);
    printf("File permissions: %o\n", file_stat.st_mode & 0777);

    printf("File owner: %d\n", file_stat.st_uid);

    printf("File group: %d\n", file_stat.st_gid);

    return 0;
}
