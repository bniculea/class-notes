# Problema Iustin

## V1 cu strtok
/* strcpy example */
```c++
#define _CRT_SECURE_NO_WARNINGS
#include <iostream>
#include <string.h>

using namespace std;

int main()
{
	char text[251]= "copiii*sunt*la***zoo";

	//// Spargem pe cuvinte
	char* pch;
	pch = strtok(text, "*");
	while (pch != NULL) {
		for (int i = 0; i < strlen(pch) - 1;i++) {
			if (pch[i] == pch[i + 1]) {
				cout << pch[i] << pch[i + 1] << endl;
			}
		}
		pch = strtok(NULL, "*");
	}
	return 0;
}
```

## V2 Varianta cu loop simpla
```c++
/* strcpy example */
#include <iostream>
#include <string.h>

using namespace std;

int main()
{
	char text[251];

	cin.get(text, 251);

	//// Spargem pe cuvinte
	int i = 0;
	while (i <= strlen(text)) {
		if (text[i] == '*') {
			i++;
			continue;
		}
		if (text[i] == text[i + 1]) {
			cout << text[i] << text[i + 1] << endl;
		}
		i++;
	}
	return 0;
}
```