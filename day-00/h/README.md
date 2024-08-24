## H - Apple Division

There are 𝑛 apples with known weights. Your task is to divide the apples into two groups so that the difference between the weights of the groups is minimal.

### Input

The first input line has an integer 𝑛: the number of apples.

The next line has 𝑛 integers p<sub>1</sub> ,p<sub>2</sub> ,…,p<sub>n</sub> : the weight of each apple.

### Output

Print one integer: the minimum difference between the weights of the groups.

### Constraints

- 1 ≤ n ≤ 20
- 1 ≤ p<sub>i</sub> ≤ 10<sup>9</sup>

### Example

| Input            | Output         |
| ---------------- | -------------- |
| 5                | 1              |
| 3 2 7 4 1        |                |

Explanation: Group 1 has weights 2, 3 and 4 (total weight 9), and group 2 has weights 1 and 7 (total weight 8).

# Answer:

```c++

#include <iostream>

typedef unsigned long long number;

# define ABS(x) (x >= 0 ? x : -x)

number brute_force(
    number *diff,
    number *combination, int combination_index, int combination_size,
    const number* weights, int apple_index, const number weights_sum
)
{
    if (combination_index == combination_size)
    {
        number s1 = 0;
        for (int j = 0; j < combination_size; j++)
        {
            s1 += combination[j];
        }
        const number si = ABS(weights_sum - 2 * s1);
        if ((si < *diff) && (s1 < weights_sum))
            *diff = si;
    }
    else if (apple_index < 20)
    {
        combination[combination_index] = weights[apple_index];
        brute_force(diff, combination, combination_index + 1, combination_size, weights, apple_index + 1, weights_sum);
        brute_force(diff, combination, combination_index, combination_size, weights, apple_index + 1, weights_sum);
    }
    return (*diff);
}

long long minimum(const number* weights, const int apples_count, const number weights_sum)
{
    number diff = weights_sum;
    static number combination[20];
    int combination_size = 1;
    while (combination_size <= apples_count)
    {
        brute_force(&diff, combination, 0, combination_size, weights, 0, weights_sum);
        combination_size++;
    }
    return (diff);
}

int main(void)
{
    int apples_count = 0;
    number weights_sum = 0;
    static number weights[20];

    std::cin >> apples_count;
    for (int i = 0; i < apples_count; ++i)
    {
        std::cin >> weights[i];
        weights_sum += weights[i];
    }
    std::cout << minimum(weights, apples_count, weights_sum) << std::endl;
    return (0);
}
```
