#include <stdio.h>
#include <unistd.h>
#include <fcntl.h>
#include <sys/stat.h>

int main() {
    int fd; // file descriptor
    char *file_path = "example.txt"; // path of file
    char buffer[100]; // buffer for reading/writing file
    int n;

    // create a new file with read and write permissions
    fd = open(file_path, O_CREAT | O_RDWR, S_IRUSR | S_IWUSR);

    // write to the file
    write(fd, "This is an example file.\n", 24);

    // move the file pointer to the beginning of the file
    lseek(fd, 0, SEEK_SET);

    // read from the file
    n = read(fd, buffer, 100);
    buffer[n] = '\0';
    printf("File content: %s\n", buffer);

    // close the file
    close(fd);

    // remove the file
    unlink(file_path);

    return 0;
}
