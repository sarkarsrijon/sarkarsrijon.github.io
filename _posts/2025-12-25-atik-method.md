---
layout: post
title: Tikhonov Regularization with Arnoldi and Newton's Method
date: 2025-12-25 20:56:00-0000
description: Solving for the regularization parameter λ using flexible Arnoldi and Newton's method for inverse problems
tags: summer-research
categories: sample-posts
related_posts: false
---

# Lemma

In 

$$||A\mathbf{x} - \mathbf{b}||_2^2 + \lambda ||\mathbf{x}||_2^2$$

we want to choose $$\lambda$$ such that 

$$||A\mathbf{x}_\lambda^{(k)} - \mathbf{b}|| = \tau\delta.$$

Incorporating (flexible) Arnoldi and using Newton's method to solve for $$\lambda$$.

## Derivation

First, we consider the subspace reduction to get $$\|A\mathbf{x} - \mathbf{b}\|_2^2$$ reduced to $$\|H\mathbf{y} - V_p^T\mathbf{b}\|_2^2$$. Now, as we consider $$x=V_p y$$, and $$V_p$$ is orthogonal we get $$\|\mathbf{x}\|_2^2 = \|V_p\mathbf{y}\|_2^2 = \|y\|^2_2$$. Leading our problem to be 

$$||H\mathbf{y} - ||\mathbf{b}||\mathbf{e}_1||_2^2 + \lambda ||\mathbf{y}||_2^2.$$

Where $$\|\mathbf{b}\|\mathbf{e}_1 = V_p^T \mathbf{b}$$.

**Lemma:** Using the fact that closed form solution of $$\underset{\mathbf{x}}{\min}\|A\mathbf{x} - \mathbf{b}\|_2^2 + \lambda \|\mathbf{x}\|_2^2$$ is 

$$x = (A^TA + \lambda I)^{-1}A^T\mathbf{b}.$$

In our reduced subspace with the Hessenberg matrix of $$H$$ we get 

$$y = (H^TH + \lambda I)^{-1} H^T||\mathbf{b}||\mathbf{e}_1.$$

Further, squaring our given problem gives $$\|A\mathbf{x}_\lambda^{(k)} - \mathbf{b}\|_2^2 = \tau^2\delta^2.$$ Combining these yield 

$$||H(H^TH+\lambda I)^{-1}H^Tb^\odot - b^\odot||_2^2 = \tau^2\delta^2. \qquad (1)$$

Where $$\|\mathbf{b}\| \mathbf{e}_1 = b^\odot$$. Now, considering SVD of $$H$$, we have $$H = U\Sigma V^T$$. Therefore, $$H^T = V\Sigma^T U^T$$. 

So, in the inner bracket, we have

$$H^TH + \lambda I = V\Sigma^T U^TU\Sigma^T V^T + \lambda I = VDV^T + \lambda I.$$

Where we let $$D = \Sigma^T\Sigma$$.

Finally to calculate its inverse, we let $$X = VDV^T + \lambda I$$ and pre and post multiply it with $$V^T$$ and $$V$$ to get 

$$V^TXV = D + \lambda V^TIV = D + \lambda V^TV = D + \lambda I$$

All while using the fact that for orthogonal matrices $$V^TV = VV^T = I$$. (Likewise for $$U$$.) Taking the inverse on both sides gives 

$$(V^TXV)^{-1} = V^{-1}X^{-1}{V^T}^{-1} = V^TX^{-1}V = (D+\lambda I)^{-1}.$$

Again, right and left multiplying with $$V$$ and $$V^T$$, we finally get our desired result 

$$X^{-1} = V(D+\lambda I)^{-1}V^T.$$

Plugging this back in $$(1)$$ with SVD of $$H$$ and $$H^T$$ we get 

$$U\Sigma V^T \big(V(D+\lambda I)^{-1}V^T\big)V\Sigma^T U^T = U\Sigma(D+\lambda I)^{-1}\Sigma^T U^T.$$

Where all three matrices in the middle are diagonal. Therefore, we have 

$$||\left(I - U\Sigma(D+\lambda I)^{-1}\Sigma U^T\right)b^\odot||^2_2 = \tau^2\delta^2.$$

In addition, we note that pulling out the orthogonal matrix of $$U$$ using invariance under the 2-norm further simplifies the above expression to

$$||(U^T - \Sigma(D+\lambda I)^{-1}\Sigma^TU^T)b^\odot||_2^2 = ||(I - \Sigma(D+\lambda I)^{-1}\Sigma^T) \hat{b}||_2^2$$

Where $$\hat{b} = U^Tb^\odot$$. Further, to observe terms of the product of the three matrices, we let $$\sigma_i$$ denote the diagonal elements (singular values) of $$\Sigma$$ of the SVD of $$H_{k+1,k}$$.

Since $$\Sigma$$ is $$(k+1)\times k$$, it constitutes an additional last row of all zeros while its transpose $$\Sigma^T$$ contains the last column of all zeros. Nonetheless, we get the terms of $$(D + \lambda I)^{-1}$$ as 

$$\frac{1}{\sigma_i^2 + \lambda}$$

where $$D$$ being $$\Sigma^T\Sigma$$ leads it to being a $$k \times k$$ matrix.

$$
\begin{bmatrix}
\sigma_1 & 0 & \cdots & 0 \\
0 & \sigma_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \sigma_k \\
0 & 0 & \cdots & 0
\end{bmatrix}
\begin{bmatrix}
\frac{1}{\sigma_1^2 + \lambda} & 0 & \cdots & 0 \\
0 & \frac{1}{\sigma_2^2 + \lambda} & \cdots & \vdots \\
\vdots & \vdots & \frac{1}{\sigma_3^2 + \lambda} & 0 \\
0 & \ddots & \cdots & \frac{1}{\sigma_k^2 + \lambda}
\end{bmatrix}
\begin{bmatrix}
\sigma_1 & 0 & \cdots & 0 & 0\\
0 & \sigma_2 & \cdots & 0 & 0\\
\vdots & \vdots & \ddots & 0 & 0\\
0 & 0 & \cdots & \sigma_k & 0
\end{bmatrix}
$$

Multiplying these all out, we finally have an $$(k+1) \times (k+1)$$ matrix, such that the last row and last column constitute all zeros while the diagonal entries are $$\frac{\sigma_i^2}{\sigma_i^2 + \lambda}$$. Finally, with the identity matrix subtraction, we get the diagonal elements as 

$$1-\frac{\sigma_i^2}{\sigma_i^2 + \lambda} = \frac{\lambda}{\sigma_i^2 + \lambda}$$

with the $$(k+1)^{\text{th}}$$ diagonal entry as just $$1$$.

Now, substituting $$\lambda = \frac{1}{\alpha}$$ here (for ease of computation) boils this to 

$$\frac{1}{\alpha \sigma_i^2 + 1}.$$

Lastly, considering the $$\hat{b}$$ vector multiplied by this diagonal matrix, we get the norm square of the product as the following summation

$$\sum_{i=1}^k \left(\frac{\hat{b}_i}{\alpha\sigma_i^2 + 1}\right)^2 + \hat{b}_{k+1}^2.$$

Therefore, 

$$f(\alpha) = \sum_{i=1}^k \left(\frac{\hat{b}_i}{\alpha\sigma_i^2 + 1}\right)^2 + \hat{b}_{k+1}^2 - \tau^2\delta^2.$$

Taking the derivative w.r.t $$\alpha$$ using the chain rule gives this as 

$$f'(\alpha) = \sum_{i=1}^k \hat{b_i}^2 \cdot \frac{-2\sigma_i^2}{(\alpha\sigma_i^2+1)^3}.$$

With the last terms cancelling being constant. Now, applying Newton's method for root finding to get a recursive formula for $$\alpha$$ to eventually converge we plug the above in the following 

$$\alpha_{n+1} = \alpha_n - \frac{f(\alpha_n)}{f'(\alpha_n)}.$$
