### building arrays
1. dynamic array:
```CS
string [ ] tableStr;// Table of string
```

2. static array:
```CS
int [ ] tablel = new int [5];
int [ ] table2 = {17,-9,4,3,57};
```

3. multi-dimension array:
```CS
int n=10;
int [ ][ ] table = new int [n+1][ ];
```

4. filling array values:
```CS
int n=10;
int [ ][ ] table = new int [n+1][ ];

int p=8;

for (int i=0; i<n+1; i++)
	table[i] = new int [p+1];
```

### building functions
1. simple static function:
```CS
bool test( ) {
	// .....
}
```

2. void functions:
```CS
void recomputel ( ){
	// .....
}
```

3. functions with parameters:
```CS
// Methods with parameters
int compute2 (byte a, byte b, int x ) {
	// .....
}
```

4. function with array as parameter:
```CS
static void Main(string[ ] args) {
}
```

### switch case:
```CS
namespace LogicalOperators
{
	class LogicalOperators
	{
		static void Main(string[] args)
		{
			int x = 13;
			switch (x)
			{
				case 11: Console.WriteLine("the number is 11");
					break;
				case 12: Console.WriteLine("the number is 12");
					break;
				default: Console.WriteLine("the number is: " + x);
					break;
			}
		}
	}
}
```

### data type ranges

![](cs_data_type_ranges.png)

### operators priority

![](../../static/operators_priority.png)