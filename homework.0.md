#homework #0

##1 Probability and Statistics
###1.1 (combinatorics)
Let C(N,K)满足下式：
$$
C(N,K) =\begin{cases}
1 & K=0\ or\ K=N \\
C(N-1,K) + C(N-1, K-1) & 0 < K <= N
\end{cases}
$$
> 证明：
$$C(N,K) = \dfrac{N!}{K!(N-K)!} $$                                                 
**解：**
用数学归纳法来证明，
-  (1) 初始值满足公式：
 当$K=0, N=1$时，有
                  $$C(1,0) = 1 = \dfrac{1!} {0!*1!}$$
 当$K=1,N=1$时，有
                  $$C(1,1) = 1 =     \dfrac{1!} {1!*0!}$$
- (2) 现在要递推证明：
   当K=k, N=n与K=k+1, N=n都满足公式，证明K=k+1, N=n+1满足公式
  即：
    $$C(n,k) = \dfrac{n!}{k!(n-k)!} \     (a)$$
    $$C(n,k+1) = \dfrac{n!}{(k+1)!(n-k-1)!}  \ (b)$$  
   => 
   $$C(n+1, k+1) = C(n, k+1) + C(n, k) \\ 
      =  \dfrac{n!}{(k+1)!(n-k-1)!}  +  \dfrac{n!}{k!(n-k)!} \\
      = \dfrac{n!}{k!(n-k-1)!*(k+1)} + \dfrac{n!}{k!(n-k-1)!*(n-k)} \\
      =\dfrac{n!}{k!(n-k-1)!} * (\dfrac{1}{k+1} + \dfrac{1}{n-k})\\
      =\dfrac{n!}{k!(n-k-1)!} * \dfrac{n-k +k +1}{(k+1)(n-k)}\\
      =\dfrac{n!}{k!(n-k-1)!} * \dfrac{n+1}{(k+1)(n-k)}\\
      = \dfrac{(n+1)!}{(k+1)!(n-k)!}$$
综合（1）（2）原命题得证
      
###1.2 (counting)

1. What is the probability of getting exactly 4 heads when flipping 10 fair coins?

>从10次抛硬币事件中，取4次，那么$$p=\dfrac{C(10, 4)}{2^{10}} $$

2. What is the probability of getting a full house (XXXYY) when randomly drawing 5 cards out of a deck of 52 cards?
> 分母: 从52张牌选取5张的组合
>  分子： 先选2张数字：P(13,2), 有两个数字有差异，有一个形成xxx，有一个数字形成yy形式; 再选花色： 对于xxx是C(4,3), YY是C(4,2), 所以结果是
> $$\dfrac{P(13,2)*C(4,3)*C(4,2)}{C(52,5)}$$

###1.3(conditional probability)
If your friend flipped a fair coin three times, and tell you that one of the tosses resulted in head, what is the probability that all three tosses resulted in heads?
>解：
这是个条件概率问题。条件事件： 某一次抛的结果是head；未知事件： 三次均为head
$$p(三次均为head| 某一次抛的结果head) =  0.5*0.5*0.5 / (1 - 0.5*0.5*0.5) \\
=1/7$$
###1.4 (Bayes theorem)
A program selects a random integer X like this: a random bit is first generated uniformly. If the bit is 0, X is drawn uniformly from {0, 1, . . . , 7}; otherwise, X is drawn uniformly from {0, −1, −2, −3}. If we get an X from the program with |X| = 1, what is the probability that X is negative?

>解：设最高位为Y一共有两种取值，Y=0或者1（表示其他值）
要求条件概率p(Y=1 |  |X|=1) = 
$$p(Y=1||X| = 1) = \dfrac{p(Y=1, |X| = 1)}{p(|X|=1)}\\=
\dfrac{p(Y=1, X=1) + p(Y=1, X=-1)}{(p(X=1) + p(X=-1))}\\=\dfrac{p(Y=1, x=1) + p(Y=1, x=-1)}{p(Y=1, X=1) + p(Y=0, X=1)  + p(Y=1, X=-1) + p(Y=0, X=-1)}$$
其中，
$p(Y=1, X=1) = 0 $ 
$p(Y=0, X=-1) = 0$
$p(Y=1, x=-1) = \dfrac{1}{2} * \dfrac{1}{4}=\dfrac{1}{8}$
$p(X=1) = p(Y=1, X=1) + p(Y=0, X=1) = \dfrac{1}{2}*\dfrac{1}{8}=\dfrac{1}{16}$
$p(X=-1) = p(Y=1,x=-1) + p(Y=0, X=-1) = \dfrac{1}{2}*\dfrac{1}{4} = \dfrac{1}{8}$
$$p(Y=1||X| = 1) = \dfrac{2}{3}
$$
 

###1.5(union/intersection)
If P(A) = 0.3 and P(B) = 0.4,
what is the maximum possible value of P (A ∩ B)? 
what is the minimum possible value of P (A ∩ B)? 
what is the maximum possible value of P (A ∪ B)? 
what is the minimum possible value of P (A ∪ B)?
>解：
P(A∩B) =  P(A) - P(A-B)
当P(A-B) = 0时，P (A ∩ B) 最大为P(A)=0.3
当P(A-B) = A时，P (A ∩ B) 最小为 0
P (A ∪ B) = P(B)  + P(A-B) 
当P(A-B) = 0 即A是B的子集时最小， 此时P(A U B) = P(B) = 0.4 
当P(A-B) = P(A)时最大，此时P(A U B) = P(A) + P(B) = 0.7
