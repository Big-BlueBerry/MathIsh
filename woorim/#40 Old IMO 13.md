# #Old IMO 13 #

역으로, "문제의 조건을 만족하지 않는 n개의 조합이 존재하는 최대의 n" 을 구하자. 이 값을 m 이라고 하자.
우선, 280 미만의 소수의 개수는 59개이고, 1까지 추가하면 60개가 있다.
즉, n >= 225 이면 어떠한 n개의 수를 뽑아도 그 안에 소수 혹은 1 인 수가 5 개가 있어서 그것들이 쌍마다 서로소이다. 따라서 m < 225.
이때, 소인수 2, 3, 5, 7 의 배수들의 합집합 안에서 어떠한 5개를 뽑아도 자명히 서로소가 아닌 두 수가 5개 안에 존재하므로,
n = [소인수 2, 3, 5, 7의 배수들의 합집합의 원소의 개수] 로 놓으면 문제의 조건을 만족하지 않는 n개의 조합이 존재한다.
이 수를 구하기 위하여 집합의 포함 - 배제의 원리를 적용하자. 다음 결과들은 계산으로 쉽게 얻어진다:

280 이하의 2의 배수의 개수 = 140

280 이하의 3의 배수의 개수 = 93

280 이하의 5의 배수의 개수 = 56

280 이하의 7의 배수의 개수 = 40

280 이하의 2와 3의 공배수의 개수 = 46

280 이하의 2와 5의 공배수의 개수 = 28

280 이하의 2와 7의 공배수의 개수 = 20

280 이하의 3와 5의 공배수의 개수 = 18

280 이하의 3와 7의 공배수의 개수 = 13

280 이하의 5와 7의 공배수의 개수 = 8

280 이하의 2,3,5의 공배수의 개수 = 9

280 이하의 2,3,7의 공배수의 개수 = 6

280 이하의 2,5,7의 공배수의 개수 = 4

280 이하의 3,5,7의 공배수의 개수 = 2

280 이하의 2,3,5,7의 공배수의 개수 = 1

따라서 저 합집합의 원소의 개수는 ( 140 + 93 + 56 + 40 ) - ( 46 + 28 + 20 + 18 + 13 +8 ) + ( 9 + 6 + 4 + 2 ) - 1 = 216
즉, m >= 216 이다. 이제 사실 m = 216 임을 보여서 문제의 답이 217 임을 증명하자. m < 217 임을 증명하는 것으로 충분하다. 이때 m = 217 이 안됨을
증명하면 m > 217 인 경우는 당연히 안되므로, m 이 217 이 아님을 증명하면 된다. 
조건을 만족하지 않는 217 개가 존재하려면, 이 조합에서 뺄 수들을 뽑는데, 위의 고찰에 따라 소수 혹은 1인 수들 중 55 개보다 더 많이 뽑아야 한다. 즉 56개를 [소수 혹은 1]
중에서 뽑고 나머지 7개를 어떻게 뽑느냐에 대해서 생각해야 한다. 이때, 이 7 개 중 두 개는 2, 3, 5, 7, 11, 13 의 제곱들 중에 뽑아야 한다.
그렇지 않으면 당연히 쌍마다 서로소인 5개가 존재하기 때문이다.

또, 이 7 개중 다른 하나는 소수여야 한다. 그렇지 않으면, 소수 4개가 이 조합
안에 존재한다. (그 4개가 최소라고 하여 2, 3, 5, 7 이라고 하자) 이때 이들과 모두 서로소인 두 소수의 곱으로 된 수를 따져보면
13`*`11, 11`^`2, 13`^`2, 17`*`13, 13`*`19, 11`*`19, 11`*`17, 11`*`23 의 8 개가 존재하는데, 이중에 어느 7개를 뽑아도 하나가 남아서 조합 안에 존재하므로 그것과
2, 3, 5, 7 은 쌍마다 서로소여서 안 된다. (소수들이 최소가 아니면 더 많은 이들과 모두 서로소인 두 소수의 곱으로 된 수들이 존재한다)  

그런데, 이 논리를 소수의 제곱에 대해서 적용할 수도 있기 때문에, 결론적으로 7 개 중 세 개는 2, 3, 5, 7, 11, 13 의 제곱들 중에, 한 개는 소수여야 한다.
(이 경우, 11`^`2과 13`^`2을 빼고 적용할 수 있고 6 개 중에 다른 4 개 (소수인 하나와 제곱수 2개 제외) 를 어떻게 뽑아도 하나가 남으니까..)

이제 다시 두 소수의 곱으로 된 280 이하의 수들에 대해 관찰한다. 각 행(row) 에서 뽑을 수 있는 개수는 위의 제약을 고려하면 최대 4개(이 경우
제곱수 하나를 뽑아야 한다)이므로,
제약을 지켜 어떠한 7개를 뽑는다고 해도 첫 4행에서는 각각 2, 3, 5, 7과 19보다 큰 소수의 곱으로 된 수가 하나 이상씩 남는다. 각 행의
원소의 범위를 살펴보면 2, 3, 5, 7 과 곱해진 19 초과의 소수들이 서로 다르도록 그러한 4개의 수를
남은 수들 중에서 각각의 행에서 택하는 것이 가능하다.

2`*`2, 2`*`3, 2`*`5, ... 2`*`139

3`*`2, 3`*`3, 3`*`5, ... 3`*`89

5`*`2, 5`*`3, 5`*`5, ... 5`*`53

7`*`2, 7`*`3, 7`*`5, ... 7`*`37

11`*`2, 11`*`3, ... 11`*`23

13`*`2, 13`*`3, ... 13`*`19

이제 5, 6 번째 항의 11`^`2, 13`^`2, 11`*`13, 11`*`17, 11`*`19, 13`*`17, 13`*`19 중에서, 제약을 지켜 뽑을 수 있는 개수는
기껏해야 5개 (제곱수 2 개 포함) 이므로, 어떻게 뽑든 하나의 수는 이들 중에 남아 있다. 그 수를 택하자.

아까 뽑은 4 개의 수들에서 2, 3, 5, 7 과 곱해진 소수들은 각각 서로 다르고 19 보다 크므로 택한 5개의 수는 쌍마다 서로소이다. 

따라서 m = 217 일 수 없다. 즉 m = 216이고 문제의 답은 217 이다.


