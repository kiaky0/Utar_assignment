```C++
#include<iostream>
#include<iomanip>
#include<cmath>
using namespace std;

int main()
{
	int a0, a1, a2, a3, b0, b1, b2, delta, x1, x2, y1, y2, num_solution;
	double r, s, m, t;
	bool stop;

	cout << "Please Enter value of a3: ";
	cin >> a3;
	cout << endl;

	cout << "Please Enter value of a2: ";
	cin >> a2;
	cout << endl;

	cout << "Please Enter value of a1: ";
	cin >> a1;
	cout << endl;

	cout << "Please Enter value of a0: ";
	cin >> a0;
	cout << endl;

	if (a3 <= 0)
	{
		cout << "Invalid input";
		terminate;
	}

	b2 = 3 * a3;
	b1 = 2 * a2;
	b0 = a1;

	delta = (pow(b1, 2)) - (4 * b2 * b0);

	if (delta <= 0)
	{
		num_solution = 1;
		cout << num_solution;
	}
	else
	{
		x1 = ((-b1) - sqrt(delta)) / (2 * b2);
		x2 = ((-b1) - sqrt(delta)) / (2 * b2);
		y1 = ((a3)*pow(x1, 3)) + ((a2)*pow(x1, 2)) + ((a1) * (x1)) + a0;
		y2 = ((a3)*pow(x2, 3)) + ((a2)*pow(x2, 2)) + ((a1) * (x2)) + a0;

		if (y1 > 0 && y2 > 0)
		{
			num_solution = 1;
			cout << num_solution;
		}
		else if (y1 < 0 && y2 < 0)
		{
			num_solution = 1;
			cout << num_solution;
		}
		else if ((y1 == 0) || (y2 == 0))
		{
			num_solution = 2;
			cout << num_solution;
		}
		else if ((y1 == 0) && (y2 == 0))
		{
			cout << "Precision error";
			terminate;
		}
		else if ((y1 > 0) && (y2 < 0))
		{
			num_solution = 3;
			cout << num_solution;
		}
		else if ((y1 < 0) || (y2 > 0))
		{
			num_solution = 3;
			cout << num_solution;
		}
	}
	// new part

	if (num_solution = 1)
	{
		s = 1;
		while (((a3)*pow(s, 3)) + ((a2)*pow(s, 2)) + (a1 * s) + a0 <= 0)
		{
			s = 2 * s;
		}

		r = -1;
		while (((a3)*pow(r, 3)) + ((a2)*pow(r, 2)) + (a1 * r) + a0 <= 0)
		{
			r = 2 * r;
		}

		stop = false;
		while (stop = false)
		{
			m = (r + s) / 2;
			int y_m;
			y_m = ((a3)*pow(m, 3)) + ((a2)*pow(m, 2)) + ((a1)*m) + a0;

			if (y_m = 0 || sqrt(pow((s - r), 2)) < 0.00001);
			{
				t = m;
				cout << t;
				stop = true;
				continue;
			}
			do
			{
				s = m;
				return s;
			} while (y_m > 0);
			do
			{
				r = m;
				return r;
			} while (y_m < 0);


			//else
			//{
			//	if (y_m > 0)
			//	{
			//		s = m;
			//	}
			//	else if (y_m < 0)
			//	{
			//		r = m;
			//	}
			//	return 0;
			//}

			

		}
	}

}
```
