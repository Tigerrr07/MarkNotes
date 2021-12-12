使用vector初始化得到拷贝不成功（未解决）
```C++
loadData(char *buffer, ll size, vector<edge> &G);

vector<edge> G;
loadData(buffer, size, G);
cout << G.size() << endl;   // 显示未0
vector<edge> G = GT;

```

改用动态数组+memcpy的形式来进行拷贝
```C++
edge *G = new edge[num_arcs];
loadData(char *buffer, ll size, edge *G);
edge *GT = new edge[num_arcs];
memecpy(GT, G, sizeof(edge)*num_arcs);
delete [] G;
delete [] GT;
````


