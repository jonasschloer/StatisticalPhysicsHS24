---
noteID: 0551b893-6440-4e65-aac9-2bfb78d5a127
tags: 
---
___
# 1.1 Micro states with same energy

Consider system of N atoms in $z$ different mictostates $\{s_{i}^{\nu}\}$. $s_{i}$ is a vector with one component being one and the others zero (the state of the i-th atom).
- Micro state can change during a single timestep with **transition propability** $p_{\nu \nu'}=\Gamma_{\nu \nu'}\Delta t$ with **transition rate** $\Gamma_{\nu \nu'}$https://nswpedia.com/download/super-mario-3d-all-stars-12012/2/download_list
	- Require $p_{\nu \nu'}$ for time reversal symmetry
- $N_{\nu}=\sum\limits_{i=1}^{N} s_{i}^{\nu}$ is **number of units of the system that are in the micro state $\nu$**, with $\sum N_{\nu}=N$
- Find random unit $i$ in the micro-state $\nu$ with **population probability** $w_{\nu}=\frac{N_{\nu}}{N}$ with $\sum w_{\nu}=1$

Budget of micro-state $\nu$ during evolution in time: 
- Some units transition to other state $\nu \mapsto \nu'$ with rate $\sum_{\nu'}\Gamma_{\nu \nu'}N_{\nu}$, reducing $N_{\nu}$
- Other units transition from other state $\nu' \mapsto \nu$ with rate $\sum_{\nu}\Gamma_{\nu '\nu}N_{\nu'}$ , increasing $N_{\nu'}$
- **Budget equation**: $N_{\nu}(t_{n+1}) = N_{\nu}(t_n)+ \Delta t \sum_{\nu' \neq \nu} \underbrace{\Gamma_{\nu \nu'} N_{\nu}(t_n)}_{\text{leaving state } \nu} + \Delta t \sum_{\nu' \neq \nu} \underbrace{\Gamma_{\nu' \nu} N_{\nu'}(t_n)}_{\text{entering state } \nu}$ 
- Have $z$ iterative equations, describing ecolution of N states, state of individual units not tracked

### Detailed Balance
Find later in [[H-theorem]] #ToDo that iteration moved to fixed point for any arbitrary configuration:
$$0=\sum\limits_{\nu' \neq \nu} \Gamma_{\nu \nu'} N_{\nu}(t_{n}) - \sum\limits_{\nu'\neq \nu} \Gamma_{\nu'\nu}N_{\nu'} (t_{n}) \underbrace{=}_{\text{since independent}} \Gamma_{\nu \nu'} N_{\nu}(t_{n}) -  \Gamma_{\nu'\nu}N_{\nu'} (t_{n})$$
- Since in our model $\Gamma_{\nu \nu'}=\Gamma_{\nu'\nu}$, find that $N_{\nu}=N_{\nu'}=\frac{N}{z}$ and all micro states are equally occupied
- **Detailed Balance Condition**: $w_{\nu}\Gamma_{\nu \nu'}=w_{\nu'}\Gamma_{\nu'\nu}$, holds in equillibrium 
- Detailed balance describes the distribution $w_{\nu}$ with the highest probability, see [[#Interpretation of detailed balance using H-function]]

### Master equation - same energy 
Taking limit $\Delta t \to 0$ and dividing by $N$, get different equation: $$\frac{dw_{\nu}}{dt} = -w_{\nu} \sum\limits_{\nu'\neq \nu}\Gamma_{\nu \nu'} + \sum \limits_{\nu'\neq \nu}\Gamma_{\nu'\nu}w_{\nu'}$$
- Detailed balance condition $w_{\nu}\Gamma_{\nu \nu'}=w_{\nu'}\Gamma_{\nu'\nu}$ leads to solution with all probabilities $w_{\nu}(t)$ are constant in time: $\frac{w_{\nu}}{w_{\nu'}}=\frac{\Gamma_{\nu'\nu}}{\Gamma_{\nu \nu'}}=1,\quad w_{\nu}=\frac{1}{z}$

### Time evolution of macro states
Define mean value of macro state "$\alpha$", which is associated with each macro state as $\alpha_{\nu}$, by $\langle \alpha \rangle = \sum \limits_{\nu} \alpha_{\nu}w_{\nu}$
- Time evolution derived as: 
$$\begin{align}
\frac{d}{dt}\langle  \alpha \rangle  &= \sum_{\nu} \alpha_{\nu} \left[ -w_{\nu} \sum_{\nu' \neq \nu} \Gamma_{\nu \nu'} + \sum_{\nu' \neq \nu} \Gamma_{\nu'\nu} w_{\nu'} \right] \quad \bigg | \quad\Gamma_{\nu \nu'}=\Gamma_{\nu'\nu}\\
&= -\frac{1}{2} \sum_{\nu \nu'} \{\alpha_{\nu} - \alpha_{\nu'}\}(w_{\nu}-w_{\nu'}) \Gamma_{\nu \nu'}
\end{align}$$

## 1.1.1 H-function and information

H-function is measure for lack of knowledge about the microscopic state of the system:
$$H(t) = -\sum_{\nu} w_{\nu} \log w_{\nu}$$
- Whe picking one atom at random, ask how well we can predict the micro-state of the atom.
	- If knowing system exactly: If $w_{1}=1$ and $w_{\nu}=0$ for allothers, then are sure that atom is in micro-state 1 and H=0.
- The larger H, the less certain the outome of our picking experiment and the less information is availiable about the system.
- ! The H-function is equivalent to entropy via $H=\frac{S}{Nk_{B}}$, as shown [[#1.2.1 H and the equilibrium thermodynamics |below]].

### Time dependence of H-function
Using [[#Master equation]] and [[#Detailed Balance]] get
$$\begin{align}
\frac{dH(t)}{dt} &= - \sum_{\nu} \frac{dq_{\nu}}{dt} (\log_{w}+1) \\
&= \sum_{\nu \nu'} \Gamma_{\nu \nu'}(w_{\nu} - w_{\nu'})(\log w_{\nu} +1) \\
&= \frac{1}{2} \sum_{\nu \nu'} (\log w_{\nu} - \log w_{\nu'})(w_{\nu}-w_{\nu'}) \Gamma_{\nu \nu'}\quad\ge 0
\end{align}$$
- Evolves increasingly, despite assumption of time reversal symmetry
- Microscopic states obey time reversal, but macroscopic states dont
- Condition $\frac{dH}{dt}=0$ requires $w_{\nu}=w_{\nu'}$ which is just [[#Detailed Balance]]. Corresponds to the maximum value of H, which is maximum level of uncertainty. 
- For finite systems as in [[#1.1.2 Simulation of a two-state system]], this is not a strict inequality.

Different approach: 
- For given $w_{\nu}=\frac{N_{\nu}}{N}$, there are $\frac{N!}{N_{1}!\cdots N_{z}!}=W(N_{\nu})$ **realizations** among all $z^N$ possible configurations. 
- Apply Stirling formula ($\log(n!) \approx n\log (n) - n+\frac{1}{2}\log(2\pi n)$) and get: $$\log(W(N_{\nu})) \approx N\log N -N - \sum_{\nu} [N_{\nu} \log N_{\nu }- N_{\nu}] = -N \sum_{\nu} w_{\nu }\log w_{\nu }= NH(t)$$
- $\Rightarrow H$ measures number of availiable configurations of the units for a given set $\{N_{\nu}\}$
### Interpretation of detailed balance using H-function
Maximum $H$ corresponds to detailed balance condition:
- When maximizing $H$ as function of $w_{\nu}$ with Lagrange multiplier resembling the normalization of the probability distribution, then get $\frac{dH'}{dw_{\nu}} = -\log w_{\nu} -1 + \lambda =0$ and $\sum_{\nu} w_{\nu}=1$, which is solved by $w_{\nu}=e^{\lambda⁻1}=\frac{1}{z} \quad\boxed{}$
- Detailed balance describes distribution $w_{\nu}$ with the highest probability
- In our case, this is the largest number of different possible realizations that yield the same $\{N_{1},\dots,N_{z}\}$.
	- Corresponds to the maximum value of realizations $W(N_{\nu})$
- A system thus follows the master equation and moves towards a fixed point with this property. $H(t)$ grows minitonously until it reaches the maximum value

## 1.1.2 Two-State System

Looking at the [[#Time dependence of H-function]], find that while microscopic quantities obey time reversal symmetry, the macroscopic states do not. Want to investigate this by compating analytical solutions to master equation with numerical solutions of the micro states. 

### Simulation
- Consider system of $N$ units with two different micro-states (z=2), described by $m_{i}=+1$ called $\nu=1$ and $m_{i}=-1$ called $\nu=2$. Interpret as mangnetic moment. 
- Transition happens with equal propability $p$ (time reversal symmetry obeyed)
- Use **Markov Chain** algorithm (transition independent of previous steps) by generating uniformly distributed random number $R \in [0,1]$ and flipping sign if $0\le R \le p$.
- Measure average magnetization per unit $M(t) = \frac{1}{N} \sum m_{i}(t)$ and $H$-function $H(t)=-\sum\limits_{\nu=1}^{2} w_{\nu}(t) \log w_{\nu}(t)$ with $w_{{1},{2}} = \frac{1}{2} \{1\pm M(t)\}$ 
- Start simulation wirh all $m_{i}=+1$ (just one configuration corresponding to this state) while fixed point (=equillibrium) solution $w_{1}=w_{2}=\frac{1}{2}$, corresponding to M=0, is realized by large number of states $W=\frac{N!}{\left( \frac{N}{2}! \right)^{2}}\approx_{2}^{N} \sqrt{ \frac{2}{\pi N} }$.
- Find $W(M)\approx 2^{N}\sqrt{ \frac{2}{\pi N} }e^{-M^{2}N/2}$ 
	- When increasing the magnetization from equillibrium ($M=0$) to maximum value $(M=\pm1)$, the number of realizations drop quickly. The larger $N$, the larger the fraction of all possible configurations belonging to the macroscopic state $M \approx_{}0$.
	- Fixed point/equillibrium reached after a long time corresponds to each configuration of micro states accessed with the same probability. Macro states deviating from fixed point occupy less and less of the available configuration space for increasing $N$.

### Solving Master equation
Master equations for 2-state system are $$\frac{dw_{1}}{dt} = \Gamma(w_{2} - w_{1}),\quad \frac{dw_{2}}{dt} = \Gamma(w_{1}-w_{2}).$$
- Solve by adding and subtracting (see page 6)
- Give exponential decay $M(t)=M_{0} e^{-2t\Gamma}$ with $M_{0}=1$.
- Also obtain $H(t)\approx \log(2) - \frac{1}{2 e^-4t\Gamma}$
	- Relaxation times $\tau_{M}=\frac{1}{2\Gamma}$ for $M$ and $\tau_{H}=\frac{1}{4\Gamma}$ for $H$ differ by factor of 2

## 1.1.3 Equilibrium of a system

Analysis of the [[#1.1.2 Two-State System |two state system]] shows that system relaxes towards fixed point in probability distribution $w_{\nu}$. This then describes the macroscopic state independent of time. 
The probability distribution of the micro-states allows for calculation of averaged physical quantities. 
Deviations from equillibrium yield non-equillibrium states that then relax towards equillibrium again. 
The equillibrium state can be seen in a statistical sense as the state with the maximum number of realizations (configurations of micro-states of the units).
___
# 1.2 Analysis of a closed system

Now aim to get connection to macroscopic thermodynamic properties of the system in equillibrium. 
Consider closed system (no matter or energy exchange) of N units with states that possess different energies $\epsilon_{\nu}$. Describe macro-state of the system by probability distribution $w_{\nu}=\frac{N_{\nu}}{N}$. Total number and total energy of units is conserved: 
- $\langle \epsilon \rangle = \sum_{\nu=1}^{z} w_{\nu}\epsilon_{\nu},\quad 1=\sum w_{\nu}$
- **Internal energy** $U=N \langle \epsilon \rangle = Nu$ is unchanged

## 1.2.1 H and the equilibrium thermodynamics

For now consider only aspects of the equillibrium and ignore time evolution and non-equillibrium. Search for maximum $H$ with respect to $w_{\nu}$ under condition of energy conservation.
- Take [[#1.1.1 H-function and information|definition]] of $H$ along with lagrange multipliers for number end energy conservation and find $0= \frac{dH}{dw_{\nu}} = -\log w_{\nu} -1 + \lambda -\frac{\epsilon_{\nu}}{\theta}$
- Get $w_{\nu} = e^{\lambda -1 -\epsilon_{\nu}/\theta}$ with $e^{1-\lambda}=\sum_{\nu} e^{-\epsilon/\theta}:=Z$.
- Equals to $w_{\nu} = \frac{e^{\frac{-\epsilon_{\nu}}{k_{B}T}}}{Z}$

Want to give this a thermodynamic meaning:
- Find $1-\lambda=H- \frac{\langle\epsilon \rangle}{\theta}$ and obtain $\langle\epsilon \rangle=\theta (\log w_{\nu} + H) + \epsilon_{\nu}$
- Find differential $d\langle\epsilon \rangle = \theta dH + \sum_{\nu} q_{\nu}d \epsilon_{\nu}$
	- View $\langle \epsilon \rangle=u$ as internal energy per unit
	- View $d\epsilon_{\nu} = \sum_{i} \frac{\partial\epsilon_{\nu}}{\partial q_{i}}dq_{i}$, with $q_{i}$ a *generalized coordinate*, such as volume or magnetization.
	- View $\frac{\partial\epsilon_{\nu}}{\partial q_{i}} = -F_{i\nu}$ as *generalized force*, such as pressure or magnetic field
- Find $\theta=k_{B}T$ the temperature and $H=\frac{s}{k_{B}}$ the entropy density.
- Get $$dH = \frac{du}{k_{B}T} + \frac{1}{k_{B}T} \sum_{i} \langle F_{i}\rangle dq_{i}$$
- Identify $$\left( \frac{ \partial S }{ \partial U }   \right)_{q_{i}} = \left( \frac{ \partial s }{ \partial u }  \right)_{q_{i}} = \frac{1}{T}, \quad \left( \frac{ \partial s }{ \partial q_{i} }  \right)_{u} = \frac{1}{T} \langle F_{i} \rangle $$
	- Connection to thermodynamics. 
- From now on, $H$-function is equivalent to entropy as $S=Nk_{B}H$ 

## 1.2.2 General Master equation

Modify master equtation to guarantee energy conservation. Microstates of different units need to be transformed together: $$\frac{ d w_{\nu} }{ d t } = \sum\limits_{\nu_{1}, \nu_{2}, \nu_{3}} \{ \Gamma_{\nu_{2}\nu_{3};\nu \nu_{1}}w_{\nu_{2}}w_{\nu_{3}} -\Gamma_{\nu \nu_{1};\nu_{2}\nu_{3}} w_{\nu}w_{\nu_{1}}  \},$$where $\Gamma_{\nu_{2},\nu_{3};\nu \nu_{1}}$ denotes rate for transition of pair $(\nu_{2},\nu_{3})$ to $(\nu,\nu_{1})$ under condition $\epsilon_{\nu_{2}} + \epsilon_{\nu_{3}} = \epsilon_{\nu}+\epsilon_{v_{1}}$. 

Enforcing **detailed balance**:
- Time reversal symmetry and freedom of exchange of 2 states: $\Gamma_{\nu \nu_1; \nu_2 \nu_3} = \Gamma_{\nu_2 \nu_3; \nu \nu_1} = \Gamma_{\nu_1 \nu; \nu_2 \nu_3} = \Gamma_{\nu \nu_1; \nu_3 \nu_2}$
- Find that H-function increases with time $$\frac{ d H }{ d t } = -\sum_{\nu} \frac{ d w_{\nu} }{ d t } \{\log w_{\nu}+1\} =\frac{1}{4} \sum_{\nu, \nu_1, \nu_2, \nu_3} \Gamma_{\nu, \nu_1; \nu_2, \nu_3} \left( w_{\nu} w_{\nu_1} - w_{\nu_2} w_{\nu_3} \right) \left\{ \log (w_{\nu} w_{\nu_1}) - \log (w_{\nu_2} w_{\nu_3}) \right\} \ge 0$$
- equillibrium reached when = 0 $\Rightarrow w_{\nu} w_{\nu_1} = \frac{e^{-\epsilon_{\nu}/k_B T} e^{-epsilon_{\nu_1}/k_B T}}{Z^2} = \frac{e^{-\epsilon_{\nu_2}/k_B T} e^{-\epsilon_{\nu_3}/k_B T}}{Z^2}= w_{\nu_2} w_{\nu_3}$ (utilized $w_{\nu} = \frac{e^{\frac{-\epsilon_{\nu}}{k_{B}T}}}{Z}$)

Revisiting master equaiton with detailed balance
-  For each term: $0=\Gamma_{\nu_{2}\nu_{3};\nu \nu_{1}}w_{\nu_{2}}w_{\nu_{3}} -\Gamma_{\nu \nu_{1};\nu_{2}\nu_{3}} w_{\nu}w_{\nu_{1}}=\Gamma_{\nu \nu_{1};\nu_{2}\nu_{3}} \{w_{\nu_{2}}w_{\nu_{3}} - w_{\nu}w_{\nu_{1}}\}$
- New notation: $\Gamma'_{\nu \nu'}=\sum_{\nu_{1},\nu_{2}} \Gamma_{\nu \nu_{1};\nu'\nu_{2}} w_{\nu_{1}}$ and $\Gamma'_{\nu'\nu} =\sum_{\nu_{1},\nu_{2}} \Gamma_{\nu \nu_{1};\nu_{0}\nu_{2}}w_{\nu_{2}}$ (I think this is the total transition rate, incorporating all possible transitions)
- Can now simplify $$\Gamma'_{\nu \nu'}w_{\nu}=\Gamma'_{\nu'\nu}w_{\nu'}$$
	- In detailed balance, transitions from and transitions to state $\nu$ balance out
- At equillibrium $\Gamma'_{\nu'\nu}=e^{-(\epsilon_{\nu}-\epsilon_{\nu'}) / k_{B}T} \Gamma'_{\nu \nu'}$
	- Detailed balance implied different tarnsition rates for the two directions of processes, depending on the energy difference between two micro-states and the temperature: $$\frac{w_{\nu}}{w_{\nu'}} = \frac{\Gamma'_{\nu'\nu}}{\Gamma'\nu \nu'}=e^{-(\epsilon_{\nu} - \epsilon_{\nu'}) / k_{B}T}$$

## 1.2.3 Irreversible processes and increase of entropy
Irreversible processes (considering time evolution of system from non-equillibrium to equillibrium state) not part of thermodynamics usually. 