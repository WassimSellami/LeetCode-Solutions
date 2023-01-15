class Solution {
public:
    int networkDelayTime(vector<vector<int>>& times, int n, int k) {
        int dis[n];
        for(int i=0; i<n; ++i){
            dis[i] = INT_MAX;
        }
        vector<pair<int, int>> adj[n];
        for(int i=0; i<times.size(); ++i){
            adj[times[i][0]-1].push_back({times[i][1]-1, times[i][2]});
        }
        dijkastra(adj, dis, k-1);
        int ma = dis[0];
        for(auto x: dis){
            ma = max(ma, x);
             if(x == INT_MAX){
                 return -1;
            }
            
        }
        return ma;
    }
    void dijkastra(vector<pair<int, int>> adj[], int dis[], int u){
        dis[u] = 0;
        priority_queue<pair<int, int>> q;
        // priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> q;
        q.push({0, u});
        while(!q.empty()){
            int u = q.top().second;
            q.pop();
            for(int i=0; i<adj[u].size(); ++i){
                int v = adj[u][i].first;
                int w = adj[u][i].second;
                if(dis[u]+w < dis[v] ){
                    dis[v] = dis[u]+w;
                    q.push({dis[v], v});
                }
            }
        }
    }
};
