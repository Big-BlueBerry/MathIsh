# #Old IMO 14 #

Graph Theory 를 도입하여 생각한다.

G의 connnected spanning subgraph 에 대해서 명제가 성립하면 자명하게 G에서도 성립하므로, G의 minimal connected spanning subgraph를
생각하자. 이 그래프에 사이클이 존재하면 사이클의 한 edge를 없애도 G는 연결되어 있고 점들이 span되는 것도 똑같으므로, 최소성에 의해
이 그래프는 사이클을 포함하지 않고, 따라서 tree 이다.

즉 Tree 에 대해서만 명제가 성립함을 보이면 된다. 먼저, Tree T 의 maximal path 를 생각하자. maximal path 의 시점과 종점은
degree 1인 점이다. 아니라면 그 점과 연결된 점이 있고, 이 점은 path 에 포함되지 않는다. 포함된다면 사이클을 이루가 때문이다. 따라서 
maximal path 를 연장시킬 수 있다는 모순을 얻는다.

따라서 이 점들은 차수 1이기 때문에 점에 연결된 edge에 뭐가 있던간에 명제의 성립 여부에 상관이 없다. maximal path를 따라서 시점에 연결된
변부터 1, 2, ...m(m은 이 경로의 길이) 이렇게 차례로 라벨링하자. 그러면 이 path 차수 2 이상의 점들에는, 그 점을 갖는 path의 두 변에 연속하는 두 자연수가
쓰여지므로 ( gcd( k, k+1 ) 은 항상 1 ) 다른 변들에 뭐가 쓰여지던간에 상관없다.

maximal path 를 T에서 제외하면 T 는 여러 트리들의 합집합으로 나누어지고, 따라서 각 트리에 대해서 m + 1 부터 해서 똑같은 과정을 반복하면 원하는
labeling 을 얻는다.
