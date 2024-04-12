Thank you for your insightful comments on our manuscript.

We acknowledge that incorporating an overview diagram of the SODIUM framework would significantly enhance the reader's comprehension. To this end, we will develop a clear and informative diagram that delineates the key components and workflow of SODIUM. Furthermore, we are considering revising the layout of the paper, including possibly relocating the algorithm from the appendix to the main text, thereby making it more readily accessible to our readers.

Regarding the time and space complexity, it is comparable to that of training a standard deep classifier.

The overall time complexity of the main training loop is $O(K \cdot (m \cdot T_{DNN} + n \cdot T_{DNN} + p))$, where:
* $K$ represents the number of iterations in the outer loop until convergence.
* $m$ denotes the size of the minibatch.
* $n$ corresponds to the number of augmented OOD samples.
* $T_{DNN}$ is the time complexity of a forward pass, which depends on the specific network architecture design.
* $p$ indicates the total number of parameters in the neural network.

The space complexity for the main training loop is $O(m + n + p)$.
