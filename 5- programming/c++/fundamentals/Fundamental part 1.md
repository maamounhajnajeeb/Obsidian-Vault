---
tags:
  - cpp
  - cp
title: C++ fundamentals
type: permanent
date: 2025-12-05
---
1. unsigned variable:
	when we use unsigned variables, the storage range turned from: (-2^(n-1), 2^(n-1) - 1) to: (0, 2^(n) - 1)

	code:
	```cpp
	unsigned int x = 2;
	```

2. how to print variable location in memory:
	```cpp
	int main()
	{
	    unsigned int x = 2;
	    cout << &x;  // result: 0x61fe1c
	
	    return 0;
	}
	```

3. how to view variable size in memory:
	```cpp
	int main()
	{
	    unsigned int x = 2;
	    cout << sizeof(x);  // result: 4
	
	    return 0;
	}
	```

4. define custom type:
	```cpp
	typedef unsigned int UInt;
	
	int main()
	{
	    UInt x = 2;
	    cout << x;
	
	    return 0;
	}
	```

5. automatic types:
	```cpp
	int main()
	{
	    auto x = 2;
	    return 0;
	}
	```

6. how to define types depending on other types:
	```cpp
	int main()
	{
	    auto x = 2;
	    decltype(x) y = 5;
	
	    return 0;
	}
	```

7. define structure:
	structures are useful data containers
	```cpp
	struct Info {
		string name;
	    int age;
		float GPA;
	};

	int main()
	{
	    struct Info maamounInfo;
	
	    maamounInfo.name = "Maamoun Haj Najeeb";
	    maamounInfo.age = 25;
	    maamounInfo.GPA = 5.0;
	
	    return 0;
	}
	```

	in another (better) way (using typedef):
```cpp
	typedef struct {
		string name;
	    int age;
		float GPA;
	} Info;

	int main()
	{
	    Info maamounInfo;
	
	    maamounInfo.name = "Maamoun Haj Najeeb";
	    maamounInfo.age = 25;
	    maamounInfo.GPA = 5.0;
	
	    return 0;
	}
	```

8. array length
```cpp
	int main()
	{
	    int numbers[5] = {5, 6, 4, 7, 8};
	    int arrayLength = sizeof(numbers) / sizeof(numbers[0]);
	
	    cout << arrayLength << endl;
	
	    return 0;
	}
	```

9. string length
```cpp
int main()
{
	string word = "Hello, World!";
	cout << word.size() << endl;
}
```
