#include <iostream>
#include <string>
using namespace std;
int main()
{
	bool a[65];
	string name1, name2;
	int x1, y1,x2,y2,i;
	int j = 0;
	cout << "Players , tell me your names!" << endl;
	cin >> name1 >> name2;
	for (i = 0; i < 65; ++i)
	{
		a[i] = false;
	}
	for (i = 0; i < 33; ++i)
	{
		j = 0;
		if (i % 2 == 1)
		{
			cout << "Now it's " << name1<<"'s turn"<<endl;
		}
		else
		{
			cout << "Now it's " << name2<<"'s turn"<<endl;
		}
		cin >> x1 >> y1>>x2>>y2;
		a[x1*y1] = true;
		a[x2*y2] = true;
		for (int k = 1; k < 65; ++k)
		{
			if (a[k] == true && a[k + 1] == true && a[k - 1] == true && a[k + 8] == true && a[k - 8] == true)
			{
				++j;
			}
		}
		if (j == 64)
		{
			break;
		}
	}
	if (i % 2 == 1)
	{
		cout << "The winner is " << name1 << "!";
	}
	else
	{
		cout << "The winner is " << name2 << "!";
	}
	while (1);
}
