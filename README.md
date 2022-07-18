# Binary_Max1s
#include <bits/stdc++.h>

using namespace std;

string ltrim(const string &);
string rtrim(const string &);



int main()
{       int arr[100];
        int maxNum=0;
        int sum=0;
        int i=0;

    string n_temp;
    getline(cin, n_temp);

    int n = stoi(ltrim(rtrim(n_temp)));
    
        while(n>0){
        arr[i]=n%2;
        n=n/2;
        i++;
        }

        for(int j=i-1;j>=0;j--){

                if(arr[j]==1){
                    sum++;
                if(maxNum<sum){
                    maxNum=sum;
                }
                }
                else {sum=0;}


}
        cout<<maxNum;

    return 0;
}

string ltrim(const string &str) {
    string s(str);

    s.erase(
        s.begin(),
        find_if(s.begin(), s.end(), not1(ptr_fun<int, int>(isspace)))
    );

    return s;
}

string rtrim(const string &str) {
    string s(str);

    s.erase(
        find_if(s.rbegin(), s.rend(), not1(ptr_fun<int, int>(isspace))).base(),
        s.end()
    );

    return s;
}
