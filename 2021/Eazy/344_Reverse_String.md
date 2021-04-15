**c++**

```c++
class Solution {
public:
    void reverseString(vector<char>& s) {
        auto left = 0;
        auto right = s.size()-1;
        while(left<right)
            swap(s[left++],s[right--]);
    }
};
```