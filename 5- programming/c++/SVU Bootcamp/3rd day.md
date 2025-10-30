### Ordinary Bitmask convertor
```cpp
string intToBin(int n) {
    if (n == 0) {
        return "";
    }
    if (n % 2) {
        return intToBin(n/2) + "1";
    } else {
        return intToBin(n/2) + "0";
    }
}
```
### Reverse Bitmask
take the binary number, then reverse each 0 with 1 and each 1 with 0, then add 1.
### Bitmask operation
1. And
2. OR
3. XOR: when two bits are different it returns 1, when two bits are same it returns 0.
4. Not: is same as `Reverse Bitmask`, but we don't add one.
### Bits shifts
##### 1. right shift:
is same as dividing by 2
```cpp
int main() {
    int x, n;
    cin >> n;

    x = n>>1;

    cout << x << endl;

    return 0;
}

```
##### 2. left shift:
is as multiplication with 2
```cpp
int main() {
    int x, n;
    cin >> n;

    x = n<<1;

    cout << x << endl;

    return 0;
}
```

`note:` Bitmask can be used instead of original power when working with base of 2:
```cpp
Pow(2, 10) == BitmaskShift(1, 10);
```

`quest`: how to know if a number is one of 2 expotional
```cpp

```
