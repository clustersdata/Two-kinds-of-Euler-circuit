# Two-kinds-of-Euler-circuit

Two kinds of Euler circuit

无向图：

#define M 45

int used[M][M],id[M];

void dfs(int u,vector<int> g[],vector<int> &vans){  //O（E^2）
  
  
	int j,w,v,t;
  
	for(j=g[u].size()-1;j>=0;j--){
  
		t=v=g[u][j]; w=u;
    
		if(v>w) swap(v,w);
    
		if(used[v][w]!=0){
    
			used[v][w]--;
      
			dfs(t,g,vans);
      
		}
    
	}
  
	vans.push_back(u);
  
}


有向图：

int n,m;

vector<int> g[M],vans;
  
void dfs(int u){   //O（E^2*log(e)）

	int j,t;
  
	Edg et;
  
	for(j=g[u].size()-1;j>=0;j--){
  
		et.u=u; et.v=g[u][j];
    
		if(mp[et]!=0){
    
			mp[et]--;
      
			dfs(g[u][j]);
      
		}
    
	}
  
	vans.push_back(u);
  
}

