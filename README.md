#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<Windows.h>
#include<assert.h>

void gotoxy(int x,int y)
	{
		COORD pos;pos.X=x-1;pos.Y=y-1;
		SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), pos);
	}
int main()
{
	system("color f0");
	long i;
	char FileName[100];
	char hi[254000];
	FILE *in;
	system("C:\\Users\\xzh\\Desktop\\计科大作业\\01\\小视频\\极乐净土.wmv");//打开视频或音频文件
	Sleep(3000);
	for (i = 1; i <= 999; i++)
	{
		sprintf(FileName,"C:\\Users\\xzh\\Desktop\\字符画\\（0） (1)\\txtpicture\\(%ld).txt", i);
		in = fopen(FileName, "r");
		assert(in !=NULL);
		fread(hi, 1, 254000, in);
		printf("%s\n%d", hi, i);
		gotoxy(1, 1);
		Sleep(26);//等待27毫秒执行
		fclose(in);
	}
}
