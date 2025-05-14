---
noteID: 44b57a9a-d206-43cb-a5df-038a7d672f2d
---
Now deal with equillibrium properties of matter. Time is not a variable anymore. Measurements are considered over large ensembles of identical systems. These can be in different microstates but have same external parameters.

___
# 2.1 Gibbsian concept of ensembles
Practical Example: 
Consider gas of N particles. Have 6N dimensional space $\Gamma$ where each point in $\Gamma$ represents a state of the microscopic system.
An infinite number of states in $\Gamma$ are compatible with the same external conditions and would not be distinguishable by macroscopic measurements. 
- Could do temporal average of microscopic variables to calculate macroscopic quantities. However, then would need notion of time
- $\Rightarrow$ Use Gibbs concept of ensembles
- *Ergodicity hypothesis:* Averaging over many identical macroscopic ensembles is equivalent to temporal average. Time evolution leads to all possible states in the ensemble

Density function $\rho(p,q)$ provides measure of density of points in $\Gamma$-space. $(p,q)$ stands for whole state $(p_{1},\dots,p_{3N};q_{1},\dots,q_{3N})$.
- $\rho(p,q)d^{3N}pd^{3N}q$  gives number of representative points in the volume $d^{3N}pd^{3N}q\in \Gamma$ 
- Average of any quantity: $$\langle A \rangle  = \frac{\int A(p,q)\rho(p,q)~dpdq}{\int \rho(p,q)~dpdq}$$
## 2.1.1 Liouville Theorem

Dynamics of system described by Hamiltonian for each particle. Since total numberof points is the same, also have continuity equaiton $$\frac{ d \rho }{ d t } +\nabla \cdot(\rho v)=0$$
- Or with *substantial derivative* $\frac{D\rho}{Dt} + \rho \nabla \cdot v=0$
	- Divergence of velocity is 0, so system behaves like *incompressible fluid* => **Liouville Theorem**. Write as: $$0 = \frac{D\rho}{Dt} = \frac{ \partial \rho }{ \partial t } + \sum_{i=1}^{3N} \left\{  \dot{q_{i}} \frac{ \partial \rho }{ \partial q_{i} }  + \dot{ p_{i}} \frac{ \partial \rho }{ \partial p_{i} }   \right\} =  \frac{ \partial \rho }{ \partial t } + \sum_{i=1}^{3N} \left\{  \frac{ \partial \mathcal{H} }{ \partial p_{i} }  \frac{ \partial \rho }{ \partial q_{i} }  + \frac{ \partial \mathcal{H} }{ \partial q_{i} }  \frac{ \partial \rho }{ \partial p_{i} }   \right\}$$ or with *Poisson Bracket*: $\frac{ \partial \rho }{ \partial t } = \{ \mathcal H ,\rho\}$

### 2.1.2 Equillibrium system

Equillibrium should mean, that density function does not depend on time:$\frac{ \partial \rho }{ \partial t }=0$. From [[#2.1.1 Liouville Theorem|Liouville Theorem]] get $0=\{\cal H, \rho\}$
- Satisfy by taking density funciton that depends only on conserved quantities. Then system evolves in a subspace, where $\rho$ is constant. 

Use this to now look at averages of certain quantities. Have equivalence of temporal and ensemble average in mind. 
Temporal average: $\langle A \rangle = \lim\limits_{T\to\infty} \frac{1}{T} \int_{0}^{\infty} A(\rho(t), q(t)) dt$
- Ergodicity implies that this average can be taken over infinite number of different microscopic states. Since energy is conserved in this evolution, consider an ensemble with fixed (internal) energy -> *microcanonical*. Describes isolated, closed system with no energy exchange with the environment. 

In equillibrium, *any state of a macroscopic system satisfying the external conditions appears with equal probability*. In the time evolution this means that each point in the allowed subspace is equally frequently visited.

Use density function $\rho(p,q) = \text{const} \iff E \le H(p,q) \le E+\delta E$ and 0 otherwise. $\delta E$ is small but large enough to contain a macroscopic number of states.
Approach valid based on assumptions that standard deviation of observable is small $\frac{\langle \{A - \langle A \rangle\}^{2}\rangle}{\langle A \rangle^{2}} \ll 1$

___

# 2.2 Microcanonical Ensemble

System of N particles in volume V which is isolated and closed. Consists of all states where energy lies in the range $[E, E+\delta E]$. First need to define phase space volume $\Phi (E) = \Lambda_{N} \int_{H(p,q)\le E} dpdq$, containing all allowed points in $\Gamma$. $\Lambda_{N}$ is a renormalization factor, compensating for over-counting of individual states by permutation $\Lambda_{N}=\frac{1}{N! h^{3N}}$, where $h$ makes this dimensionless and has units energy.

Volume of microcanonical ensemble:
$$\omega(E) = \Lambda_{N} \int_{\Phi(E)} dpdq = \Phi(E + \delta E) - \Phi(E) = \frac{d\Phi(E)}{dE}\delta E$$
- Normalize density function $\rho(p,q)$ so $1=\Lambda_{N} \int \rho(p,q)dpdq = \frac{\Lambda_{N}}{\omega(E)} \int_{\Phi(E)} dpdq$
- Now $\rho(p,q) = \begin{cases}  \frac{1}{\omega(E))} \quad E \le H(p,q) \le E + \delta E \\ 0 \quad \text{otherwise}  \end{cases}$    is constant in this energy range


## 2.2.1 Entropy
Define $$S(E,V,N) = k_{B} \log \omega(E)$$
- Is measure of the imprecision of our system.
- The more states in the system, the larger the volume $\omega$ and thus the entropy.


### Composite system consisting of 2 subsystems
Composite system consisting of 2 subsystems: $H(p,q)=H_{1}(p_{1}, q_{1}) + H_{2}(p_{2}, q_{2})$ with different volumes and particle numbers: $E=E_{1}+E_{2}, \quad N=N_{1}+N_{2}, \quad V=V_{1}+V_{2}$
- Assume V and N of subsystems are fixed, but energy can be exchanged. 
- Volume of the total system $\omega(E)= \sum_{0\le E' \le E} w_{1}(E')w_{2}(E-E')$, assuming discrete mesh of equally spaces $E'$-values of mesh spacing $\delta E\ll E$.
- Claim (and prove) that this sum is approximated by single value $E_{0}'$. Means that sum is dominated by single term => microstate with largest number of microscopic realizations. 
	- Largest term with equillibrium condition $\frac{ \partial S_{1}E_{1} }{ \partial E_{1} } \bigg|_{E_{1}=E_{0}'} = \frac{ \partial S_{2}E_{2} }{ \partial E_{2} }\bigg|_{E_{2}=E-E_{0}'}$
	
Identify $E$ as internal energy $U$ and define temperature $\frac{ \partial S }{ \partial U }=\frac{1}{T} \Rightarrow \frac{1}{T_{1}} = \frac{1}{T_{2}}$. Other variables N, V ignored for now (see  below #ToDo)

Assume there is something (e.g. a wall) that forces the 2 subsystems to be at their own equillibrium but not the combined system.
- Combined state volume  $\tilde\omega(E,V,N)=\omega_{1}(E_{1}, V_{1}, N_{1})\omega_{2}(E_{2}, V_{2}, N_{2})$
- Entropy $\tilde{S}(E,V,N) = S_{1}(E_{1}, V_{1}, N_{1}) + S_{2}(E_{2}, V_{2}, N_{2}) \le S(E,V,N)$
- $\Rightarrow$ *Entropy is concave*, equillibrium is obtained by maximal entropy. 

## 2.2.2 Relation to Thermodynamics

Can calculate a number of state variables and relations: $$dS = \left( \frac{ \partial S }{ \partial E }  \right)_{V,N}dE + \left( \frac{ \partial S }{ \partial V }  \right)_{E,N} dV + \left( \frac{ \partial S }{ \partial N }  \right)_{E,V}dN = \frac{1}{T} dE + \frac{p}{T}dV - \frac{\mu}{T}dN$$
- $\frac{1}{T} = \left( \frac{ \partial S }{ \partial E }  \right)_{V,N}$ caloric equation of state
- $p=T\left( \frac{ \partial S }{ \partial V }  \right)_{E,N}$ thermodynamic equation of state
- $\mu = -T \left( \frac{ \partial S }{ \partial N }  \right)_{E,V}$ chemical potential

## 2.2.3 Ideal gas - microcanonical treatment

N independent, mnoatomic particles in fixed volume V, closed and isolated. Hamiltonian given as $$H(p,q) = H(p) = \sum_{i=1}^{N} \frac{p_{i}^{2}}{2m}$$
- Volume of microcanonical space is $$\Phi(E) = \Lambda_{N} \int_{H(p) \le E} dpdq = \Lambda_{N}V^{N}\int_{H(p) \le E} dp = \Lambda_{N}V^{N}C_{3N} \sqrt{(2mE)}^{3N},$$where integral is the volume of a 3N-dimensional sphere with radius $R=\sqrt{ 2mE }$ and then $C_{n}=\frac{\pi^{n/2}}{\Gamma\left( \frac{n}{2}+1 \right)}$
- Leads to $$\omega(E) = \frac{ \partial \Phi(E) }{ \partial E } \delta E = \Lambda_{N} C_{3N} V^{N} \frac{3N}{2}  2m(2mE)^\frac{3N}{2-1}\delta E$$
- ! Find that for large N, the following terms are identical up to order $\log N$: $S_{\omega}=k_{B}\log \omega(E,V,N)$ and $S_{\Phi}k_{B} \log \Phi(E,V,N)$
	- Proof: $S_{\omega}= k_{B} \log(\Lambda_{N}V^{N}C_{3N}) + k_{B}\left( \frac{3N}{2} -1 \right) \log(2mE) + k_{B}\log\left( \frac{3N}{2} 2m\delta E \right) = \dots = S_{\Phi} + \mathcal O(\log N)$
- $S(E, V, N) = N k_{\text{B}} \log \left\{ V \left( \frac{2 \pi m E}{h^2} \right)^{3/2} \right\}- \frac{3N}{2} k_{\text{B}} \log \frac{3N}{2}+ \frac{3N}{2} k_{\text{B}}- N k_{\text{B}} \log N + N k_{\text{B}}$  with sterlings formula $\log(N!) \approx n\log n -n + \frac{1}{2} \log(2\pi n)$
- Rewrite $S(E,V,N) = Nk_{b} \log \left\{  \frac{V}{N} \left(  \frac{4\pi mE}{2Nh^{2}}  \right)^{\frac{3}{2}}  \right\} + \frac{5}{2} Nk_{B}$
- Solve for E to obtain internal energy as thermodynamic potential: $$U(S,V,N) = E = N \frac{3n^{\frac{2}{3}}h^{2}}{4\pi m} \exp\left\{  \frac{2S}{3Nk_{B}} - \frac{5}{3}   \right\}$$
### Thermodynamic quantities - microcanonical ensemble
- Obtain thermodynamic quantities from [[#2.2.2 Relation to Thermodynamics]]: 
	- temperature: $T=\left( \frac{ \partial U }{ \partial S } \right)_{V,N} = \frac{2U}{3Nk_{B}} \Rightarrow U=\frac{3}{2} N k_{B} T$
	- pressure: $p=-\left( \frac{ \partial U }{ \partial V } \right)_{S,N} = \frac{2}{3} \frac{U}{V} = \frac{Nk_{B}T}{V} \Rightarrow pV=Nk_{B}T$
	- chemical potential: $\mu = \left( \frac{ \partial U }{ \partial N } \right)_{S,V} = \frac{U}{N}\left( \frac{5}{3} - \frac{2}{3} \frac{S}{Nk_{B}} \right) = -k_{B} T \log\left\{  \frac{V}{N} \left(  \frac{2\pi mk_{B}T}{h^{2}}  \right)^{\frac{3}{2}}  \right\}$
		- only determined up to a constant, since parameter h is independent of density N/V.

### Sterling Formula
$\log(N!) \approx n\log n -n + \frac{1}{2} \log(2\pi n)$


___

# 2.3 Canonical Ensemble

![[Canonical Ensemble.png|Canonical Ensemble - System 1 connected to heat reservoir]]
Control temperature by connecting to very large reservoir. Forms closed system with fixed total energy. Consider as 2 subsystems with one system being the reservoir: $H(p,q) = H_{1}(p_{1}, q_{1}) + H_{2}(p_{2},q_{2})$ with $N_{2} \gg N_{1}$ so heat transfer doesnt change reservoir temperature. 

Work in microcanonical ensemble, similar to [[#Composite system consisting of 2 subsystems]]. This means we look at combined system in energy range $E \le E_{1}+E_{2} \le E+\delta E$.
- The microcanonical volume is $\omega(E)=\sum\limits_{0\le E_{1}\le E} \omega_{1}(E_{1})\omega_{2}(E-E_{1})$.
- Again, have one dominating value in sum $\bar{E_{1}} = E_{0}' (\bar{E_{2}}=E-E_{0}')$, with corresponding phase-space volumes $\omega_{1}(\bar{E_{1}})$ and $\omega_{2}(\bar{E_{2}})$ and $\omega(E) \approx \omega_{1}(\bar{E_{1}})\omega_{2}(E-\bar E_{1})$.
Now, only focus on statistics of subsystem 1 and how it interacts with the reservoir. We refuce the full microcanonical descrption to a marginal description for system 1 by *coarse-graining* over the reservoir. 
- Want to determine the (unrenormalized) density function $\rho(p_{1},q_{1})$ of the system 1:
	- Calculate mean value of $A(p,q)$ in system 1: $$\langle A \rangle_1 = 
\frac{ \int_1 \mathrm{d}p_1\, \mathrm{d}q_1\, A(p_1, q_1) \rho_1(p_1, q_1) }
     { \int_1 \mathrm{d}p_1\, \mathrm{d}q_1\, \rho_1(p_1, q_1) }
= 
\frac{ \int_1 \mathrm{d}p_1\, \mathrm{d}q_1\, A(p_1, q_1) \int_2 \mathrm{d}p_2\, \mathrm{d}q_2\, \rho(p,q) }
     { \int_1 \mathrm{d}p_1\, \mathrm{d}q_1 \int_2 \mathrm{d}p_2\, \mathrm{d}q_2\, \rho(p,q) }$$
	- Since in microcanonical ensemble, $\rho(p,q)$ is constant in the allowed energy range: #clarify $$\langle A\rangle_{1} = \frac{ \int_1 \mathrm{d}p_1\, \mathrm{d}q_1\, A(p_1, q_1) \omega_{2}(E-H_{1}(p_{1},q_{1}))}
     { \int_1 \mathrm{d}p_1\, \mathrm{d}q_1 \omega_{2}(E-H_{1}(p_{1},q_{1}))}$$
     - Consider $\omega_{2}(E-H_{1}(p_{1},q_{1}))=\rho_{1}(p_{1},q_{1})$ as the density function of the system 1. 
     - The number of microstates availiable to the total system is in this choice proportional to $\omega_{2}(E-H_{1})$.
     - This effectively means we *treat the number of compatible states in the reservoir as the weight of each state of the system 1.* The compatible states are the *leftover energy in the reservoir after giving $H_{1}$ to system 1.*
 - Assume $\bar{E_{2}} \approx E \gg \bar{E_{1}}$ may expand the entropy in $H_{1}$: $$k_{B}\log\omega_{2}(E-H_{1}(p_{1},q_{1})) = S_{2}(E -H_{1}(p_{1},q_{1})) = S_{2}(E) - H_{1}(p_{1},q_{1})\frac{ \partial S_{2}(\bar{E}_{2}) }{ \partial \bar E_{2} }\bigg|_{\bar{E_{2}}=E} +\dots= S_{2}(E) -  \frac{H_{1}(p_{1},q_{1})}{T} +\dots$$
 - This is now an approximation of the influence of the reservoir as a Boltzman weight
 - Get (with T the equillibrium temperature) $$\rho_{1}(p_{1},q_{1})=\omega_{2}(E-H_{1}(p_{1},q_{1}))=e^{{S_{2}(E)/k_{B}}}  e^{-H(p_{1},q_{1})/k_{B}T}.$$

Write generally for the density function, the probability to find the system of N paricles in microstate $(p,q)$ as $$\boxed{\rho(p,q) = \frac{1}{Z} e^{-H(p_{1},q_{1})/k_{B}T}}$$ with **partition function** $$\boxed{Z=\Lambda_{N} \int e^{-\beta H(p,q)}dpdq~~\text{   with  }~~ \beta=\frac{1}{k_{B}T},}$$which corresponds to volume of ensemble of system 1, called canonical ensemble, renormalized by $\Lambda_{N}= \frac{1}{N!h^{3N}}$. 

### Important Observation
- $w(E)$ is microcanonical volume. 
	- Counts how many microstates exist in $[E,E+\delta E]$ 
	- defined as $\omega(E)=\int \delta(H(p,q) -E)dpdq$
- $\rho(p,q)$ is canonical probability density. 
	- Gives probability density of finding the system in microstate $p,q$ at *fixed temperature* T.
	- defined as $\rho(p,q)=\frac{1}{Z} e^{-\beta H(p,q)}$
	- Get from conecting sysem to reservoir and coarse-graining over reservoir states: $\rho_{1}(p_{1},q_{1}) \propto \omega_{2}(E-H_{1}(p_{1},q_{1}))$
- We replaced the exact energy constraint from microcanonical approach by a *boltzmann weight* that suppresses high-energy microstates. 
	- $\omega_{1}(E-H_{1})\approx e^{S_{2}(E)- \frac{H_{1}}{T}} \Rightarrow \rho(p,q)\propto e^{-H_{1}(p,q)/k_{B}T}$ 

### Average in canonical ensemble
From [[#2.1 Gibbsian concept of ensembles]], in canonical ensemble, the average of a function $A(p,q)$ is $$\boxed{\langle  A \rangle = \frac{1}{Z} \int A(p,q) e^{-\beta H(p,q)}dpdq}$$

## 2.3.1 Thermodynamics

Conenection to thermodynamics via **Helmholtz free energy** $F=U-TS$ and relation $$Z=e^{-F(T,V,N)}$$
- $F$ is an *extensive* quantity, since scaling system by factor $\lambda$ yields $Z^\lambda$. 
- Defined as $F=U-TS$ with $U=\langle H \rangle$ and $S=-\left( \frac{ \partial F }{ \partial T } \right)_{V,N}$
	- proven with relation $1=\Lambda_{N}\int e^{\beta(F-H)}$ by differentiation wrt. $\beta$
- **Thermodynamic equation of state**: $$p=-\left( \frac{ \partial F }{ \partial V } \right)_{T,N}$$
- **Caloric equaiton of state**: $$U(T,V,N)=\langle  H \rangle = \frac{\Lambda_{N}}{Z} \int He^{-\beta H}dpdq = -\frac{1}{Z} \frac{ \partial Z }{ \partial \beta } =-\frac{ \partial  }{ \partial \beta } \log Z$$
## 2.3.2 Equipartition law

*"For a classical system i thermal equillibrium at temperature T, each **quadratic degree of freedom** contributes an average energy of $\frac{1}{2} k_{B}T$."* Means quadratic in variables like $p^2$ or $q^2$.

We now consider a set of special average values which will lead us to the so-called equipartition
law, the equal distribution of energy on equivalent degrees of freedom.
Start with examination of [[#Average in canonical ensemble]] (using integration by parts and assuming vanishing boundary conditions) $$\begin{align}
\left\langle   q_{\mu}\frac{ \partial H }{ \partial q_{\nu} }  \right\rangle  &= \frac{\lambda_{N}}{Z} \int q_{\mu}\frac{ \partial H }{ \partial q_{\nu} } e^{-\beta H}dpdq &&\\
&= \frac{\lambda_{N}}{Z\beta} \int q_{\mu} \frac{ \partial  }{ \partial q_{\nu} } e^{-\beta H}dpdq \\
&= -\frac{\Lambda_{N}}{Z\beta} \int' q_{\mu}e^{-\beta H} dpd'q + \frac{\Lambda_{N}\delta_{\mu \nu}}{Z\beta} \int e^{-\beta H}dpdq \\
&= 0+ \delta_{\mu \nu}k_{B}T. \\ 
\end{align}$$
- Used integration by parts $\int q_{\mu}\frac{ \partial  }{ \partial q_{\nu} }(e^{-\beta H})dq=[qe^{-\beta H}]-\delta_{\mu \nu}\int e^{-\beta H}dq$ and assume boundary term vanishes since $e^{-\beta H}\to 0$ for large q.
Same for momentum: $$\left\langle  p_{\mu}\frac{ \partial H }{ \partial p_{\nu} } \right\rangle  = \delta_{\mu \nu}k_{B}T$$
If Hamiltonian can be seperated into a p-dependent kinetic and a q-dependent potential part and this is valid: $$H(p,q)=E_{kin}(p)+V(q),\quad E_{kin}(\lambda p)=\lambda^{2}E_{kin}(p),\quad V(\lambda q)=\lambda^{\alpha}V(q),$$
- Find for mono-atomic particles (since only kinetic energy): $$\boxed{\langle E_{kin} \rangle =\frac{3N}{2} k_{B}T, \quad \langle  V\rangle =\frac{3N}{\alpha} k_{B}T, \quad U=\langle E_{kin}\rangle + \langle V\rangle = k_{B}T\left( \frac{3N}{2} + \frac{3N}{\alpha} \right)}$$

## 2.3.3 Ideal gas - canonical treatment

Same as [[#2.2.3 Ideal gas - microcanonical treatment]], consider gas of N particles without externap potential and mutual interactinos described by same Hamiltonian. 
- Partition funciton is $Z= \Lambda_{N} \prod \limits_{i=1}^{N} \int e^{-p_{i}^{2}/2mk_{B}T}d^{3}p_{i}d^{3}q_{i}  =  \Lambda_{N}\left\{  \int e^{-p^{2} / 2mk_{B}T} d^{3}pd^{3}q\right\}^{N} = \Lambda_{N}V^{N}\{ 2\pi mk_{B}T \}^\frac{3N}{2}$ 
	- partition function has a product form because each particle is described independently. Leads to extensive free energy and internal energy. 
- Obtain free energy and internal energy with [[#Sterling Formula]]: $$\begin{align}
F(T,V,N) &= -k_{B}T \log Z=-N{k_{B}}T \log \left(  \frac{V}{N} \left( \frac{2\pi mk_{B}T}{h^{2}} \right)^\frac{3}{2} \right)-Nk_{B}T \\
U(T,V,N) &= -\frac{ \partial  }{ \partial \beta } \log Z =\frac{3N}{2}k_{B}T \quad \text{(caloric equation of state)}
\end{align}$$
- Entropy: $$\boxed{S(T,V,N) = -\left( \frac{ \partial F }{ \partial T }  \right)_{V,N} = Nk_{B}\log\left\{  \frac{V}{N} \left(  \frac{2\pi mk_{B}T}{h^{2}} \right)^{3/2} \right\}+\frac{5N}{2}k_{B}}$$
- thermodynamic equation of state: $$\boxed{p=-\left( \frac{ \partial F }{ \partial V }  \right)_{T,N}=\frac{Nk_{B}T}{V}}$$
- Chemical potential: $$\boxed{\mu=\left( \frac{ \partial F }{ \partial N }  \right)_{T,V}=-k_{B}T\log\left\{ \frac{V}{N} \left( \frac{2\pi mk_{B}T}{h^{2}} \right)^{3/2} \right\}}$$

___
# 2.4 Grand canonical ensemble

![[Grand Canonical ensemble.png|Grand Canonical Ensemble - System 1 has fixed µ and T]]

Now also allow exchange of matter into the system by connecting to very large hear and particle reservoir. 
Have $N_{1}\ll N_{2}$ and $V_{1}\ll V_{2}$ with $N=N_{1}+N_{2}$ and $V=V_{1}+V_{2}$ fixed.
- Can decompose the Hamiltonian into 2 parts $H(p,q,N)=H_{1}(p_{1},q_{1},N)+H(p_{2},q_{2},N_{2})$ and have *partition function* for given temperature $$Z_{N}(V,T)=\frac{1}{h^{3N}N!}\int e^{-\beta H(p,q,N)}dpdq.$$
- Try to segregate this into the subsystems: $$\begin{align}
  Z_N &= \frac{1}{h^{3N} N!} \sum_{N_1 = 0}^{N} \frac{N!}{N_1! N_2!} 
  \int dp_1 \, dp_2 \int_{V_1} dq_1 \int_{V_2} dq_2 \, 
  e^{-\beta \left\{ \mathcal{H}(p_1, q_1, N_1) + \mathcal{H}(p_2, q_2, N_2) \right\}} \\
  &= \sum_{N_1 = 0}^{N} 
  \frac{1}{h^{3N_1} N_1!} \int_{V_1} dp_1 \, dq_1 \, 
  e^{-\beta \mathcal{H}(p_1, q_1, N_1)} 
  \cdot \frac{1}{h^{3N_2} N_2!} \int_{V_2} dp_2 \, dq_2 \, 
  e^{-\beta \mathcal{H}(p_2, q_2, N_2)}
\end{align}$$
	- Factor accounts for all ways to distribute the particles from the two subsystems. 
- Define probability $\rho(p_{1},q_{1},N_{1})$ of finding $N_{1}$ particles in volume $V_{1}$ at the space coordinates $(p_{1},q_{1})$: $$\rho(p_{1},q_{1},N_{1})= \frac{\Lambda_{N_{2}}\int_{V_{2}} e^{-\beta H(p_{2},q_{2},N_{2})}dp_{2}dq_{2}}{Z_{N}} e^{-\beta H(p_{1},q_{1},N_{1})} = \frac{Z_{N_2}}{Z_N} e^{-\beta \mathcal{H}(p_1, q_1, N_1)}$$
- Using relations 
	- Renormalization  $\sum_{N_1=0}^{N} \Lambda_{N_1} \int_{V_1} dp_1 \, dq_1 \, \rho(p_1, q_1, N_1) = 1$ 
	- Partition function fraction$\frac{Z_{N_2}(V_2, T)}{Z_N(V, T)} = e^{-\beta \left\{ F(T, V - V_1, N - N_1) - F(T, V, N) \right\}}$
	- Energy difference $F(T,V-V_{1},N-N_{1})-F(T,V,N)\approx-\left( \frac{ \partial F }{ \partial V } \right)_{T,N}V_{1} - \left( \frac{ \partial F }{ \partial N } \right)_{T,V}N_{1} = pV_{1}-\mu N_{1}$, using first order taylor expansion.  
	- Reformulate to $$\rho(p_1, q_1, N_1) = e^{-\beta(pV_{1}-\mu N_{1})} e^{-\beta \mathcal{H}(p_1, q_1, N_1)}$$
Define **fugacity** $z=e^{\beta \mu}$ and write for density function of the whole system $\rho(p,q,N)=z^{N}e^{-\beta\{pV+H(p,q,N)\}}$
- Key feature of grand canonical ensemble: states are weighted by both their energy and their particle number. 

Introduce **Grand partition funciton**, incorporating all important information of a system of fixec volume, temperature and chemical potential: $$\boxed{\mathcal{Z}(T,V,z)=\sum\limits_{N=0}^{\infty}z^{N}Z_{N}(V,T)}$$
- From this, can derive average particle number, energy, pressure etc. 

## 2.4.1 Thermodynamic quantities - grand canonical ensemble

Use probability density and integrate both sides: $$1 = e^{-\beta pV}\sum_{N=0}^{\infty}\frac{z^{N}}{N!} \int \frac{1}{h^{3N}} e^{-\beta H(p,q,N)} dpdq = e^{-\beta pV}\mathcal Z(T,V,z))$$
Find **Grand Potential** $\boxed{\Omega(T,V,\mu) = -pV = -k_{B}T\log(\mathcal Z(T,V,z))}$ with $$\boxed{d\Omega=-Sdt-pdV-Nd\mu}$$
- Average N (with $P_{N}$ the probability to find N particles in the system): $\langle N \rangle = -\left( \frac{ \partial \Omega }{ \partial \mu } \right)_{T,V}=k_{B}T \frac{ \partial  }{ \partial \mu }\log \mathcal Z = z \frac{ \partial  }{ \partial z }\log \mathcal Z = \frac{1}{\mathcal{Z}} \sum_{N=0}^{\infty}N z^{N}Z_{N} = \sum_{N=0}^{\infty}P_{N}N$
- Internal Energy: $$\boxed{U=-\frac{ \partial  }{ \partial \beta }\log\mathcal Z \quad\Rightarrow\quad C_{V}=\left( \frac{ \partial U }{ \partial T } \right)_{V,\mu}}$$

## 2.4.2 Ideal gas - grand canonical treatment

Calcualte grand partition function for ideal gas $$\mathcal Z (T,V,z)= \sum_{N=0}^{\infty}z^{N}Z_{N}(T,V) = \sum_{N=0}^{\infty} \frac{z^{N}}{h^{3N}} (2\pi k_{B}T)^{3N /2} =\exp\left( \frac{zV}{h^{3}} (2\pi mk_{B}T)^{3/2} \right) $$
Probability $P_{N}$ of finding system with $N$ particles: $\langle N \rangle = z \frac{ \partial  }{ \partial z }\frac{z^{N}}{h^{3}} (2\pi k_{B}T)^{\frac{3 }{2}} = \frac{zV}{h^{3}}(2\pi mk_{B}T)^{\frac{3}{2}} \Rightarrow \mathcal Z=e^{\langle N \rangle}$
- #clarify Appears that $P_{N}$ is not defined properly due to $h$. However, chemical potential is only determined up to a constant shift that absorbs h.
- Can write $P_{N}=\frac{z^{N}Z_{N}}{\mathcal Z} = e^{-\langle N \rangle} \frac{\langle N\rangle^{N}}{N!} \approx \frac{1}{\sqrt{ 2\pi \langle N \rangle }} e^{-(N-\langle N \rangle)^{2} /2\langle N \rangle}$
	- Peaks at $N\gg 1$ with fluctuations as $\langle N^{2}\rangle - \langle N\rangle^{2}= z\frac{ \partial \langle N \rangle }{ \partial z }=\langle N \rangle$
- Grand potential: $$\Omega(T,V,\mu) = -k_{B}Te^{\beta \mu} \frac{V}{h^{3}}(2\pi mk_{B}T)^{\frac{3}{2}}=-k_{B}T\langle N \rangle = -pV$$
- Chemical Potential $$\mu=-k_{B}T \log\left( \frac{V(2\pi mk_{B}T)^{\frac{3}{2}}}{\langle  N \rangle  h^3} \right)$$

# Summary Ensembles

![[Ensembles Overview.png]]

|                          | **Microcanonical Ensemble**                                                  | **Canonical Ensemble**                                                 | **Grand Canonical Ensemble**                                                                           |
| ------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Density function**     | $\rho(p,q) = \delta(E - \mathcal{H}(p,q)) \, \delta E$                       | $\rho(p,q) = e^{-\beta \mathcal{H}(p,q)}$                              | $\rho(p,q,N) = z^N e^{-\beta \mathcal{H}(p,q,N)}$                                                      |
| **Partition function**   | $\omega(E) = \Lambda_N \int \rho(p,q)dpdq$<br>                               | $Z_N = \Lambda_N \int e^{-\beta \mathcal{H}(p,q)}dpdq$                 | $\mathcal{Z} = \sum\limits_{N=0}^\infty z^N Z_N$                                                       |
| **Average value**        | $\langle A \rangle = \frac{\Lambda_N}{\omega(E)} \int \rho(p,q) A(p,q) dpdq$ | $\langle A \rangle = \frac{\Lambda_N}{Z_N} \int  \rho(p,q) A(p,q)dpdq$ | $\langle A \rangle = \sum\limits_{N=0}^\infty \frac{\Lambda_N}{\mathcal{Z}} \int \rho(p,q) A(p,q)dpdq$ |
| **Thermodyn. potential** | $S = k_B \log \omega$                                                        | $F = -k_B T \log Z_N$                                                  | $\Omega = -k_B T \log \mathcal{Z}$                                                                     |

___

# 2.5 Fluctuations

Certain quantities that are statistically fiyed in one ensemble are statistical variables of other ensembles.howe well can the mean values of these quantities be determined statistically? How equivalent are the formulations of different ensembles. 

## 2.5.1 Energy
In canonical ensemble, internal Energy given as average of the Hamiltonian $U=\langle H \rangle$. Therefore have $\Lambda_{N} \int [U-H]e^\beta(F-H)dpdq=0$
- Take derivative wrt. $\beta$ and obtain $0=\frac{ \partial U }{ \partial \beta }+\Lambda_{N} \int(U-H)\left[ F-T\frac{ \partial F }{ \partial T }-H \right]e^{\beta(F-H)}dpdq = \frac{ \partial U }{ \partial \beta }+ \langle (U-H)^{2}\rangle$
- #clarify where does the $\frac{ \partial U }{ \partial \beta }$ come from?
- Get energy fluctuations: $\langle H ^{2}\rangle - \langle H \rangle ^{2}= \langle (U-H)^{2}\rangle = -\frac{ \partial U }{ \partial \beta } = k_{B}T^{2}\frac{ \partial U }{ \partial T } = k_{B}T^{2}C_{V}$
- Since $C_{V}$ is an extensive quantity (proportional to N), get $\frac{\langle H^{2}\rangle - \langle H \rangle ^{2}}{\langle H \rangle ^{2}} \propto \frac{1}{N}$
- -> Sign of equivalence of miceocanonical and caonical ensembles. In thermodynamic limit $N\to \infty$, the fluctuations of the energy vanish compared to energy itself. Internal energy is thus well defined quantity in canonical and microcanonical ensemble. 

Consider partition function #ToDo (Latex with ChatGPT from page 28) $$Z=\int_{0}^{\infty} \frac{dE}{\partial E} e^{\beta(TS_{m'can}(E)-E)}$$ where $\omega(E)=\Lambda_{N} \int \delta(E-H(p,q))\delta E dpdq$ defines the microcanonical volume and the entropy is defined according to the microcanonical ensembe $S(E)=E_{m'can}(E)=k_{B}\log \omega(E)$.
- The maximum of the integrand at $E=E_{0}$ is defined by the condition $T\frac{ \partial S }{ \partial E }\bigg|_{E=E_{0}}=1$ and $\frac{ \partial ^{2}S }{ \partial E^{2} }\bigg|_{E=E_{0}}$.
	- Note #ToDo 
- Expand the exponent in the integra and #ToDo obtain $$F_{can}\approx U-TS_{m'can} - {2 k_{B}T \log\left( \frac{2\pi k_{B}T^{2}C_{V}}{\delta E^{2}} \right)} = U - TS_{m'can} + \mathcal O(\log N)$$
## 2.5.2 Particle number

#ToDo Derive $$\langle N^{2}\rangle - \langle N \rangle ^{2} = -k_{B}T \frac{ \partial ^{2 }}{ \partial \mu^{2 }} \Omega(T,V,\mu)= k_{B}T \frac{ \partial \langle N \rangle }{ \partial \mu }$$
Relate rhs. with isothermal compressibility and introduce **Gibbs-Duhem relation** $$\boxed{Sdt - Vdp + Nd\mu=0}$$
Define *specific volume* $v=\frac{V}{N}$ and express both intensive quantities $\mu=\mu(v,T)$ and $p=p(v,T)$as functions of only intensive vatiables $v$ and $T$. 
Obtain for fixed temperature $dT=0$: $$d\mu=vdp-\frac{S}{N}dt \Rightarrow \left( \frac{ \partial \mu }{ \partial v }  \right)_{T} = v\left( \frac{ \partial p }{ \partial v }  \right)_{T}$$
Can formulate following derivatives: $$\begin{align}
\left( \frac{ \partial  }{ \partial v }  \right)_{V,T} &= \left( \frac{ \partial N }{ \partial v }  \right)_{V,T}\left( \frac{ \partial  }{ \partial N }  \right)_{V,T}=-\frac{N^{2}}{V} \left( \frac{ \partial  }{ \partial N }  \right)_{V,T} \\
\left( \frac{ \partial  }{ \partial v }  \right)_{N,T} &= \left( \frac{ \partial V }{ \partial v }  \right)_{N,T}\left( \frac{ \partial  }{ \partial V }  \right)_{N,T}=N \left( \frac{ \partial  }{ \partial V }  \right)_{N,T}
\end{align}$$
Finally somehow obtain $$-\frac{N^{2}}{V} \left( \frac{ \partial \mu }{ \partial N }  \right)_{V,T}=V\left( \frac{ \partial p }{ \partial V }  \right)_{N,T} \Rightarrow \frac{1}{N} \left( \frac{ \partial N }{ \partial \mu }  \right)_{V,T} = -\frac{1}{vV} \left( \frac{ \partial V }{ \partial p }  \right)_{N,T} = \frac{\kappa_{T}}{v}$$
This is **isothermal compressibility** $\kappa_{T} = \frac{v}{\langle N \rangle k_{B}T}(\langle N ^{2}\rangle - \langle N \rangle^{2})$
#todo #clarify   

## 2.5.3 Magnetization
