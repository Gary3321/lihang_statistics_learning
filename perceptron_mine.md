Perceptron is an easy machine learning algorithm, which is also the first machine learning algorithm. Its hypothesis is that the dataset
is linear separable.

I will use the following picture to demonstrate this algorithm.
![perceptron_example](/pictures/perceptron_example.png)
There are two sets of points, red points and green points, which are not mixed (linear separable). The perceptron algorithm (f(x)) is to find a line to separate the two sets of points, in other words, f(x) outputs red or green given a point.

The perceptron algorithm is: 

f(x) = sign(w.x+b)

sign(x) =
$\begin{cases}
+1, & x\ge0 \\
-1, & x<0
\end{cases}$

That is, if $w.x+b\ge 0$, then f(x) = +1 (red points), f(x) = -1 (green points) otherwise. So, perceptron only applies to **binary classification** problems. $w.x+b$ represents a super space, in this two dimensional example, it represents a line.

### how does the algorithm learn
The objective is to find such a super space that the distance between the miss-classified points and this space is 0.

if $-y_i(w.x_i + b)>0$, then $x_i$ is miss-classified (shown by the definiton of linear-separable dataset). So, the distance can be defined as $\gamma_i = -y_i(w.x_i + b)$.

The objective is to minimize the loss function:
L(w,b) = $\sum_i^M(\gamma_i) = -\sum_i^M y_i(w.x_i + b)$.

We use gradient descent to minimize L(w,b):
- initialize w =0, b=0
- calculate the gradient of w and b
  - $\nabla_{w}$ L(w,b) = $-\sum_{x_i\in M}(y_i.x_i)$
  - $\nabla_{w}$ L(w,b) = $-\sum_{x_i\in M}y_i$
- 更新w, b (对每个误分类点更新一次)
  - w <- w + $\alpha * \sum_{x_i\in M}(y_i.x_i)$
  - b <- b + $\alpha \sum_{x_i\in M}y_i$
