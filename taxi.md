# c-problems

// Link - https://codeforces.com/contest/158/problem/B


#include <bits/stdc++.h>
 
using namespace std;
 
int main()
{
     vector<int> v;
     int n,x;
     cin>>n;
     while(n){
          cin>>x;
          v.push_back(x);
          n--;
     }
     sort(v.begin(),v.end());
 
     vector<int>::iterator upper1,upper2,upper3,upper4;
     
     upper1=upper_bound(v.begin(),v.end(),1);
     
     int up1 = (upper1-v.begin());
     
     upper2 = upper_bound(upper1,v.end(),2);
     
     int up2 = (upper2-upper1);
     
     upper3 = upper_bound(upper2,v.end(),3);
     
     int up3 =(upper3-upper2);
     
     upper4 = upper_bound(upper3,v.end(),4);
     
     int up4 =(upper4-upper3);
     
     
     int remaining1=0,remaining2=0,taxi=0;
     if(up3>up1)
          up1=0;
     else
          up1=up1-up3;
     remaining1=up1%4;
     remaining2=up2%2;
     taxi = taxi + up1/4 + up2/2 + up3 + up4;
     if(remaining1+remaining2==4)
     taxi=taxi+2;
     else if(remaining1!= 0 || remaining2!= 0)
          taxi=taxi+1;
       cout<<taxi;
 
    return 0;
}
