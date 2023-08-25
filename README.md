# Determine
判断大小端
方法一
#include <stdio.h>
int main()
{
	int a = 1;
	char* p = (char*)&a;
	if (*p == 1) {
		printf("小端\n");
	}
	else {
		printf("大端\n");
	}
	return 0;
}


方法二
#include <stdio.h>
int check_sys(int a) {
	char* p = (char*)&a;
	return *p;
}
int main()
{
	int a = 1;
	int ret = check_sys(a);
	if (ret == 1) {
		printf("小端");
	}
	else {
		printf("大端");
	}
}

方法三
#include <stdio.h>
int check_sys(int a) {
	return *(char*)&a;
}
int main()
{
	int a = 1;
	int ret = check_sys(a);
	if (ret == 1) {
		printf("小端");
	}
	else {
		printf("大端");
	}
}
