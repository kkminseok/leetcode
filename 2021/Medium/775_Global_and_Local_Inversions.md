**c++**

```c++
class Solution {
public:
    bool isIdealPermutation(vector<int>& A) {
        for(int i =0;i<A.size();++i){
            if(A[i] == i || A[i] ==i+1 || A[i]==i-1)     continue;
            else return false;
        }
        return true;
    }
};
```