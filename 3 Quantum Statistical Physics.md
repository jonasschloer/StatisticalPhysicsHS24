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

## 3.4.2 Spin S - classical limit

Now larger wuantum spins with magnitude $S=\hbar s$ with $s \in \{\text{Integer or half integer}\}$. Hilbert space contains $2s+1$ basis states $\{|s,s_{z}\rangle\} = \{|s,-s \rangle ,|s, -s+1\rangle, \dots, |s,s \rangle\}$.
- Have operators for *total spin* $\hat{\mathbf{S}}^{2}|s,s_{z}\rangle = \hbar^{2}s(s+1)|s,s_{z}\rangle$ and *spin projection operator* $\hat{S}_{z} |s,s_{z}\rangle = \hbar s_{z} |s,s_{z}\rangle$.

Apply magnetic field in parallel $z$-direction of the N independent spins. 
- **Hamiltonian** $$\mathcal H = -\frac{g\mu_{B}}{\hbar } \sum_{i=1}^{N} \hat{\mathbf{S}}\cdot \mathbf{H} = -\frac{g\mu_{B}}{\hbar} \sum^{N}\hat{S}_{i}^{z}H$$
- **Partition function** $$\begin{align}
Z &= \text{Tr} \left\{ e^{-\beta \mathcal{H}} \right\}  \\
&= \text{Tr} \left\{ \bigotimes_{i=1}^{N} e^{\beta g \mu_B H \hat{S}_i^z / \hbar} \right\} 
&&\quad \text{| Hamiltonian is diagonal in \( \hat{S}^z \), trace factorizes over \( N \) particles} \\
&= \left( \sum_{s_z=-s}^{s} \langle s, s_z | e^{\beta g \mu_B H \hat{S}^z / \hbar} | s, s_z \rangle \right)^N 
&&\quad \text{| Trace becomes sum over spin states \( |s, s_z\rangle \)} \\
&= \left( \sum_{s_z = -s}^{s} e^{\beta g \mu_B H s_z} \right)^N 
&&\quad \text{| Eigenvalue of \( \hat{S}^z \) is \( s_z \), in units of \( \hbar = 1 \)} \\
&= \left( e^{-\beta g \mu_B H s} \sum_{n=0}^{2s} e^{\beta g \mu_B H n} \right)^N 
&&\quad \text{| Rewriting sum over \( s_z = -s + n \), for \( n = 0 \ldots 2s \)} \\
&= \left( \frac{ e^{-\beta g \mu_B H s} \left( e^{\beta g \mu_B H (2s+1)} - 1 \right)}{e^{\beta g \mu_B H} - 1} \right)^N 
&&\quad \text{| Geometric series: \( \sum_{n=0}^{k} x^n = \frac{x^{k+1}-1}{x-1} \)} \\
&= \left( \frac{ \sinh \left( \beta \mu_B H (2s+1)/2 \right) }{ \sinh \left( \beta \mu_B H /2 \right) } \right)^N 
&&\quad \text{| Final closed form using identity: \( \sinh(nx)/\sinh(x) \) from exponential sums}

\end{align}$$
- **Free energy** $$F=-Nk_{B}T\log \{\frac{\sinh(\beta \mu_{B}H(2s+1))}{\sinh(\beta \mu_{B}H)}\}$$
	- reduces to result from [[#3.4.1 Spin 1/2]].
- **Internal energy**$$U=-N\mu_{B}H\{(2s+1) \coth(\beta \mu_{B}H(2s+1)) - \coth(\beta \mu_{B}H)\} = -N \mu_{B}H_{2}sB_{s}(\beta \mu_{B}H)$$
	- with *Brillouin function* ... (page 39)
- **Heat capacity**: $C_{V} = \frac{ d U }{ d T }$ in quantum formulation approaches classical heat capacity as spin $s$ increases: ![[QuantumHeatCapacity.png|500]]
- **Magnetization**: Expressed with Brillouin function $$M_{z} = g\mu_{B}\sum^{N} \langle  \hat{S}_{i}^{z} \rangle  = N \mu_{B}2sB_{s}(\beta \mu_{B}H)$$
	- identify **internal enery** now as $U=-M_{z}H$
	- Other components vanish $M_{x} = M_{y}=0$

- *Classical Limit:* Get classical result for $s \gg{1}$: #ToDo page 40 footnote
	- now simultaneously fix $2s\mu_{B}=m$ to be finite and take *high-temperature limit* $k_{B}T \gg mH$ to find
		- Free energy $F=-Nk_{B}T \log{2}s$
		- Entropy $S=Nk_{B}\log 2s$ (same as $S_{0}$ in classical case)
	- *low-temperature limit*: Find 2 regimes:  
		- $2sk_{B}T \gg mH \gg k_{B}T:$ find essentially low-temperature classical regime solution
		- $mh \gg 2sk_{B}T:$ obtain wuantum limit. The quantum range shrinks for increasing $s$.

___
# 3.5 Ideal quantum gas - grand canonical ensemble

Important factor in gas of independent quantum particles: Classified in Fermions (follow Pauli principle, cannot find two of them in the same state) and Bosons (no restrictions).
Many-particle systems of Bosins is described by completely symmetric wavefunction under pairwise exchange. System of Fermions is completely antisymmetric. Discuss later in next chapter #ToDo link

Free particles represented by plane waves: $$\psi_{\mathbf p}(\mathbf{r}) = \langle  \mathbf{ r} | \psi_{\mathbf{ p}} \rangle  = \frac{1}{\sqrt{ V }} e^{i\mathbf{p}\cdot \mathbf{r}\frac{1}{\hbar r}} \quad\text{with}\quad\epsilon_{\mathbf{p}}=\frac{\mathbf{p}^{2}}{2m}$$
Introduce periodic boundary conditions and wuantize the momentum quantum number:
- Assume subic system with $V=L^3$. 
- Wavefunciton satisfies $\psi_{p}(r+(L,0,0)) = \dots=\psi_{p}(r)$ if $p=\frac{2\pi \hbar}{L}(n_{x},n_{y},n_{z}) = \frac{h}{L}(n_{x},n_{y},{n_{z}})\quad\text{with}\quad n\in \mathbb{Z}$
	- $\Rightarrow$ periodic boundary conditions lead to *momentum quantization*

 **Grand partition function** for such a gas: $$\mathcal  Z=\sum_{\{n_{\mathbf{p}}\}} g_{\{n_{p}\}}e^{-\beta(E-\mu N)_{\{n_{p}\}}} \quad\text{with}\quad E=\sum_{p}\epsilon_{p}n_{p}, \quad N=\sum_{p}n_{p}$$
 - $n_{p}$ is *occupation number* (= number of particles per state). Sum runs over all allowed configurations of occupations. 
 - Factor $g_{\{n_{p}\}}$ is 1 for indistinguishable particles (Fermions and Bosons) and $\prod_{p} \frac{1}{n_{p}!}$ for classical particles (Boltzmann) #clarify I still dont understand the difference...
- Each many-particle quantum state for indistinguishable particles includes all permutations through the total symmtryzation (Bosons) or antisymmetrization (Fermions) of the wavefunction #clarify what?
	- Fermions have occupation number $n_{p}\in \{0,1\}$ for each state and Bosons $n_{p}=0,1,2,\dots$

**Partition function**: With fugacity $z=e^{\beta \mu}$ have  $$\begin{align}
\mathcal Z&= \sum_{n_{p_{1}},n_{p_{2}},\dots} [\{z e^{-\beta \epsilon_{p_{1}}}\}^{n_{p_{1}}} \cdot\{z e^{-\beta \epsilon_{p_{2}}}\}^{n_{p_{2}}}\cdot \dots] && \text{sum over occupation number configurations}\\
&=\prod_{p}\sum_{n_{p}}(z e^{-\beta\epsilon_{p}})^{n_{p}} && \text{non-interacting}\\
&=\begin{cases}
\prod_{p}(1+ ze^{-\beta\epsilon_{p}}) &\text{Fermions} \\
\prod_{p}  \frac{1}{(1+ ze^{-\beta\epsilon_{p}})} &\text{Bosons}
\end{cases}
\end{align}$$
**Equation of state** from partition function: $$\frac{pV}{k_{B}T}=-\beta \Omega(T,V,\mu) = \begin{cases}
~~~\sum_{p}\log(1+ze^{-\beta\epsilon_{p}}) &\text{Fermions} \\
-\sum_{p} \log(1-ze^{-\beta\epsilon_{p}}) &\text{Bosons}
\end{cases}$$
**Particle number:** $$N=z \frac{ \partial  }{ \partial z } \log \mathcal Z = \begin{cases}
\sum_{p} \frac{1}{e^{\beta\epsilon_{p}}z^{-1}+1} &\text{Fermions} \\
\sum_{p} \frac{1}{e^{\beta\epsilon_{p}}z^{-1}-1} &\text{Bosons}
\end{cases}$$
**Occupation number of a state** $$\langle n_{p}\rangle  = \dots=-k_{B}T \frac{ \partial  }{ \partial \epsilon_{p} } \log \mathcal Z=\begin{cases}
\frac{1}{z^{-1}e^{\beta\epsilon_{p}}+1} &\text{Fermions} \\
\frac{1}{z^{-1}e^{\beta\epsilon_{p}-1}}&\text{Bosons}
\end{cases}$$
- Correspond to *Fermi-Dirac* and *Bose-Einstein* distirbutions #clarify

**Grand potential** (plus for Fermions, minus for Bosons): $$\Omega = \dots=-\frac{2}{3} V \frac{1}{8\pi^{2}} \left( \frac{2m}{\hbar^{2}} \right)^{\frac{3}{2}} \int_{0}^{\infty}  \frac{\epsilon^{\frac{3}{2}}}{z^{-1}e^{\beta\epsilon} \pm 1}  d\epsilon$$
- used *density of states* for energy integration $g(\epsilon ) = \sum_{p}\delta(\epsilon-\epsilon_{p}) = V \frac{1}{8\pi^{2}}\left( \frac{2m}{\hbar^{2}} \right)^{\frac{3}{2}}\epsilon^{1/2}$

**Internal Energy $$U=\sum_{p}\langle n_{p} \rangle  \epsilon_{p} = \int_{0}^{\infty} g(\epsilon) \frac{\epsilon}{z^{-1}e^{\beta \epsilon}\pm 1}d\epsilon = V \frac{1}{8\pi^{2}} \left( \frac{2m}{\hbar^{2}} \right)^{\frac{3}{2}}  \int_{0}^{\infty} \frac{\epsilon^{3/2}}{z^{-1} e^{\beta \epsilon}\pm 1}d\epsilon$$
- From $\Omega=-pV$ obtain general relation: $U=\frac{3}{2}pV$
- So far *did not include spin* s of particles in considerations! Introduces another factor $2s+1$ to $\Omega$ and $U$.

#Insights: 
- This is base model for understanding other quantum gases
	-  Fermi gas in metals (Fermions)
	- Photon or phonon gases or Bose-Einstein condensates (Bosons)
- Can derive other quantities from these equations
	- Heat capacity
	- compressibility
	- chemical potential
	- Need to be able to compare this to classic Boltzmann Gas [[2 Classical Statistical Physics#2.4.2 Ideal gas - grand canonical treatment]]  #ToDo  .


# 3.6 Fermi gas

Consider now Fermions with spin $s$. Have $2s+1$ different species. 
Use relation $\sum_{p}=\frac{V}{\hbar^{3}} \int d^{3}p$ from page 42 to get
- **equation of state** $$\frac{p}{k_{B}T} = \frac{4\pi}{h^{3}}(2s+1) \int_{0}^{\infty} p^{2}\log(1+ze^{-\beta \epsilon_{p }}) dp$$
- **particle number** (general expression) $$n = \frac{1}{v} = \frac{N}{V}= \frac{4\pi}{h^{3}} (2s+1) \int_{0}^{\infty} p^{2} \frac{1}{z^{-1}e^{\beta \epsilon_{p}}+1} dp$$
- 
Use *Fermi-Dirac integrals* (with apparently interesting limits #ToDo) $$\begin{align}
f_{\frac{5}{2}}(z) &= -\sum_{l=1}^{\infty}(-1)^{l} \frac{z^{l}}{l^{\frac{5}{2}}} \quad\lim_{z \gg_{1}} \dots \text{page 43}\\
f_{\frac{3}{2}}(z) &= -\sum_{l=1}^{\infty}(-1)^{l} \frac{z^{l}}{l^{\frac{3}{2}}}
\end{align}$$
- Espress above with the *thermal de Broglie wavelength* $\lambda=  h/ \sqrt{ 2\pi mk_{B}T }$ as $$\begin{align}
\frac{p}{k_{B}T}&=\frac{2s+1}{\lambda^{3}} f_{\frac{5}{2}}(z) \\
n = \frac{1}{v} &= \frac{2s+1}{\lambda^{3}} f_{\frac{3}{2}}(z)
\end{align}$$
## 3.6.1 High-temperature and low-density limit

Low density (= and high temperature), implies $\lambda^{3}n \ll{1}$ and $z=e^{\beta \mu} \ll 1$.
- From special functions limits: $\lambda^{3}n = (2s+1)\left\{ z - \frac{z^{2}}{2^{\frac{3}{2}}} +\dots\right\} \Rightarrow z=\frac{\lambda^{3}n}{2s+1} + \frac{(\lambda^{3}n)^{2}}{2^{\frac{3}{2}}(2s+1)^{2}}+\dots$
- **Equation of state** in high-temperature limit: $$\frac{p}{k_{B}T}\approx\frac{2s+1}{\lambda^{3}} \left\{ z - \frac{z^{2}}{2^{\frac{5}{2}}} \right\}\approx \frac{N}{V} \left\{ 1+ \underbrace{\frac{\lambda^{3}n}{2^{\frac{5}{3}}(2s+1)}}_{\begin{align} \text{quantum correction to}  \\
\text{classical ideal gas limit}
\end{align}}    \right\}$$
	- Compare to [[2 Classical Statistical Physics#2.4.2 Ideal gas - grand canonical treatment]] 
	- pressure increases due to Pauli exclusion principle
- **Isothermal compressibility** $$\kappa_{T}=-\frac{1}{V} \left( \frac{ \partial V }{ \partial p }  \right)_{T,N} = \frac{V}{Nk_{B}T} \left\{  1+ \frac{\lambda^{3}n}{2^{\frac{5}{2}}(2s+1)}  \right\}$$
	- Compared to [[2 Classical Statistical Physics#2.5.2 Particle number]], see that compressibility is reduced in quantum correction. Is consequence of Pauli exclusion principle, as Fermions avoid each other #clarify 
- **Occupation number** $$\langle n_{p}\rangle = \frac{1}{z^{-1}e^{\beta \epsilon_{p}} +1} \approx ze^{-\beta \epsilon_{p}} \approx \frac{\lambda^{3}n}{2s+1} e^{-\beta \epsilon_{p}} = \frac{1}{2s+1} \frac{nh^{3}}{(2\pi mk_{B}T)^{\frac{3}{2}}} e^{-\beta \epsilon_{p }}$$
	- Corresponds to *Maxwell-Boltzman distribution* per spin #clarify #ToDo Link
- **Internal Energy** $$U \approx \frac{3}{2} Nk_{B}T \left\{  1 + \frac{\lambda^{3}n}{2^{\frac{5}{3}}(2s+1)} \right\}$$
- **Heat capacity** $$C_{V} = \frac{3}{2} N k_{B} \left\{ 1- \frac{\lambda^{3}n}{2^{\frac{7}{2}}(2s+1)} \right\}$$

## 3.6.2 Low-temperature and high-density limit: degenerate Fermi gas
At low temperatures, reach "quantum limit": $\lambda^{3}n \gg 1$, implying *large fugacity* $z$.

### Zero temperature
Occupation numbers follow step function: $$\langle  n_{p}\rangle  = \Theta(\mu-\epsilon_{p}) = \begin{cases}
1,&\epsilon_{p} \lt \mu \\
0,&\epsilon \gt \mu
\end{cases}$$
- $\Rightarrow$ all states up to fermi energy are filled

Fermions occupy *Fermi sphere* in momentum space. **Particle density** is $$n=\frac{N}{V} = 2s+\frac{1}{h^{3}} \int \langle  n_{p}\rangle d^{3}p  =  2s+\frac{1}{h^{3}} \frac{4\pi}{3} p_{F}^{3} = \frac{(2s+1)k_{F}^{3}}{6\pi^{2}},$$with *isotropic Fermi momentum* $\epsilon_{F}= \epsilon_{p_{F}}=\mu(T=0)$ and *Fermi wavevector* $k_{F}=\frac{p_{F}}{\hbar}$

**(Ground state) internal energy** $$U_{0} = \frac{2s+1}{h^{3}} V\int \epsilon_{p}\langle  n_{p }\rangle  d^{3}p  =  \frac{2s+1}{h^{3}} 4\pi V\int p^{2}\frac{p^{2}}{2m}dp = \frac{2s+1}{h^{3}} \frac{4\pi V}{5} p_{F}^{3} \frac{p_{F}^{2}}{2m} = \frac{3}{5} N\epsilon_{F}$$with *Fermi energy* $\epsilon_{F}$. 

**zero-point pressure** obtained from [[#3.5 Ideal quantum gas - grand canonical ensemble|general internal energy]]: $p_{0}=\frac{2}{3} \frac{U_{0}}{V}=\frac{2}{5} \frac{N}{V} \epsilon_{F}$
- Unlike [[2 Classical Statistical Physics#2.3.3 Ideal gas - canonical treatment|classical ideal gas]], where pressure is 0 at zero-point, Fermi gas has finite zero-point pressure. This is a consequence of pauli principle and responsible forthe stability of metals and neutron stars. 

### Finite temperatures
Occupation number broadens the fermi pressure step. 
Use special functions and particle density from above to get $$\left( \frac{\epsilon_{F}}{k_{B}T} \right)^{\frac{3}{2}} = \frac{3}{4}  \frac{\sqrt{ \pi }\lambda^{3}}{2s+1} \frac{N}{V} = \left( \frac{\mu}{k_{B}T} \right)^{\frac{3}{2}} + \frac{\pi^{2}}{8}\left( \frac{\mu}{k_{B}T} \right)^{- \frac{1}{2}}+\dots$$

- For constatnt density $n=\frac{N}{V}$, can solve for **chemical potential** $$\mu(T) = \epsilon_{F}\left(  1- \frac{\pi^{2}}{12} \left( \frac{k_{B}T}{\epsilon_{F}} \right)^{2}+\dots \right)$$
- analogously, obtain for **pressure** $$p(T) = p_{0}\left(  1 + \frac{5\pi^{2}}{12} \left( \frac{k_{B}T}{\epsilon_{F}} \right)^{2}+\dots\right)$$
- **internal energy** from $U=\frac{3}{2}pV$: $$U = \frac{3}{2}pV=U_{0}\left( 1+ \frac{5\pi^{2}}{12}\left( \frac{k_{B}T}{\epsilon_{F}} \right)^{2}+\dots \right)$$
- From this, derive **heat capacity** for fixed N: $$C_{V}=\left( \frac{ \partial U }{ \partial T }  \right)_{V,N} = \frac{5\pi^{2}}{6} U_{0} \frac{k_{B}^{2}T}{\epsilon_{F}^{2}}+\dots=\frac{\pi^{2}}{2} k_{B}^{2}\frac{N}{\epsilon_{F}}T+\dots \propto T$$
	- Famous linear temperature dependence of the heat capacity. Observe for electrons in simple metals $C_{V}=\gamma T+\dots$ for *Sommerfeld coefficient* $\gamma$.
	- Now third law of thermodynamics is satisfied: $C_{N} \lim_{T\to{0}}0$ 
	- Also, entropy goes linearly to zero
- ![[quantumComparison-internalEnergyAndHeatCapacity.png]]
___
#Insights 
- In *classical limit*, Fermi gas behaves like ideal gas with small quantum corrections (where is this?)
- in *quantum limit*, Pauli exclusion principle dominates: 
	- Fermions fill all states up to Fermi level
	- System resists compression and has nonzero zero-point pressure and energy
- Transition between both regimes controlled by dimensionless parameter $\lambda^{3}n$
- Fermi gas is standard model conduction electrons in metals and neutron star matter at high densities

## 3.6.3 Spin 1/2 Fermions in a magnetic field - Ideal paramagnetic gas

*Ideal paramagnetic gas* = spin $s=\frac{1}{2}$ Fermions in magetic field. Hamiltonian with field along z-axis needs to be expanded by *Zeeman term*: $$\mathcal H_{Z}=-\frac{g\mu_{B}}{\hbar}\sum_{i=1}^{N} s_{i}^{z}H$$

Absorb energy difference between spins parallel and antiparallel to applied field into *spin-dependent fugacity*: $$z_{\pm} = e^{\beta \mu\pm \beta \mu_{B}H}$$
- **particle density** now given as $$n=\frac{N}{V}=\frac{1}{v}=\frac{1}{\lambda^{3}} \left\{  f_{\frac{3}{2}} (z_{+}) + f_{\frac{3}{2}}(z_{-})  \right\}=: n_{+}+n_{-}$$
- **magnetization** $$m=\frac{M}{V} = \mu_{B}(n_{+}-n_{-}) = \frac{\mu_{B}}{\lambda^{3}} \left\{   f_{\frac{3}{2}}(z_{+}) - f_{\frac{3}{2}}(z_{-})   \right\}$$
- **Spin susceptibility** for *zero magnetic field* with $z=e^{\beta \mu}$: $$\chi = \frac{ \partial m }{ \partial H } \bigg|_{H=0} = \frac{\mu_{B}^{2}}{\lambda^{3}k_{B}T} 2z \frac{ \partial f_{\frac{3}{2}}(z) }{ \partial z } \bigg|_{H=0} = \frac{2\mu_{B}^{2}}{\lambda^{3}k_{B}T} f_{\frac{1}{2}}(z)$$
	- *High-temperature limit*: Replace $z \ll 1$ with expression from [[#3.6.1 High-temperature and low-density limit]] and find $$\chi= \mu_{B}^{2} \frac{n}{k_{B}T} \left\{ 1- \frac{\lambda^{3}n}{2^{5/2}} \right\}$$
		- First term is for particles with spin and behaves like *Curie* #ToDo link
		- Second term is quantim correction and reduces susceptibility
- *Low-temperature limit*: Take only lowest order for $z \gg 1$ and obtain $$\chi= \frac{\mu_{B}^{2}}{\lambda^{3}k_{B}T} \frac{4}{\sqrt{ \pi }} (\log z)^{\frac{1}{2}} =  \frac{\mu_{B}^{2}}{\lambda^{3}k_{B}T} \frac{4}{\sqrt{ \pi }} \left( \frac{\epsilon_{F}}{k_{B}T} \right)^{\frac{1}{2}} = \mu_{B}^{2} \frac{3n}{2\epsilon_{F}}$$
	- Famous *Pauli spin susceptibility for a fermi gas*. Is temperature independent.

___
# 3.7 Bose gas
