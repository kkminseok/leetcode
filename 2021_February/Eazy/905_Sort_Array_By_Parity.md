```c++
class Solution {
public:
    vector<int> sortArrayByParity(vector<int>& A) {
        for(size_t i=0, j = 0;i<A.size();++i)
        {
            if(A[i]%2 ==0)
            {
                swap(A[i],A[j++]);
            }
        }
        return A;
    }
};
```