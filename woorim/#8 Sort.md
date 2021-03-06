# #8 #

원래 문제는, 다음 Theorem 에 대입하여 곧바로 해결된다. 

# Theorem. #
1, 2, .. n의 permutation function p를 swap들의 합성으로 나타낼 때, 합성 횟수의 홀짝성은 합성 방법에 상관없이 일정하다. 

# Proof #

`*`는 합성 연산자, `p'` 는 p의 inverse function, `id`는 identity permutation `{1,2,..n}`이라고 하고, `{s}` 와 `{t}`은 swap funcation의 함수열이라고 하자. 
이제, p를 두 가지 합성 방법으로 나타내어, 

`p = s_i * s_(i-1) * ... s_1 = t_j * t_(j-1) * ... t_1` 이라고 하자. 바로 다음 사실을 알 수 있다.

`id = p' * p = s_1'*...* s_(i-1)' * s_i' * t_j * t_(j-1) * ... t_1 * (id)`

즉, j와 i의 parity 가 같음을 보이기 위해서는, 임의의 `f_k * f_(k-1) * ... * f_1 * (id) = id` 를 만족하는 swap function의 함수열 `{f}` 에 대해 `k % 2 =0`
임을 보이는 것으로 충분하다.

이제 함수  `X(p)` 와 `x(a)` 를 다음과 같이 정의하자.

`x(a) = permutation p의 원소 a에 대해, a보다 오른쪽에 있으면서 a보다 작은 원소의 개수`

`X(p) = p의 모든 원소에 대한 x(a)의 총합`

`id = {1,2,...n}`에 대하여, 자명히 `X(id) = 0`이 성립한다. 이제, 임의의 p에 대하여 f가 swap function 일 때, `X(f * p)` 와 `X(p)`
사이의 관계를 관찰하자.

`p = {...a, ... b, ...}`, `f * p = {...b, ...a, ...}` 으로 놓고, `a < b` 라고 가정하자. 

`len(I) = p에서 a와 b 사이의 구간 I의 원소의 개수`

`L = p에서 I의 a 보다 작은 원소의 개수`

`M = p에서 I의 b보다 큰 원소의 개수`

라고 놓자. 다음 변화에 주목한다.

(1) a의 왼쪽, b의 오른쪽에 있는 원소들에 대해서 x의 함수값은 f를 합성한 후에도 불변이다.

(2) 합성 후 I의 원소들에 대해서, x의 함수값의 총합은 `len(I) - L - M` 이다. `len(I) - L` 개의 원소들이 a보다 큰 것들이므로, a가 앞으로 오면서
count가 1씩 증가하게 되고, M개의 원소들이 b보다 큰 것들이었으므로, b가 뒤로 밀려나면서 역시 그 원소들에 대해서 count가 1 감소하기 때문이다.

(3) 합성 후 a에 대해서, x(a) 는 a가 I앞으로 당겨졌으므로 L만큼 감소한다.

(4) 합성 후 b에 대해서,b가 I뒤로 밀려났으므로, `len(I) - M` 개의 b보다 작은 I의 원소가 있고 또한 `b > a` 이므로, `x(b)` 는 `len(I) - M + 1` 만큼 증가한다.

1, 2, 3, 4를 총합하면, `X(f * p) = X(p) +2len(I) -2M -2L +1` 을 얻는다. 즉, `mod 2`를 취하면, `X(f * p) === X(p) + 1 (mod 2)` 임을 알 수 있다. 이제,
`f_k * f_(k-1) * ... * f_1 * (id) = id` 에서 k가 홀수라고 가정하자. `X(id) = 0` 이므로, `X(f_k * f_(k-1) * ... * f_1 * (id))`의 parity 는 `k mod 2 = 1`이다.

그러나, 좌변과 우변은 같아야 하므로 그 parity 는 `X(id) = 0` 이어야 하고, 이는 모순이다. 따라서, k는 짝수라는 결론에 도달한다. 
