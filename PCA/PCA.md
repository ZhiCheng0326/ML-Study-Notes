# Principle Component Analysis
Aim: Find a direction of projection that maximize the data's variance

## How does the variance looks like?
### Generally
Variance/Covariance formula:
$$
Var(X) = Cov(X,X)={\frac {1}{N}}\sum _{i=1}^{N}\left(X_{i}-{\bar {X}}\right)\left(X_{i}-{\bar {X}}\right)
$$
In PCA, first step is to **centralize** the dataset.
$$
X_i = X_i-\bar X
$$
Therefore, for simplicity purpose, the variance formula becomes:
$$
Var(X) = {\frac {1}{N}}\sum _{i=1}^{N}\left(X_{i}\right)\left(X_{i}\right)
$$
### PCA
Note that x must be **centralized**!
The projected data, y :
$$
y = x_i \cdot w
$$
$$
\sigma^2_w = {\frac {1}{n}}\sum _{i} (x_{i} \cdot w_{i})^2 = \frac{1}{n}(xw)^T(xw) = \frac{1}{n}w^Tx^Txw
$$
$$
\sigma^2_w =w^T\frac{x^Tx}{n}w = w^TCw
$$
C = Covariance matrix
$$

$$
## Find the Principle axes of the dataset
Objective function:
$$
\max_{w^Tw=1} w^TCw
$$
> Since it's a maximizing function, the purpose of w has unit length to avoid w->inifinity

Lagrangian:
$$
L(w,\lambda)= w^TCw-\lambda (w^Tw-1)
$$

From KKT condition:
$$
\frac{\partial L(w,\lambda)}{\partial w} = 2Cw-2\lambda w=0
$$
$$
Cw=\lambda w
$$
> where w = eigenvectors, lambda = eigenvalue

## Some final remarks...
* Eigenvector w with the largest eigenvalue(since it's maximizing function) is the projection we're looking for!
* Eigenvectors of the Covariance Matrix, `C` are the principle components of the dataset.
* The direction of second principle component is orthogonal to the first component with the most variance.

## Reference
* [CMU Lecture Notes](https://www.stat.cmu.edu/~cshalizi/uADA/12/lectures/ch18.pdf)
* [Why eigenvector w taken to be unit norm?](https://stats.stackexchange.com/questions/117695/why-is-the-eigenvector-in-pca-taken-to-be-unit-norm)

## Author
Author: Lee Zhicheng  
Date: 30/04/2020
