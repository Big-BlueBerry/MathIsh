# Test #

The problem was to evaluate the limit

![1](/woorim/imgs/CodeCogsEqn.gif)

If there are r 2's and n-r 1's among n variables, the inner term is equal to (n+r)/(n+3r)

![2](/woorim/imgs/T1.gif)

Since the sum is over all possible combinations, there are nCr cases with r 2's and n-r 1's. Thus,
the limit can be simplified like this.

![3](/woorim/imgs/T2.gif)

I proved the following lemma as my analysis exercise:

# Lemma. # 

For Bernstein polynomial b(v,n), sequence of polynomials B_n converges uniformly to f(x) on [0,1],
given that f is a continuous function on [0,1].

![4](/woorim/imgs/T3.gif)

To solve the problem, I put f = 1 - 2x/(2+3x), and x  = 1/2.

![5](/woorim/imgs/T4.gif)


# Question #

I interpreted b(v, n) as a probability:
For an event E with probability x, probability (v times occurrence of E among n independent trial) is 
equal to b(v,n)

Next, to generalize the problem, I interpreted f(v/n) as the value of random variable when E occured v times.
Then B_n will be an expected value of this random variable. 

Here, by setting f(x) = x and applying the lemma, I concluded like this:
the expected value of (the number of occurence)/(Total number of trial) converges to the mathematical probability
as total number of trial goes infinity.

Can my inference an explanation for specific case of "Law of Large Number"?

