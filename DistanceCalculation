#include <math.h>
#include <iostream>
#include <fstream>
using namespace std;

// Returns the calculation using distance forumla
double calcDistance(double x[], double y[], double z[])
{
	return sqrt(pow(x[0] - x[1], 2.0) + pow(y[0] - y[1], 2.0) + pow(z[0] - z[1], 2.0));
}

int main()
{
	// Read and writes to file
	ifstream fin("input.text");
	ofstream fout("output.txt");

	double x[2], y[2], z[2];

	// Store two sets of (x, y, x) points.
	for (int i = 0; i <= 20 && fin.good(); i++)
	{
		fin >> x[0] >> y[0] >> z[0] >> x[1] >> y[1] >> z[1];
		fout << calcDistance(x, y, z) << endl;
	}
return 0;
}
