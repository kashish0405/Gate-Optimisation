# Quantum Computing
## Optimising Quantum Gates
 
Existing quantum programming languages and compilers use a quantum assembly language composed of 1- and 2-qubit gates.

Quantum compiler frameworks translate this quantum assembly to electric signals (called control pulses) that implement the specified computation on specific physical devices.

There is a mismatch between the operations defined by the 1- and 2-qubit logical ISA and their underlying physical implementation, so the current practice of directly translating logical instructions into control pulses results in inefficient, high-latency programs. <br/>
**Reducing latency** will prove to be an important contributor in enabling quantum computing applications.

## Aim of the Project - 
The aim of my project was to optimise in particular swap gate using QOC (Creating custom control pulses optimized for the aggregate (instead of individual 1- and 2-qubit operations)) 

### Why Swap Gate?
IBM Q (and other machines) do not provide full connectivity among qubits. Thus Swap gates are required to move qubit state where it is needed. Hence it becomes an important gate whose optimised compilation is relatively unexplored.
![image](https://user-images.githubusercontent.com/58369459/137583439-25d21134-fa13-44ed-9d36-ee0459a55765.png)

### Traditional Gate Based Compiler Approach 
In traditional gate based compiler approach, programs are compiled into quantum assembly instructions (or gates) that specify 1- and 2-qubit operations. This quantum assembly is a virtual ISA which represents a rich set of operations. These gates must then be translated into control pulses—the electrical signals that implement the specified operations on the underlying physical hardware.
<p align ="center">
<img src="https://user-images.githubusercontent.com/58369459/137583535-2c5d60d0-8173-449d-98b1-4e6cf0f90ecb.png">
</p>

### Our Approach
Our method it uses quantum optimal control on the aggregates to produce a set of control pulses that is optimized for the underlying physical architecture.
Quantum computing systems can be continuously driven by external physical operations to any state in the space spanned by the logical states. The physical operations, called control fields, are specific to the underlying system, with control fields and system characteristics controlling a unique and time-dependent quantity called the Hamiltonian. The Hamiltonian determines the evolution path of the quantum states.

The ability to engineer the system Hamiltonian in real-time allows us to direct the qubits to the quantum state of interest through precise control of related control fields. Thus, quantum computing is achieved by constructing a quantum system in which the Hamiltonian evolves in a way that aligns with a computational task, yielding the desired result with high probability upon final measurement of the qubit system.
Quantum optimal control algorithms find the optimal evolution path from a starting quantum state to a final quantum state, typically by performing gradient descent methods, such as the GRadient Ascent Pulse Engineering (GRAPE) algorithm.




### References
- Gokhale, P., Javadi-Abhari, A., Earnest, N., Shi, Y., & Chong, F. T. (2020). Optimized quantum compilation for near-term algorithms with OpenPulse. In arXiv [quant-ph]. http://arxiv.org/abs/2004.11205

- Shi, Y., Leung, N., Gokhale, P., Rossi, Z., Schuster, D. I., Hoffman, H., & Chong, F. T. (2019). Optimized compilation of aggregated instructions for realistic quantum computers. In arXiv [quant-ph]. http://arxiv.org/abs/1902.01474

- Alexander, T., Kanazawa, N., Egger, D. J., Capelluto, L., Wood, C. J., Javadi-Abhari, A., & McKay, D. (2020). Qiskit Pulse: Programming quantum computers through the cloud with pulses. In arXiv [quant-ph]. http://arxiv.org/abs/2004.06755

- Qiskit Learn. (n.d.). Qiskit.Org. https://qiskit.org/learn/

- QuTiP - Quantum Toolbox in Python. Qutip.Org. https://qutip.org/tutorials.html







 
 
