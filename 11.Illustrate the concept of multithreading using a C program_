#include <pthread.h>
int g = 0;
void *myThreadFun(void *vargp)
{
	int *myid = (int *)vargp;

	static int s = 0;

	++s; ++g;

	printf("Thread ID: %d, Static: %d, Global: %d\n", *myid, ++s, ++g);
}

int main()
{
	int i;
	pthread_t tid;

	for (i = 0; i < 3; i++)
		pthread_create(&tid, NULL, myThreadFun, (void *)&tid);

	pthread_exit(NULL);
}
