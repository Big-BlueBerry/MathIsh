# #Old IMO 11 # 

우선 조건을 번역하면, (편의를 위해서 점들이 원을 2n - 1 등분하고 인접한 두 점을 잇는 호의 길이는 1 이라고 하자.) 두 점이 이루는 두 호 중 하나에
n 개의 점이 존재한다는 것은 큰 호의 길이가 n + 1  (다른 말로 하면 작은 호의 길이가 n - 2) 인 것이다. 

일단 k = n - 2 를 생각하자. 연속하는 n - 2 개의 점을 검게 칠한다면, 그 중 어느 두 점 사이에도 n 개 미만의 점이 있고 반대쪽 호에는 n 개보다 많은
점이 있게 되므로, n - 2는 불가능하다.

이번에는 k = n 을 생각하자. 어떤 n개의 검게 칠해진 점집합 O가 있어서, 그 둘 중 어느 쌍을 택해도 조건을 만족하지 않는다고 하자. 그렇다면,
O에서 "시계 방향으로" 호를 따라 n + 1 만큼 이동한 점들의 집합 (A라고 하자) 역시 원소수가 n개이고, O와 A의 공통원소가 없다. 그러나, 총
2n - 1 개의 점만 원 위에 있으므로 모순이다. 

즉 k 의 최소값은 n 이거나 n -1 중 하나이다. 여기서 우리는 n -1 이 최소값이 아니라고 가정한다:

아까의 O와 A의 표기를 그대로 사용하고, O 에서 시계 방향으로 호를 따라 n - 2 만큼 이동한 점들의 집합을 B라고 하자. 가정에 따라, B와 O, A와 O의 공통
원소가 없다. 이때, B와 A가 같으면, A, B, O 모두에 속하지 않는 점 x가 단 하나 있고, 그 점에서 시계 반대 방향으로 n - 2 만큼 이동하면 O의 점이 아니므로
A와 B의 공통원소인 점이 나온다. 그러나 A와 B의 공통원소이므로 이 점에서 시계 반대 방향으로 n + 1 만큼 이동하면 O의 점이다. 그런데 원에서 
"시계 반대 방향 n + 1만큼 이동 " = "시계 방향 n -2 만큼 이동" 이므로 x는 O의 점이 되어 모순이다.

따라서, B에 속하지 않는 A의 원소 a, A에 속하지 않는 B의 원소 b 가 각각 유일하게 존재하고 나머지는 A와 B의 공통원소, 혹은 O의 점이다.
이때, a에서 시계 반대 방향으로 n - 2 만큼 이동한 점을 생각하자. A의 정의에 따라 이 점은 O의 점이 아니고 이 점이 A의 점이라고 
가정하면 a에서 시계 방향으로 n + 1 만큼 이동한 점이 이 점인데 a는 O의 점이 아니므로 모순이 생긴다. 즉 이 점은 b이다.

정리해보면 다음과 같다. 지금부터는 헷갈리지 않도록 n + 1만 쓰도록 하고, 방향을 명시하여 구분하기로 한다.

집합 O (n-1개)
색칠된 점 집합

집합 A (n-1개)
O의 점의 시계방향으로 n + 1 만큼의 평행이동

집합 B (n-1개)
O의 점의 시계 반대 방향으로 n + 1만큼의 평행이동  

O 와 A, O 와 B는 각각 서로소, A와 B의 교집합(n-2개)

a 에서 시계 방향으로 n + 1 -> b
시계 반대 방향으로 n + 1 -> O의 점

b에서 시계 방향으로 n + 1 -> O의 점 
시계 반대 방향으로 n + 1 -> a

이제 약간의 정수론적 관찰을 도입한다. 2 * (n + 1) = 2n + 2 = 2n -1 +3 이므로, gcd(n+1, 2n-1) 은 1혹은 3이다. 먼저 
n +1 과 2n - 1 은 서로소라고 하자. 그러면, mod 2n -1 에 대하여 n+1, 2(n+1), ...(2n-2)(n+1) 은 모두 다른 수이다. 이것의 의미는
"어떤 한 점에서 시작해서(시작점은 지난 것으로 하자) 시계방향으로의 n+1 만큼씩 이동을 반복하면 겹치치 않고 2n -2 번만에 모든 점을 경유한다." 는 것이다.

a 에서 시작하면, a 다음은 b, b다음은 O의 점, 가정에 따라 O의 점 다음에는 A와 B의 공통원소가 나오는 패턴이 반복되에 마지막에는 O의 점이
등장한다. ( 여기서 한 번 더 가면 a )

n - 1 이 최소값이 아니며 n + 1과 2n - 1이 서로소이면 저렇게 되어야 한다는 것을 얻었는데, 실제로 n = 6 인 경우에 먼저 a 가 될 점을
찾고 n + 1씩 이동하면서 O의 점들을 칠하면 조건을 만족하는 두 쌍이 없는 O를 구성할 수 있다. 모든 n +1 , 2n - 1 이 서로소인 경우에 이 방법을
적용할 수 있다. 

반면, n+1 과 2n - 1의 최대공약수가 3 인 경우를 생각하자. 이 경우에는, 한 점에서 시작하여 n + 1씩 계속 이동하는 동작을 반복하면, (2n -1)/3 개의
점을 갖는 사이클을 형성한다. 왜냐면 n+1 씩 2 번 가면 원래의 점보다 3 이동한 점에 안착하는데 총 점의 개수가 3의 배수이기 때문이다. 모든 점이
이러한 사이클 3 개로 분할된다는 것은 자명하다. 그중 하나에 a와 b 가 모두 있는 것도 자명하다. a와 b가 없는 사이클을 생각하자.
이 사이클의 순회는 A, B의 공통원소 -> O의 점 -> A, B의 공통원소 -> O의 점... 을 반복하여 홀수 번 이동으로 시작점 돌아오게 됨을 의미한다.
그러나 이것은 가능하지 않다. 왜냐면 짝수 번 이동하면 A, B의 공통원소이므로 시점으로 돌아오기 전의 마지막 점은 A, B의 공통원소여야 하는데, 시작점도
A, B의 공통원소이므로 정의에 따라 돌아오기 전의 마지막 점은 O 의 점이어야 하기 때문이다.

결국 모순을 낳고, n + 1 과 2n - 1이 서로소가 아닌 경우에는 n-1 이 최소값임을 얻는다.









