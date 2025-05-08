#include<stdio.h> 
#include<unistd.h> 
#include<fcntl.h> 
#include<stdlib.h> 
int main() 
{ 

    char c ,fd,sz; 

    int fd1 = open("sample.txt", O_RDONLY, 0); 

    int fd2 = open("sample.txt", O_RDONLY, 0); 

    read(fd1, &c, 1); 

    read(fd2, &c, 1); 

    printf("c = %c\n", c); 

fd = open("foo.txt", O_WRONLY | O_CREAT | O_TRUNC, 0644); 

if (fd < 0) 
{ 

    perror("r1"); 

    exit(1); 
} 
 

sz = write(fd, "hello geeks\n", strlen("hello geeks\n")); 
 

printf("called write(% d, \"hello geeks\\n\", %d)."

    " It returned %d\n", fd, strlen("hello geeks\n"), sz); 
 
close(fd); 
}
