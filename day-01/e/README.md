# E - i3ada

You are given a DNA sequence: a string consisting of characters A, C, G, and T. Your task is to find the longest repetition in the sequence. This is a maximum-length substring containing only one type of character.

## Input

The only input line contains a string of 𝑛 characters.

## Output

Print one integer: the length of the longest repetition.

## Constraints

- 1 ≤ n ≤10<sup>6</sup>

## Example

| Input            | Output         |
| ---------------- | -------------- |
| ATTCGGGA         | 3              |

# Answer:

```c++

/*
	https://github.com/Abdelmathin/cpc-bootcamp/tree/main/day-01/e
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

# include <iostream>

int main(void)
{
	int L = 0;
	int A = 0;
	int C = 0;
	int G = 0;
	int T = 0;

	std::string dna;
	std::cin >> dna;
	for (size_t i = 0; i < dna.length(); ++i)
	{
		if (dna[i] == 'A')
		{
			if (i < 1 || (dna[i - 1] != 'A'))
				A = 0;
			A += 1;
		}
		if (dna[i] == 'C')
		{
			if (i < 1 || (dna[i - 1] != 'C'))
				C = 0;
			C += 1;
		}
		if (dna[i] == 'G')
		{
			if (i < 1 || (dna[i - 1] != 'G'))
				G = 0;
			G += 1;
		}
		if (dna[i] == 'T')
		{
			if (i < 1 || (dna[i - 1] != 'T'))
				T = 0;
			T += 1;
		}
		if (L < A)
			L = A;
		if (L < C)
			L = C;
		if (L < G)
			L = G;
		if (L < T)
			L = T;
	}
	std::cout << L << std::endl;
	return (0);
}
```
