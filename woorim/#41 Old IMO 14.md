# #Old IMO 14 #

Graph Theory 를 도입하여 생각한다.

G의 minimal connected spanning subgraph T를 생각하자. 여기서의 minimal 이란 edge 수가 가장 적은 것을 말한다. 이 그래프에 cycle이 존재하면 사이클의 한 edge e를 T에서 없애도 T - e는 connected이고, T - e 에 의해서 G의 점들이 span되는 것도 똑같으므로, T - e 는 T 보다 작은 connected spanning subgraph 가 되어 T의 최소성에 모순이다. 따라서 T 에는 cycle이 없고, T는 Tree이다.

먼저 T 에 대해서 주어진 명제가 성립함을 보이자. Tree T 의 maximal length path 를 생각하자. maximal path 의 시점과 종점은
degree 1인 점이다. 1이 아니라면 종점(시점)과 연결되어 있는 또다른 점이 있는데, 이 점은 그 path 에 포함되지 않는 점이다. 포함된다면 T에
사이클이 존재하여 Tree 임에 모순이기 때문이다. 따라서, tree 의 종점을(시점을) 이 점과 연결함으로서 maximal path 를 연장시킬 수 있다는 모순을 얻는다.
즉 종점(시점) 이 degree 1 이 아니라는 처음의 가정이 잘못되었고 종점(시점) 은 degree 1 이다.

따라서 이 점들은 degree 1이기 때문에 점에 연결된 edge에 뭐가 있던간에 T에서의 명제의 성립 여부에 상관이 없다. maximal path를 따라서 시점에 연결된
변부터 1, 2, ...m(m은 이 path의 길이) 이렇게 차례로 라벨링하자. 그러면 이 path의 차수 2 이상의 점들에는, 그 점을 갖는 path의 두 변에 연속하는 두 자연수가 쓰여지므로 ( gcd( k, k+1 ) 은 항상 1 ) 다른 변들에 뭐가 쓰여지던간에 상관없이 명제가 성립한다.

한편 maximal path 를 T에서 제외하면 T 는 여러 트리들의 합집합으로 나누어진다. 따라서 각 트리에 대해서 m + 1 부터 해서 똑같은 과정을 반복하면 원하는
labeling 을 얻는다.

이제 이것을 G에 대해서 확장하자. 이 때 다음을 주목하자: T를 1, 2, ...t (t의 edge 개수) 로 라벨링하는 아까의 과정은 결국 조작을 반복할
때에 나오는 maximal path들을 연속하는 수들로라벨링하는 과정으로 분할되고, 그 순서가 굳이 (1,2, ..m ) (m+1, ...) ...(... t-1, t) 순서대로일 필요는 없다는 것이다. 또한 이것을 1, 2, ... k 라벨링에 편입시켜도 각 path 에 라벨링 되는 수들의 연속성만 만족하면 T에서 degree 2 이상이었던 점들은 G에서도 명제의 조건을 만족하게 된다.

즉 T에서 degree 가 1 이었던 점들만 생각하면 된다. 그런데, path 들의 순서를 맘대로 조작할 수 있으므로, T에서 degree 가 1 이었던 점을 하나 찾아,
그것이 G에서 degree 가 1 이 아니면, 그것을 갖는 변들 중 T에 속하지 않은 것 하나에 1을 부여하고 T에 속한 것에 2를 부여한 후 그것을 시점으로 포함했던
path 를 2부터 순서대로 라벨링한다. 이 라벨링 과정을 다른 T에서 degree 가 1 이었던 점을 찾아서 아까 라벨링이 끝났던 곳부터 반복하여 G의 명제를 성립시키는 라벨링을 얻는다. (1, 2 가 아니라 끝났던 곳부터 연속하는 두 수를 라벨링하면 된다)
