This is a short summary of the literature I read about understanding of deep learning.

Zdeborová et al. (Zdeborová, 2020) described deep learning as the interplay between three components:
input data follows specific distributions, training algorithms and architectures of ANNs. Many different
research directions are aiming at understanding deep learning corresponding to these components. In
the view of data, researchers have tried to model the distribution of inputs and studied the generalization
properties of ANNs. To understand the training algorithms, they explored the landscape of loss surface and
training dynamics.

From the view of data distribution, Lei et al. (Lei et al., 2020) pointed out that the data distribution in
the natural dataset was very close to a low-dimensional manifold. With the help of this assumption, they
changed the generator in a generative adversarial network (GAN) to an AE-OT model, in which AE meant
an auto-encoder for manifold learning. Transfer learning is a noticeable characteristic of deep learning that
can be understood through the data space of tasks. Achille et al. (Achille et al., 2021) studied the space of
learning tasks and proposed a framework to describe their distance. The distance could be used to measure
the complexity of a transfer learning process. Ivanovic et al. (Ivanovic et al., 2019) used a different method
to compute the transition probability through the traversing path’s degree of difficulty between two learning
tasks. The adversarial robustness has attracted much attention in recent years. Researchers revealed that
the geometric structure of adversarial examples had a significant connection with the prediction of ANNs
(Ortiz-Jiménez et al., 2020).

The research of training algorithms is diversified with different perspectives. Jacot et al. (Jacot et al.,
2018) utilized a kernel to describe the evolution process of an ANN during training, and they named the
kernel as the neural tangent kernel (NTK). Cao et al. (Ortiz-Jiménez et al., 2020) connected the spectral bias
phenomenon with NTK. They found that during training, the direction of the learning could be decomposed
as directions defined by the eigenfunctions of the NTK. Belkin et al. (Belkin et al., 2018) found the
generalization properties of ANNs also related to kernel learning. They constructed kernel machines that
could be trained to be overfitting on training data while still performing well on test samples; this showed
that kernel learning was critical for understanding deep learning. Information theory is another widely
used tool for the theoretical explanation of ANNs. Achille et al. (Achille and Soatto, 2018) studied the
invariance of the learned representations. They found that the invariance was determined by the information
minimality encoded in them. Apart from this, they pointed an overfitting term in the cross-entropy loss that
the Information Bottleneck of the weights could bound. In a later article (Achille et al., 2019), Achille et al. proved that low information complexity could benefit the generalization performance of ANNs. To explain
the critical periods during the training of ANNs, they studied the connectivity between layers by computing
Fisher Information of the learned weights (Achille et al., 2018). Another way to understand the learning
dynamics is to describe ANNs as Gaussian processes (GPs). Lee et al. (Lee et al., 2017) showed that an
infinitely wide ANN is equal to a GP. A Bayesian network trained with squared loss could be equivalent to a
GP with a compositional kernel (Lee et al., 2019). Novak et al. (Novak et al., 2018) extended the conclusion
to convolutional neural networks (CNNs), proving that a multi-layer CNN could be regarded as a GP without
the trainable kernel. Besides the above theories, mean-field is also an effective way to model the training of
ANNs. Mei et al. (Mei et al., 2018) analyzed two-layer networks trained with stochastic gradient descent
(SGD) algorithms. They proposed that a specific non-linear partial differential equation (PDE) could capture
the learning dynamics. Then they proved mean-field theory was also valuable with unbounded activation
functions and noisy SGD (Mei et al., 2019).

From the view of the loss landscape, researchers focused on analyzing the surface of the loss function.
Bahri et al. (Bahri et al., 2020) proposed an interdisciplinary understanding of the error landscape, which
indicated the potential relationship between energy landscape with quenched disorder. Zhou et al. (Zhou
et al., 2020) explained why adam optimizer performed worse than SGD optimizer on unseen data through
the detailed analysis around local minimum points. Kawaguchi et al. (Kawaguchi and Kaelbling, 2020)
utilized a novel method to eliminate all suboptimal points on the loss landscape.

Compared with the above perspectives, the research of general understanding of the architectures of
ANNs is insufficient. As far as I know, there are two kinds of methods, and the first one studies the graph
structure of the neural network. You et al. (You et al., 2020) extracted a relational graph from the neural
network and showed the performance of the networks are highly related to the properties of the graph. The
second kind of method study the topological structure, which is the macro connections among the whole
network (Yuan et al., 2020).

#### References

Achille, A., Paolini, G., Mbeng, G., and Soatto, S. (2021). The information complexity of learning tasks, their structure and their
distance. Information and Inference: A Journal of the IMA, 10(1):51–72.

Achille, A., Paolini, G., and Soatto, S. (2019). Where is the information in a deep neural network? arXiv preprint arXiv:1905.12213.

Achille, A., Rovere, M., and Soatto, S. (2018). Critical learning periods in deep networks. In International Conference on Learning
Representations.

Achille, A. and Soatto, S. (2018). Emergence of invariance and disentanglement in deep representations. The Journal of Machine
Learning Research, 19(1):1947–1980.

Bahri, Y., Kadmon, J., Pennington, J., Schoenholz, S. S., Sohl-Dickstein, J., and Ganguli, S. (2020). Statistical mechanics of deep
learning. Annual Review of Condensed Matter Physics, 11:501–528.

Belkin, M., Ma, S., and Mandal, S. (2018). To understand deep learning we need to understand kernel learning. In International
Conference on Machine Learning, pages 541–549. PMLR.

Ivanovic, B., Harrison, J., Sharma, A., Chen, M., and Pavone, M. (2019). Barc: Backward reachability curriculum for robotic
reinforcement learning. In 2019 International Conference on Robotics and Automation (ICRA), pages 15–21. IEEE.

Jacot, A., Gabriel, F., and Hongler, C. (2018). Neural tangent kernel: Convergence and generalization in neural networks. arXiv
preprint arXiv:1806.07572.

Kawaguchi, K. and Kaelbling, L. (2020). Elimination of all bad local minima in deep learning. In International Conference on
Artificial Intelligence and Statistics, pages 853–863. PMLR.

Lee, J., Bahri, Y., Novak, R., Schoenholz, S. S., Pennington, J., and Sohl-Dickstein, J. (2017). Deep neural networks as gaussian
processes. arXiv preprint arXiv:1711.00165.

Lee, J., Xiao, L., Schoenholz, S., Bahri, Y., Novak, R., Sohl-Dickstein, J., and Pennington, J. (2019). Wide neural networks of any
depth evolve as linear models under gradient descent. Advances in neural information processing systems, 32:8572–8583.

Lei, N., An, D., Guo, Y., Su, K., Liu, S., Luo, Z., Yau, S.-T., and Gu, X. (2020). A geometric understanding of deep learning.
Engineering, 6(3):361–374.

Mei, S., Misiakiewicz, T., and Montanari, A. (2019). Mean-field theory of two-layers neural networks: dimension-free bounds and
kernel limit. In Conference on Learning Theory, pages 2388–2464. PMLR.

Mei, S., Montanari, A., and Nguyen, P.-M. (2018). A mean field view of the landscape of two-layer neural networks. Proceedings
of the National Academy of Sciences, 115(33):E7665–E7671.

Novak, R., Xiao, L., Lee, J., Bahri, Y., Yang, G., Hron, J., Abolafia, D. A., Pennington, J., and Sohl-Dickstein, J. (2018). Bayesian
deep convolutional networks with many channels are gaussian processes. arXiv preprint arXiv:1810.05148.

Ortiz-Jiménez, G., Modas, A., Moosavi-Dezfooli, S.-M., and Frossard, P. (2020). Optimism in the face of adversity: Understanding
and improving deep learning through adversarial robustness. arXiv preprint arXiv:2010.09624.

You, J., Leskovec, J., He, K., and Xie, S. (2020). Graph structure of neural networks. In International Conference on Machine
Learning, pages 10881–10891. PMLR.

Yuan, K., Li, Q., Zhou, Y., Shao, J., and Yan, J. (2020). Diving into optimization of topology in neural networks.

Zdeborová, L. (2020). Understanding deep learning is also a job for physicists. Nature Physics, 16(6):602–604.

Zhou, P., Feng, J., Ma, C., Xiong, C., Hoi, S., et al. (2020). Towards theoretically understanding why sgd generalizes better than
adam in deep learning. arXiv preprint arXiv:2010.05627.