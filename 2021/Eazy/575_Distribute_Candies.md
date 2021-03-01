```c++
class Solution {
public:
    int distributeCandies(vector<int>& candyType) {
        sort(candyType.begin(),candyType.end());
        int num = candyType.size()/2;
        int count = 1;
        for(size_t i =0;i<candyType.size()-1;++i)
        {
            if(candyType[i] != candyType[i+1])
                ++count;
        }
        return count > num ? num : count;
    }
};
```