---
tags:
  - cpp
  - cpp_sequences
address: Vector container implementation
---
to define vector inside function we use this:
```cpp
#include <iostream>
#include <vector>

std::vector<int> buildVector(int numberOfOnes, int numberOfTwos)
{
    std::vector<int> myVector(numberOfOnes+numberOfTwos);
    std::fill_n(myVector.begin(), numberOfOnes, 1);
    std::fill_n(myVector.begin() + numberOfOnes, numberOfTwos, 2);

    return myVector;
}

// build vector with twos and ones
std::vector<int> myVector = buildVector(ones, twos);
```