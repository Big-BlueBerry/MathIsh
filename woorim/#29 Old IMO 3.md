# #Old IMO 3 #

for the upper bound 8/27, we first use similarity and this simple principle: (If two triangle share one base, than the
ratio of heights is equal to the ratio of areas.)

and as described in the picture below, by the Arithmetic- Geometric Inequality, it is shown easily. 

![1](/woorim/imgs/29_1.png)

Second part is bit harder. Also use the principle mentioned (This time, two triangle share one height.). Applying it by both side and
applying a lemma for ratios, we get AI/A'A in terms of ABC's sides a, b, c. (Also for the other two)

![2](/woorim/imgs/29_2.png)

Then we make following substitution. Note that x, y, z are all positive since a, b, c are "sides of a triangle".
Modifying the form of expression, we finally get the factorization. Since x, y, z are positive, entire product is greater than
sum of particular terms appearing. Now, 1/8 = 1/2 * 1/2 * 1/2. Also, 1/2 * 1/2 * x/2(x+y+z), 1/2 * 1/2 * y/2(x+y+z), 1/2 * 1/2 * z/2(x+y+z)
appears in the product. Add them all to get another 1/8:

![3](/woorim/imgs/29_3.png)

Finally, the product is greater than 1/8 + 1/8 = 1/4.

