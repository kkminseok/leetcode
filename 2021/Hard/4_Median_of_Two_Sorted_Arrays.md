```c++
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        int n = nums1.size();
        int m = nums2.size();
        int mid = (n+m)/2;
        bool check = (n+m)%2;
        double result = 0;
        vector<int> vec;
        int i = 0;
        int j = 0;
        while(i<n && j<m)
        {
            if(vec.size()==mid+1)
                break;
            if(nums1[i] < nums2[j])
                vec.push_back(nums1[i++]);
            else
                vec.push_back(nums2[j++]);
        }
        int tmp = i > m ? j : i;
        while(i<n&& vec.size()!=mid+1)
        {
            vec.push_back(nums1[i++]);
        }
        while(j<m&&  vec.size()!=mid+1)
            vec.push_back(nums2[j++]);
        if(!check)
        {
            return (vec[mid] + vec[mid-1])/2.0;
        }
        return vec[mid];
    }
};
```