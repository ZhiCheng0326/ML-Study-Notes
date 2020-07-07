# Intuition of the math behind Laplacian & Laplacian Matrix
## Overview
Laplacian of a function, f is defined as:  

$$
\Delta f = div(grad(f))=\nabla \cdot \nabla f
$$  

Vector field             |  Topology
:-------------------------:|:-------------------------:
![Vector field](./Laplacian_graph_img1.PNG)  |  ![Topology](./Laplacian_graph_img2.PNG)


Referring left image, **positive** divergence diverges **out**, whereas **negative** divergence **converges** to a point.  
Referring right image, a **positive** divergence appears as **valley** in topology, whereas **negative** divergence appears as **mountaintop**.  


## Laplacian Graph
Laplacian kinda measures how **“smooth”** the function is over its domain.  
On graphs, a smooth function:  
> connected vertices -> changes slightly
> unconnected vertices -> changes significantly

Therefore, representation in mathematical way:
$$
\sum_{u,v} w_{uv}(f(u)-f(v))^2
$$
> u, v are the vertices
> w is the weight of the edge between node u and v

More formally:.

$$
\frac{1}{2} \sum_{u,v} w_{uv}(f(u)-f(v))^2 = f^TLf
$$
* **Minimizing** the equation's *left* part = minimizing **distance** between **connected**(neighbouring) nodes
* **Minimizing** the equation's *right* part =  eigenvectors the the Laplacian （Refer PCA note）


## Laplacian Matrix
Given L as Laplacian Matrix, D as Degree Matrix, W as adjacency matrix
$$
L=D-W
$$
Example:
![L=D-W](Laplacian_graph_img3.PNG)

As show in table, in Laplacian Matrix,
> diagonal value = degree of a node
> sum of number of "-1" in row/column = degree of the node

## Reference
* [Quora-Laplacian Matrix Intuition](https://www.quora.com/Whats-the-intuition-behind-a-Laplacian-matrix-Im-not-so-much-interested-in-mathematical-details-or-technical-applications-Im-trying-to-grasp-what-a-laplacian-matrix-actually-represents-and-what-aspects-of-a-graph-it-makes-accessible "Quora")

* [Youtube-Khan Academy](https://www.youtube.com/watch?v=EW08rD-GFh0&t=78s "Youtube")

* [2.3.2 Laplacian Introduction](https://blog.csdn.net/qq_24519677/article/details/82291867?depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1&utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1 "CSDN")

## Author
Author: Lee Zhicheng  
Date: 30/04/2020
