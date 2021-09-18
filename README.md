# Estimating Runtimes of Variational Quantum Algorithms
## Problem statement
Write a program that estimates how long running a variational quantum algorithm might take.

It should take the following data as input:
- Circuit (might be a circuit created in some popular framework, QASM file or some other format),
- Number of circuit evaluations per iteration,
- Number of iterations of the optimization loop,
- Device information – information about the device being used (e.g. execution times of the gates),
- Any additional information that you think is relevant.

An example of a simple, but not very accurate formula would be:

Total runtime = (N_1 * t_1 + N_2 * t_2) * n_s * n_i

Where:\
N_1, N_2 – number of 1-qubit (or 2) gates\
t_1, t_2 – time of execution of 1-qubit (or 2) gates\
n_s – number of samples per iteration\
n_i – number of iterations

Note that this doesn’t take into account that certain gates can be executed in parallel.

This task is pretty open-ended – please try to make your formula as realistic as possible. It will require some investigation and review of existing literature or technical documentation on your own, which might turn out to be much more challenging than it seems, but we hope also much more rewarding :)

Once this is done, you can try analyzing some numerical data from the existing research in order and see how long running such a circuit took (if done on a real device) or could take (if data comes from a simulation).

Some papers with data about the quantum computing devices:
- [N. Lacroix et al.](https://journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.1.020304) (ETH), see Table I
- [Arute et al., supplementary information](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-019-1666-5/MediaObjects/41586_2019_1666_MOESM1_ESM.pdf) (Google)
- [Superconducting Qubits: current state of play](https://arxiv.org/abs/1905.13641) (Review)
- [Materials challenges and opportunities for quantum computing hardware](https://www.science.org/doi/10.1126/science.abb2823) (behind paywall :( )
- You can often find specific information about quantum devices on the website of the companies building quantum hardware/software.\
(Please send us other references if you know them, we’ll add them here!)

Review paper on Variational Quantum Algorithms to look for factors that may contribute to longer runtimes:
- [1st review paper](https://arxiv.org/abs/2012.09265)
- [2nd review paper](https://arxiv.org/abs/2101.08448)

## VQAs
**Variational Quantum Algorithm (VQA)**: An algorithm that employs a classical optimizer to train *a parametrized quantum circuit*, with the purpose of approximating answers to a given problem. [[1](https://www.ibm.com/blogs/research/2021/01/quantum-mean-values/)]

> Variational quantum algorithms (VQAs) are the leading proposal for achieving quantum advantage using near-term quantum computers.

> The runtime of our classical simulation algorithm has a favorable, linear scaling with the number of qubits, meaning that the time it takes to solve the problem is equal to the number of qubits times a constant. However, adding more gates greatly increases the simulation’s runtime. [[3](https://www.ibm.com/blogs/research/2021/01/quantum-mean-values/)]

### To read:
[Variational Quantum Algorithms – How do they work?](https://www.mustythoughts.com/vqas-how-do-they-work) \
[VQAs - challenges and state of research](https://www.mustythoughts.com/vqas-challenges.html) \
[Variational Quantum Algorithms](https://arxiv.org/pdf/2012.09265.pdf) \
[Minimizing estimation runtime on noisy quantum computers](https://arxiv.org/abs/2006.09350) \
[Noisy intermediate-scale quantum (NISQ) algorithms](https://arxiv.org/abs/2101.08448) \
[Classical algorithms for quantum mean values](https://arxiv.org/pdf/1909.11485.pdf) \
[Holographic quantum simulation - Isaac H. Kim](https://arxiv.org/pdf/1702.02093.pdf) (off-topic)