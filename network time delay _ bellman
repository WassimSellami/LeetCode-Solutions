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
        bellman(adj, dis, k-1, n);
        int ma = dis[0];
        for(auto x: dis){
            ma = max(ma, x);
             if(x == INT_MAX){
                 return -1;
            }  
        }
        return ma;
    }
    void bellman(vector<pair<int, int>> adj[], int dis[], int u, int n){
        dis[u] = 0;
        for(int i=0; i<n-1; ++i){
            bool updated = false;
            for(int u=0; u<n; ++u){
                for(auto p: adj[u]){
                    int v = p.first;
                    int w = p.second;
                    if(dis[u] != INT_MAX){
                        if(dis[u]+w < dis[v]){
                            dis[v] = dis[u]+w;
                            updated = true;
                        }
                    }
                }
            }
            if(!updated){
                break;
            }
        }
    }
};
