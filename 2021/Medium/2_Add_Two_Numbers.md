```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:

    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* result = new ListNode(0);
        ListNode* location=result;
        
        string x = "";
        string y = "";
        while(l1!=nullptr)
        {
            x+=(to_string(l1->val));
            l1=l1->next;
        }
        while(l2!=nullptr)
        {
            y += (to_string(l2->val));
            l2=l2->next;
        }
        int i = 0;
        int j = 0;
        int carry=0;

        while(i<x.size() && j< y.size())
        {
            int sum = (x[i]-'0') + (y[i]-'0')+carry;
            carry= sum/10;
            sum%=10;
            ListNode* newNode = new ListNode(sum);
            result->next= newNode;
            result=result->next;
            cout<<sum<<'\n';
            
            ++i;
            ++j;                       
        }
        cout<<"dasd"<<carry<<'\n';

        while(j<y.size())  
        {
            int sum = (y[j]-'0') + carry;
            carry= sum/10;
            sum%=10;
            cout<<sum<<'\n';
            ListNode* newNode = new ListNode(sum);
            result->next= newNode;
            result=result->next;            
            ++j;   
        }
        while(i<x.size())  
        {
            int sum = (x[i]-'0') + carry;
            carry= sum/10;
            sum%=10;
            cout<<sum<<'\n';
            ListNode* newNode = new ListNode(sum);
            result->next= newNode;
            result=result->next;            
            ++i;   
        }
        if(carry!=0)
        {
            ListNode* newNode = new ListNode(1);
            result->next= newNode;
            result=result->next;  
        }
        return location->next;
    }
};
```