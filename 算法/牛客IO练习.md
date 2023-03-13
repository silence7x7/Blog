

```
 ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);
    
    和getchar()冲突
    用cin.get()替代即可
```

```
输入形式
a bb ccc这种形式可以while(cin >> s)
但逗号这种不行！
// a,bbb,cccc
// dddd
// bbbaa,aaa,aaaa,sss

while(getline(cin,line)){
        stringstream ss;
        ss<<line;
        string str;
        vector<string>v;
        while(getline(ss,str,',')){
            v.push_back(str);
        }
        sort(v.begin(),v.end());
        int n=v.size();
        for(int i=0;i<n;i++){
            if(i!=n-1) cout<<v[i]<<",";
            else cout<<v[i]<<endl;
        }
        v.clear();
    }
```

[牛客竞赛_ACM/NOI/CSP/CCPC/ICPC算法编程高难度练习赛_牛客竞赛OJ](https://ac.nowcoder.com/acm/contest/5657#question)
