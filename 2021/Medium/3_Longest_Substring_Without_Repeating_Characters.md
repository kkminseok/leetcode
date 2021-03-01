```c++
class Solution {
public:
    bool checkalpha[128]={false,};
    int lengthOfLongestSubstring(string s) {
        int count = 0;
        int result = 0;
        for(size_t i=0;i<s.length();++i)
        {
            memset(checkalpha,false,sizeof(checkalpha));
            string temp = "";
            temp+=s[i];
            count = 1;
            checkalpha[s[i]]=true;
            for(size_t j =i+1;j<s.length();++j)
            {
                if(checkalpha[s[j]]==true)
                    break;
                else
                {
                    temp+=s[j];
                    ++count;
                    checkalpha[s[j]]=true;
                }
            }
            result = max(result,count);
        }
        return result;
    }
};
```