# File-Handling-Activity
#include <stdio.h>

int main ()
{
  FILE * fptr;
  int i,n;
  char str[100];
  char fname[20];
  char str1;
  
	printf("\n\n I used Online C compiler a text tab will appear :\n");
	printf(" Input the file location: ");
	scanf("%s",fname);		
    fptr = fopen(fname, "a"); 
    printf(" input how many lines to be append : ");
    scanf("%d", &n);
    printf(" The lines are : \n");  
    for(i = 0; i < n+1;i++)
    {
    fgets(str, sizeof str, stdin);
    fputs(str, fptr);
  }
  fclose (fptr);
	fptr = fopen (fname, "r");  
	printf("\n The content of the file %s is  :\n",fname);
	str1 = fgetc(fptr);
	while (str1 != EOF)
		{
			printf ("%c", str1);
			str1 = fgetc(fptr);
		}
    printf("\n\n");
    fclose (fptr);
  return 0;
}
