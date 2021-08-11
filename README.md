# profit-earn-via-stack
class Solution{
    public:
        int profit(vector<int>V)
    {
        vector<int> v2;
        int sum=0;
        int n=V.size();
        stack<int> s1;
        s1.push(V[n-1]);
        v2.push_back(V[n-1]);
        for(int i=n-2;i>=0;i--)
        {
            while(s1.empty()==false and s1.top()<V[i])
            {
                s1.pop();
            }
            int ig=(s1.empty())? V[i]:(s1.top()-V[i]);
            v2.push_back(ig);
            s1.push(V[i]);
        }
        for(int i=0;i<v2.size();i++)
        {
            sum+=v2[i];
        }
        return sum;
    }
};
