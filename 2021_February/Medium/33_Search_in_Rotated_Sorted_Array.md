```c++
class Solution {
public:
    int search(vector<int>& nums, int target) {
        if(nums.size()==1)
            return nums[0]==target ? 0 : -1;
        
        
        int start =0;
        int end = nums.size()-1;
        int max = nums[end];
        //끝에서부터 탐색
        if(target<=nums[end])
        {
            while(end>start && nums[end]>target)
            {
                cout<<end<<'\n';
                --end;
            }
            if(nums[end]==target)
                return end;
            else
                return -1;
        }
        else
        {
            while(start<end &&nums[start]<target)
            {
                ++start;
            }
            if(nums[start]==target)
                return start;
            else
                return -1;
        }
        
        return -1;
    }
};
```