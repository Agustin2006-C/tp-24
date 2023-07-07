

#include <iostream>

const int MAX_SIZE = 25000;

int pedirConjunto(int vector[]);
int obtenerModa(int vector[], int vectorSize);

int main()
{
	int vector[MAX_SIZE] = { 0 };
	int vectorSize = 0;
	int modaEnConjunto = 0;

	vectorSize = pedirConjunto(vector);
	modaEnConjunto = obtenerModa(vector, vectorSize);

	std::cout << "\nLa moda es: " << modaEnConjunto;
}

int pedirConjunto(int vector[])
{
	int newVectorSize = 0;

	std::cout << "\nIngrese el tamano del conjunto: ";
	std::cin >> newVectorSize;

	if (newVectorSize > MAX_SIZE)
	{
		std::cout << "\nEl conjunto que desea introducir es muy grande";
		newVectorSize = 0;
	}

	for (int i = 0; i < newVectorSize; i++)
	{
		std::cout << "\nIngrese el valor N" << i + 1 << ": ";
		std::cin >> vector[i];
	}

	return newVectorSize;
}

int obtenerModa(int vector[], int vectorSize)
{
	int moda = 0;
	int modaCount = 0;

	for (int i = 0; i < vectorSize; i++)
	{
		int newModa = vector[i];
		int newModaCount = 0;

		for (int j = 0; j < vectorSize; j++)
		{
			if (newModa == vector[j])
			{
				newModaCount++;
			}
		}

		if (newModaCount > modaCount)
		{
			moda = newModa;
   	modaCount = newModaCount;
		}
	}

	return moda;
}
