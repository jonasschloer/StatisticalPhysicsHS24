---
noteID: 977e1758-efd4-4cf6-9f1d-7981ca4b334f
---
___

Opens door to new phenomena and explains third law of thermodynamics (*As the temperature of a system approaches absolute zero (0 K), the entropy of a perfect crystalline substance approaches zero*). 
Also for ideal quantim gases, indistinguishability leads to classsification into Bosons and Fermions

# 3.1 Basis of quantum statisctical physics
___

Every state of quantum mechanical system described by superposition of hamiltionian, forming complete or orthonormal basis, where $c_{n}$ represent the wavefunction whose time dependence is determined by hamiltonian: $$| \Psi \rangle =\sum_{n} c_{n} |\psi_{n}\rangle $$
For stationary states, this holds: $$\mathcal H |\psi_{n} \rangle  = \epsilon_{n} |\psi_{n}\rangle \quad\text{with}\quad \langle  \psi_{n}|\psi_{n}'\rangle =\delta_{nn'}\quad \text{and}\quad 1=\sum_{n} |\psi_{n}\rangle \langle \psi_{n}' |$$
- Normalization requires $\sum_{n} |c_{n}|^{2}$.
- $|c_{n}|^{2}$ is the probbaility of finding a state $|\phi_{n}\rangle$ in $|\Psi\rangle$

Observable quantities represented by *hermitian operators* $\hat{A}^\dagger=\hat{A}$ or $\langle\psi|\hat{A}\phi \rangle=\langle \hat{A}\psi|\phi \rangle$ with expectation value $$\langle  \Psi|\hat{A}| \Psi \rangle = \sum_{n,n'} c_{n}^{*}c_{n}' \langle \psi_{n}|\hat{A}|\psi_{n'} \rangle $$
- Generally time dependent through wavefunction $c_{n}=c_{n}(t)=c_{n}(0)e^{-i\epsilon_{n}t/\hbar}$

## Measurement of macroscopic variable
Measure as *average over long time*: $$\langle  \hat{A}\rangle = \overline{\langle \Psi|\hat{A}|\Psi\rangle }  =  \lim_{T\to \infty} \frac{1}{T} \int_{0}^{T}  \sum_{n,n'} c_{n}^{*}(t) c_{n'}(t) \langle  \psi_{n}|\hat{A}|\psi_{n}\rangle  dt = \sum_{n,n'} \overline{c_{n}^{*}c_{n'}^{*}} \langle  \psi_{n}|\hat{A}|\psi_{n'}\rangle $$
- Since dynamics follow time evolution, the state $|\Psi\rangle$ has fixed energy $E_{\Psi}= \sum_{n} |c_{n}(t)|^{2}\epsilon_{n}$

Can also view as *average over ensemble* of equivalent states: $$\langle  \hat{A}\rangle  = \sum_{n,n'} \rho_{n,n'} \langle  \psi_{n}| \hat{A} | \psi_{n'}\rangle $$
- $\rho_{nn'}=\overline{c_{n}^{*}c_{n}} = \lim_{T \to \infty} \frac{1}{T} \int_{0}^{T}  c_{n}^{*}(0)c_{n'}(0) e^{i\epsilon_{n} - \frac{\epsilon_{n'}t}{\hbar} } dt= |c_{n}^{*}c_{n}|\delta_{nn'}$
- Since all terms with $n \neq n'$ vanish, sum only over $n$. => There is no interference between different member systems of a given ensemble

## Postulates of quantum statistical physics

**Equal Probability:** $$\overline{c_{n}^{*}c_{n}} = \begin{cases}
r,\quad E \le \epsilon_{n} \le E+\delta E \quad \text{with}\quad r \in \mathbb R \\ 0, \quad \text{else}
\end{cases}$$
**Random Phase:** The phase of the wavefunction is a random variable. Requires at least weak coupling to the environment to randomize the phases: $$\overline{c_{n}^{*}c_{n}} = 0 \quad\text{if}\quad n \neq n'$$
As result of this, consider system as effectively described by a wavefunction $b_{n}$ with random phase: $$|\Psi\rangle_{eff} = \sum_{n} b_{n}|\psi_{n}\rangle \quad\text{with}\quad |b_{n}|^{2}= \begin{cases}
1 \quad E \le \epsilon_{n} \le E+\delta E \\ 0 \quad \text{else}
\end{cases}$$

Consider average values as expectation values, where each eigenstate in the energy range appears with the same probability: $$\langle \hat{A}\rangle  = \frac{\sum_{n} |b_{n}|^{2}\langle \psi_{n}|\hat{A}|\psi_{n}\rangle }{\sum_{n} |b_{n}|^{2}}$$
___
# 3.2 Density matrix
___

Mixed states or incoherent superpositions #clarify described by density matrices $\hat{\rho}$, defined as an operator through its matrix elements $$\langle \psi_{n}|\hat{\rho}|\psi_{n'}\rangle = \rho_{nn'} = |c_{n}|^{2}\delta_{nn'}$$
- For stationary states, this matrix is diagonal. Write in specral form as $\hat{\rho} = \sum_{n} |c_{n}|^{2}|\psi_{n}\rangle\langle\psi_{n}|$

Can express average of observable via trace $$\langle \hat{A} \rangle = \frac{ \sum_n \langle \psi_n | \hat{A} \hat{\rho} | \psi_n \rangle }{ \sum_n \langle \psi_n | \hat{\rho} | \psi_n \rangle } = \frac{ \mathrm{Tr}(\hat{A} \hat{\rho}) }{ \mathrm{Tr}(\hat{\rho}) }$$
- Is basis independent. Very convenient
- To describe equillibrium properties, $\hat{\rho}$ should not depend on time and commute with the hamiltonian $i \hbar \frac{ \hat{\partial}\rho }{ \partial t }=[H,\hat{\rho}]=0$.
- Compare with Liouville theorem of calssical meachanics #clarify 

## Classical vs. quantom statistical physics

Classical formulation for N gas particles with $\Lambda_{N} = \frac{1}{N! h^{3N}}$.

![[Comparison.png]]

___
# 3.3 Ensembles in quantum states

## 3.3.1 Microcanonical Ensemble - Quantum Statistics

Closed systems that do not exchange energy and particles with the environment. 

Take diagonalized density matrix $\rho_{nn'} = \delta_{nn'} |b_{n}|^{2}$. Consider incoherent state consisting of equally distributed set of states within narrow energy range. $|b_{n}|^{2}$ as in [[#Postulates of quantum statistical physics]].
- *Incoherent* means that there is no phase coherence between the states and all non-diagonal entries of the density matrix are zero. 

The energies $\epsilon_{n}$ are eigenenergies of the stationary states $|\psi_{n}\rangle$ for the hamiltonian. Write the density matrix as $$\hat{\rho} = \sum_{E \le \epsilon_{n} \le E +\delta E} |\psi_{n}\rangle  \langle  \psi_{n}| \quad\text{with}\quad \text{Tr}\hat{\rho} = \sum_{n}\rho_{nn'} = \omega(E),$$ where $\omega(E)$ is the *number of quantum states $|\psi_{n}\rangle$ with energy in the given energy range.* 

Define **entropy** analogously as in [[2 Classical Statistical Physics#2.2.1 Entropy|classical case]] as $$S(E,V)=k_{B} \log \omega(E)$$
- $\omega(E)$ is connected to density of states $g(E)=\frac{ d \Phi(E) }{ d E }$ of the quantum system as $$\Phi(E) = \sum_{\epsilon_{n} \le E} 1 \quad\Rightarrow \quad \omega(E) = \sum_{E \le \epsilon_{n} \le E+\delta E} 1 = \frac{ d \Psi(E) }{ d E } \delta E$$
- Remember, $\Psi(E)$ is total number of eigenstates with $\epsilon_{n} \le E$ and $\omega(E)$ is number of eigenstates in energy range. 
- From the formula for the entropy, can derive the thermodynamics.

## 3.3.2 Canonical Ensemle - Quantum Statistics

System in thermal equillibrium with a reservoir of given temperature $T$. 

Define **density matrix** here as $$\rho(p,q) = e^{-\beta H(p,q)} \quad \to \quad \rho_{nn'} = \delta_{nn'}e^{-\beta\epsilon_{n}}.$$
Define **partition function** as $$Z=\sum_{n} e^{-\beta\epsilon_{n}}= \text{Tr }\hat{\rho} =  e^{-\beta F(T,V,N)}$$ with $F$ the *Helmholtz free energy*.
- Since density matrix can also be written as an operator #clarify(how important is this? -> very important, since allows basis free representation. However, ChatGPT sais there is missing a 1/Z for normalization in the end.) $\hat{\rho}=\sum_{n} |\psi_{n}\rangle e^{-\beta\epsilon_{n}}\langle\psi_{n}| = e^{-\beta H}\sum_{n} |\psi_{n}\rangle\langle\psi_{n}| = e^{-\beta H}$, can express the partition function as $$Z= \text{Tr }e^{-\beta \mathcal H}$$

Average of observables given as $$\langle  \hat{ A} \rangle  = \frac{\text{Tr}(\hat{A} e^{-\beta H})}{ \text{Tr }e^{-\beta H}} = \frac{1}{Z} \text{Tr}(\hat{A}e^{-\beta H})$$
Get thermodynamics from *Helmholtz* free energy $F(T,V,N) = -k_{B}T \log Z$ via [[2 Classical Statistical Physics#2.3.1 Thermodynamics]].

___
## 3.3.3 Grand Canonical Ensemble - Quantum Statistics

Now connect canonical ensemble also to particle reservoir of given chemical potential $\mu$. 

Density matrix reads $$\hat{\rho}=e^{-\beta (H - \mu\hat{N})}$$
Grand canonical partition funciton: $$\mathcal  Z = \text{Tr }e^{-\beta(H-\mu \hat N)} = \sum_{N} z^{N}Z_{N}$$ with the *fugacity* $z=e^{\beta \mu}$.
Leads to *grand potential* $$\Omega(T,V,\mu) = -k_{B}T\log \mathcal Z $$
___

# 3.4 Ideal quantum paramagnet - canonical ensemble

## 3.4.1 Spin 1/2

Consider N quantum spin 1/2 moments (Spin $S=\frac{\hbar}{2}$) where for each spin the hilbert space contains 2 states, $|s,s_{z}\rangle = \left\{ |\frac{1}{2}, \pm \frac{1}{2}\rangle \right\}$ for chosen quantization along the z-axis. 

In a magnetic field, moments are described by the hamiltonian $$\mathcal H = \sum_{i=1}^{N} \mathcal H_{i} = -\frac{\mu_{B}g}{\hbar} \sum_{i=1}^{N}H\cdot \hat{S_{i}} = -\frac{g\mu_{B}}{2} \sum_{i=1}^{N}H \cdot \hat{\sigma}_{i}.$$

 - $\mu_{B}$ is the Bohr magneton and $g=2$ the gyromagnetic ratio.
 - **Pauli Matrices** given as $$\hat\sigma_x = 
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}, \quad
\hat\sigma_y = 
\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}, \quad
\hat\sigma_z = 
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix},$$ with $\sigma_{0}$ the 2x2 unit matrix. 
- Spin states are spinors (+1/2 is (1,0)...)
- Following properties to determine **partition function**: 

$$% Properties and derivation of partition function for spin-1/2 particles
\begin{align}
(a \cdot \hat \sigma)(b \cdot \hat{\sigma}) &= a \cdot b \ \hat{\sigma}^{0} + i(a \times b) \cdot \hat{ \sigma} 
&&\quad \text{| Pauli matrix identity: product splits into scalar and vector parts} \\
(a \cdot \hat{ \sigma})^{2n} &= |a|^{2n} \hat{ \sigma}^{0} 
&&\quad \text{| Even powers reduce to identity times magnitude squared} \\
(a \cdot \hat{ \sigma})^{2n+1} &= |a|^{2n} (a \cdot \hat{ \sigma}) 
&&\quad \text{| Odd powers preserve the operator structure} \\
\text{Tr }\hat{ \sigma} &= 0, \quad\text{Tr }\hat{ \sigma}^{0}=2 
&&\quad \text{| Trace of Pauli matrices vanishes; identity gives 2} \\
\Rightarrow \boxed{Z} &= \text{Tr } e^{-\beta H} = \text{Tr }e^{\beta \mu_{B} \sum_{i} \vec{H} \cdot \hat{ \sigma}_{i}} 
= \left(\text{Tr }e^{\beta \mu_{B} \vec{H} \cdot \hat{ \sigma}} \right)^{N}
&&\quad \text{| Spins are non-interacting: trace factorizes} \\
&= \left[\text{Tr} \left( \hat{ \sigma}^{0} \cosh(\beta \mu_{B} H) 
+ \hat{ \hat{H}} \cdot \hat{ \sigma} \sinh(\beta \mu_{B}H) \right) \right]^{N}  
&&\quad \text{| Use matrix exponential identity for Pauli matrices} \\
&= \boxed{(2\cosh(\beta \mu_{B}|\vec{H}|))^{N}} 
&&\quad \text{| Trace removes Pauli term; only identity part contributes}
\end{align}
$$

- Obtain **free energy**$$F = -Nk_{B}T \log[2 \cosh(\beta \mu_{B}H)] = \begin{cases}
-N\mu_{B}H \quad &k_{B}T \ll\ \mu_{B}H  \\
-Nk_{B}T\log_{2} \quad &k_{B}T \gg \mu_{b}H
\end{cases}$$
	- Interpret as $F=U-TS \rightarrow$ dominated by internal energy U at low and by entropy $S=k_{B}\log_{2}^{N}= Nk_{B}\log_{2}$ in high-temperature limit #Insights 

**Entropy** given as $$S(T) = -\frac{ \partial F }{ \partial T } =Nk_{B}\log[2 \cosh(\beta \mu_{B}H)] - N k_{B}\beta\mu_{B}H \tanh(\beta \mu_{B}H)$$
	- goes to zero for $T\to 0$ and thus satisfies the third law of thermodynamics
	- Measures number of accessible microstates

**Magnetization:** $$\begin{align}
\langle  M_{n}\rangle &=\mu_{B}\sum_{i=1}^{N}\langle  \hat{ n}\cdot \hat{\sigma}_{i}\rangle = \mu_{B}N \langle  \hat{ n}\cdot \hat{ \sigma}_{1}\rangle  \\
&= N \frac{ \text{Tr }(\mu_{B}\hat{n}\cdot \hat{ \sigma} \{  \hat{ \sigma}^{0} \cosh(\beta \mu_{B} H) + \hat{ H} \cdot \hat{ \sigma} \sinh(\beta \mu_{B}H) \} )}{2\cosh(\beta \mu_{B}H)} \\
&= N \hat{n}\cdot \hat{H} \mu_{B} \tanh(\beta \mu_{B}H) \\
\end{align} $$
- $\hat{n}$ is a normal vector and $\hat{H}$ is $\frac{\mathbf{H}}{|H|}$.
- For low $T$, spins align and magnetization is saturated. For high T, magnetization vanishes #Insights 

**Magnetic susceptibility:** Assume a moment along z: $\mathbf{H} \parallel \hat{z}$. Then $$\chi_{zz} = \dots = \frac{\mu_{B}^{2}N}{k_{B}T} \frac{1}{\cosh^{2}(\beta \mu_{B}H)}$$
- For high temperatures ($k_{B}T \gg \mu_{B}H$) yields *Curie-behavior:* $$\chi_{zz}(T)=\frac{\mu_{B}^{2}N}{k_{B}T}$$
	- -> Magnetic susceptibility decreases with higher temperature #Insights
