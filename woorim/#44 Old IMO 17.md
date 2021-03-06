# #Old IMO 17 #

Graph Theory를 도입하여 생각하자.

우선 각 집합 A_i 들로 2n + 1개의 정점을 구성하고, 두 정점은 공통원소가 있을 때에 간선으로 연결된다고 하자. 간선 위에는 그 공통원소를
labeling 한다. 이 그래프를 G 라고 명명한다.

그러면, 조건 (b) 에 따라서, 임의의 서로다른 두 정점은 연결되어 있어야 하고, 모든 간선 위에는 단 하나의 공통원소가 labeing 되어 있어야 한다.
고로 G는 완전그래프이다. 그런데 조건 (c) 에 따라서, G의 모든 간선들에 labeling 된 원소들의 총집합은 B를 포함한다. 즉, B의 모든 원소는 어딘가에
labeling 된다. 즉 그래프의 간선 개수 = 2n(2n+1)/2 = n(2n+1) >= |B|.

그런데, 다시 조건 (b) 로 돌아가자. 각 A_i 가 2n 개의 원소를 가지고 서로다른 두 A_i, A_j 는 하나의 공통원소만 가지므로, 공통원소를 최대로 겹치지
않게 할 때에 B의 원소 수가 최소가 된다. 이때의 모든 A_i들의 합집합의 원소 개수는 (이 합집합은 (c) 에 의해 B와 같다) 2n + (2n-1) + ...+ 1 = 
2n(2n+1)/2 = n(2n+1). 즉 n(2n+1) <= |B|.

두 논의를 종합하면 결국 n(2n+1) = |B| 이다. 따라서 G에서 B의 모든 원소가 단 한번씩만 labeling 된다.

이제, 그래프의 labeling된 원소들을 0과 1로 덧칠해서, 각 A_i 들에 연결된 2n개의 간선 중 n개에 0, n개에 1 이 labeling 되어 있다고 가정한다.
여기서 1 labeling 된 간선들을 모두 없앤 그래프를 생각하자. 이 그래프의 간선의 개수는, 당연히 (2n+1) * n/2 로 결정된다. 
(그래프의 간선 개수의 공식은 degree 의 총합/2 인데 각 점은 모두 n 개의 0 labeling 된 간선만 가지므로)

이때 n이 홀수이면 간선의 개수가 정수가 아니게 되어 모순이므로, 그러한 덧칠이 가능하려면 일단 짝수여야 한다.
이제 반대로 짝수이면 그런 덧칠이 가능함을 보여서 문제를 마무리하자. n = 2m 으로 놓자.

먼저, 각 A_i 들의 0 과 1 의 할당량은 각각 2m 씩이다. 먼저 한 점에 연결된 간선에 아무렇게나 1을 2m개, 0 을 2m 개 칠한다.
G에서 그 점과 (그 점과 연결된 모든 간선집합) 을 삭제하면 차수가 하나 낮은 완전그래프가 된다.
(완전그래프에서 임의의 점집합과 딸린 간선집합을 없애도 완전그래프이다) 이제 4m개의 점들이 남는데, 이 중 2m 개는 1의 할당량 하나를 소비했고
다른 2m 개는 0 의 할당량 하나를 소비한 상태이다. 이를 X, Y 라는 집합으로 명명하자..

X

1 할당량 : 2m 

0 할당량 : 2m -1

Y

1 할당량 : 2m - 1

0 할당량 : 2m

이제, X에서 두 점, Y에서 두 점을 뽑자. 그리고 다음과 같이 칠한다:

1) X애서 뽑힌 점은 다른 X의 점들과 모두 1 이 칠해진 간선으로 연결되고, Y에서 뽑힌 점은 다른 Y의 점들과 모두 0 이 칠해진 간선으로 연결된다.
(같이 뽑힌 점도 포함)

2) X에서 뽑힌 첫번째 점은 Y에서 뽑힌 첫번째 점과 1으로, Y에서 뽑힌 두번째 점과는 0으로 연결된다.

3) X에서 뽑힌 두번째 점은 Y에서 뽑힌 첫번째 점과 0으로, Y에서 뽑힌 두번째 점과는 1으로 연결된다.

이제 이 네 점과 딸린 간선집합을 다시 삭제한다. 그러면 위의 논의에 따라서 남은 완전그래프에서

X의 점들은 

1 할당량 : 2m -2 

0 할당량 : 2m -1

Y의 점들은

1 할당량 : 2m -1

0 할당량 : 2m -2

가 된다. 관찰하면 처음의 X와 Y의 처지가 서로 바뀌었음을 알 수 있고, (할당량의 대소관계가 반전되었다!)
4개의 점을 없앴으므로 점 수는 그대로 4의 배수로 유지되었음도 관찰 가능하다. 따라서 아까의 조작을 반복적으로 시행할 수 있고, 맨 마지막 4개의
점고 딸린 간선집합까지 제거하면 모든 점과 간선이 전부 제거되므로, G가 온전히 의도대로 칠해졌음을 알 수 있다. 

사실 색칠 방법에 대한 것은 Euler curcuit 에 의한 해답도 가능하다!
