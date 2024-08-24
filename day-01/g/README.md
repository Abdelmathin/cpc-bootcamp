# G - Clock

# Answer:

```c++
# include <iostream>
# include <sstream>

/*
	c++ -Wall -Wextra -Werror main.cpp -o a.out && ./a.out
*/

std::string add_minutes(std::string time, int minutes)
{
	int in_minutes = 0;
	int hour   = 10 * (time[0] - '0') + (time[1] - '0');
	int minute = 10 * (time[3] - '0') + (time[4] - '0');
	in_minutes = (60 * hour + minute + minutes) % 1440;
	hour   = (in_minutes / 60);
	minute = (in_minutes % 60);
	std::stringstream ss(""); 
	if (hour < 10)
		ss << "0";
	ss << hour << ":";
	if (minute < 10)
		ss << "0";
	ss << minute;
	return (ss.str());
}

int is_palin(std::string time)
{
	return ((time[0] == time[4]) && (time[1] == time[3]));
}

int main(void)
{
	int t = 0;
	std::cin >> t;
	for (int i = 0; i < t; ++i)
	{
		std::string time;
		int s = 0;
		std::cin >> time;
		std::cin >> s;
		const std::string init_time = time;
		int count = 0;
		do
		{
			count += is_palin(time);
			time = add_minutes(time, s);
		} while (init_time != time);
		std::cout << count << std::endl;
	}
	return (0);
}
```
