class Solution {
public:
    double maxProbability(int n, vector<vector<int>>& edges, vector<double>& succProb, int start, int end) {
        vector<pair<int, double>> adj[n];
        for(int i=0; i<edges.size(); ++i){
            adj[edges[i][0]].push_back({edges[i][1], succProb[i]});
            adj[edges[i][1]].push_back({edges[i][0], succProb[i]});
        }
        double prob[n];
        for(int i=0; i<n; ++i){
            prob[i] = 0.0;
        }
        dijkastra(adj, prob, start);
        return prob[end];
    }
    void dijkastra(vector<pair<int, double>> adj[], double prob[], int u){
        prob[u] = 1.0;
        priority_queue<pair<double, int>> pq;
        pq.push({1.0, u});
        while(!pq.empty()){
            u = pq.top().second;
            pq.pop();
            for(auto x:adj[u]){
                int v = x.first;
                double p = x.second;
                if(prob[v] < (p*prob[u])){
                    prob[v] = p*prob[u];
                    pq.push({prob[v], v});
                }
            }
        }
    }  
};
