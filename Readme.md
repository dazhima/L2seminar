The prepoka's theorem and $L^2$ for one dimensional real case.

The $L^2$ for $\bar{\partial}$ complex one dimensional case.

### Prepoka's theorem

##### Convex functions

A convex function is a decreasing limit of $\mathscr{C}^2$ convex functions.

##### Prepoka's theorem

Let $\phi(t,x)$ be a convex function on $\mathbb{R}_t\times \mathbb{R}_x$. Let $\tilde{\phi}(t)$ be deterimed by $$e^{-\tilde{\phi}(t)} = \int_{\mathbb{R}_x}e^{-\phi(t,x)}dx.$$ 

Then $\tilde{\phi}$ is convex.

Note: the $\tilde\phi$ is not continuous in general, it is just upper semi continuous.

##### Theorem

Let $\phi(t,x)$ be a smooth strictly convex function on $\mathbb{R}_t \times \mathbb{R}_x$. 
Define $\tilde{\phi}$ by $e^{-\tilde{\phi}(t)}= \int_{-R}^R e^{-\phi(t,x)}dx.$

Then $\tilde \phi$ is smooth strictly convex.

Note: $\tilde{\phi}$ is smooth because the integral RHS has no zeroes.

*Proof.* We want to show that $\tilde \phi_{tt}>0$.

* It sufficies to prove the case $R = 1$. Let $I$ denote the intevral $(-1,1)$ on $\mathbb{R}_x$.
* Take the derivative on $t$ both sides we get
  * $-\tilde{\phi}_t e^{-\tilde{\phi}(t)} = \int_{I}-\phi_t(t,x)e^{-\phi(t,x)}dx$.
  * $(-\tilde\phi_{tt}+\tilde\phi_t^2)e^{-\tilde\phi} = ...$
* Consider the measure $d m_{\phi,t}:=e^{-\phi(t,x)}dx$, we write $m$ instead of $m_{\phi,t}$ for simplicity. then we see that
  * $e^{-\tilde\phi(t)} = m(I)$.
  * $\tilde{\phi}\cdot m(I) = \int_I \phi dm.$
  * $\tilde{\phi}_{tt}\cdot m(I) = \int_{I}\phi_{tt}dm+ \int_{I}\phi^2dm - \tilde\phi^2\cdot m(I) = \int_{I}\phi_{tt}dm -  \int_I(\phi^2 - \tilde\phi^2)dm$.
* Since $\phi$ is strictly convex, $\phi_{tt}-\frac{\phi_{tx}^2 }{\phi_{xx}}>0$. Hence it sufficies to show that $\int_I(\phi^2-\tilde{\phi}^2)dm \leq \int_I\frac{\phi_{tx}^2}{\phi_{xx}}dm$.

* This follows from the $L^2$ estimate.

##### Lemma ($L^2$-estimate)

Let $\psi$ be a smooth strictly convex function on $\mathbb{R}$. Let $u$ be a smooth function on $\mathbb{R}$ with $\int_{|x|<1}ue^{-\psi} = 0$. Then

$$\int_{|x|<1}u^2e^{-\psi} \leq \int_{|x|<1}\frac{u_x^2}{\psi_{xx}}e^{-\psi}.$$

* Since $\phi$ is strictly convex, the Hessian matrix of $\phi$ is positive definite, in particular its determinant is $>0$, i.e.  $\phi_{tt}> \frac{\phi_{tx}^2}{\phi_{xx}}$. 
* Let $u(x) = \phi_t(t,x) - \tilde{\phi}_t(t)$, $\psi(x) = \phi(t,x)$, the $L^2$ estimate implies $\int_{|x|<1}(\phi_t - \tilde{\phi}_t)^2d\mu_t \geq \int_{|x|<1}\frac{\phi_{tx}^2}{\phi_{xx} }d\mu_t $

Hence $\tilde\phi_{tt}> 0$. This finishes the proof ot the theorem.



### Bochner identity and proof of $L^2$

#### The Bochner identity of real $\frac{d}{dx}$

##### Formal adjoint of $\frac{d}{dx}$ on $L^2(e^{-\psi})$

* Let $\delta\alpha$ be given such that $\frac{d}{dx}(e^{-\psi}\alpha ) = (\alpha_x - \alpha \psi_x)e^{-\psi} = e^{-\psi} \cdot \delta\alpha$. 

* When $\alpha$ is a test function, $\int \alpha\beta_x e^{-\psi}dx = -\int \beta d(e^{-\psi}\alpha) = \int \beta \cdot \delta\alpha \cdot e^{-\psi}dx$, i.e. $\langle \alpha, \frac{d}{dx}\beta\rangle = \langle \delta\alpha, \beta\rangle$ in $L^2$ of measure $e^{-\psi}dx$.  

##### Bochner identity

$$(\alpha^2e^{-\psi})_{xx} = ((\delta\alpha)^2+2(\delta\alpha)_x\alpha + \alpha_x^2 + \psi_{xx}\alpha ^2 )e^{-\psi},$$ where $\delta\alpha = \alpha_x -\alpha \psi_x$.

*Proof.* 

* First we have the formula $(\alpha\beta e^{-\psi})_x = (\beta\cdot\alpha e^{-\psi})_x = (\alpha e^{-\psi})_x\beta + \beta_x \cdot \alpha e^{-\psi} = \delta\alpha \cdot e^{-\psi} \cdot \beta+ \alpha\beta_x e^{-\psi}$.

* Then 
  * $(\alpha^2e^{-\psi})_x = (\alpha\cdot \delta\alpha+\alpha\alpha_x)e^{-\psi}$.
  * $(\alpha^2e^{-\psi})_{xx} = (\alpha \cdot \delta\alpha e^{-\psi})_x + (\alpha \alpha_x e^{-\psi})_x$ then apply the formula again taking $\beta = \delta\alpha$ and $\alpha$ respectively, we get
    * $(\alpha\delta\alpha e^{-\psi})_x = [(\delta\alpha)^2+\alpha(\delta \alpha)_x] e^{-\psi}]$; 这里要凑$(\delta\alpha)^2$
    * $(\alpha_x \alpha e^{-\psi})_x = (\alpha \cdot\delta\alpha_x + \alpha_x^2)e^{-\psi}$; 这里不能出现$\alpha_{xx}$
    * $\delta\alpha_x -(\delta\alpha)_x = \alpha\psi_{xx}$, in other words, $[\delta,\frac{\partial}{\partial x}]\alpha = (\Delta\psi)\cdot \alpha.$
  * Hence the desired equality follows from the above three computations.

##### Integration of Bochner identity

If $\alpha$ has compact support on $\mathbb{R}$, then $\int$ LHS = 0, $\int \alpha (\delta \alpha)_x e^{-\psi}dx = \langle \alpha, \frac{d}{dx}\delta\alpha\rangle = -\langle \delta\alpha, \delta\alpha\rangle = \int (\delta\alpha)^2 e^{-\psi} dx,$ it follows that

$$\int (\delta\alpha)^2 e^{-\psi} dx = \int \alpha_x^2 e^{-\psi} dx + \int \psi_{xx}\cdot \alpha^2 e^{-\psi} dx,$$

in other words, $\|\delta\alpha\|^2 = \|\frac{d}{dx}\alpha\|^2 + \int \Delta\psi \cdot \alpha^2 e^{-\psi}$.



##### Functional analysis lemma

​	Let $(V,(,))$ be an inner product space, let $b(,)$ be another inner product on $V$.

​	Let $H_b$ be the completion of $V$ under $b(,)$.  Let $\tilde b$ denote its unique extension on $H_b$.

​	For $v\in H$, if $|b(\alpha,\alpha)|\geq C |(\alpha,v)|^2$ for some constant $C>0$ and any $\alpha\in V $, 

then there exists a unique $u\in H_b $ such that $b(u,\cdot) = (\cdot, v)$ on $V$ with $\tilde b(u,u)\leq \frac{1}{C}$.



*Proof.* Define functional $F_v(\cdot):=b(\cdot,v)$, then the lower estimate of $b(\alpha,\alpha)$ implies that $\frac{|F_v(\alpha)|^2}{b(\alpha,\alpha)}\leq \frac{1}{C}$. 

So $F_v(\cdot)$ is a bounded linear functional on the pre-Hilbert space  $(V, b(,))$.

Let $H_b$ be the completion of $(H,b(,))$. Then $F_v$ extends uniquely to a bounded linear functional $\tilde F_v$ on $H_b $. Apply the Riesz representation theorem on $H_b $ we get an element $u\in H_b $ such that $\tilde b(\cdot, u) = \tilde F_v(\cdot)$ on $H_b$. The conclusion follows by restricting on $V$.

##### Lemma

For any smooth $v$ on $I$ , there exists $g\in L^2(I,e^{-\psi})$ such that $\frac{d}{dx}g = v$ in sense of distribution and $\int_I g^2 e^{-\psi}\leq \int_I \frac{v^2}{\psi_{xx}}e^{-\psi}.$

*Proof.* Define $b(\alpha,\beta):=\int_{I}\delta\alpha\cdot \delta\beta e^{-\psi}dx$ on $\mathscr{C}_c^\infty(I)$. Then $b(\alpha,\alpha)\geq \frac{|(\alpha,v)|^2}{\int_I  \frac{v^2}{\psi_{xx}}dx}$. 

To see this, by the Cauchy Schwartz inequality we get 

$$(\int_{I}\alpha\cdot v e^{-\psi})^2$$....

Let $H_b$ be the completion of $\mathscr C_c^{\infty}(I)$. It follows by the functional analysis lemma that there exists $u\in H_b$ such that $\tilde{b}(u,\cdot) = (v,\cdot)$ on $\mathscr{C}_c^{\infty}(I)$. 

By definition of completion, $u$ is represented by a $b$-Cauchy sequence $(u_n)_{n=1}^{\infty}$ in $\mathscr{C}_b^{\infty}$. Claim: $(u_n)$ is also a Cauchy sequence in $L^2(I,e^{-\psi})$. Indeed, it sufficies to show that $b(\alpha,\alpha)\geq C'(\alpha,\alpha)$ for some constant $C'$ and every $\alpha\in \mathscr{C}_c^{\infty}(I)$. By the Bochner identity $b(\alpha,\alpha)\geq \int\alpha^2\psi_{xx}e^{-\psi}\geq \inf_{I}\psi_{xx} \cdot \int_{I}\alpha^2e^{-\psi}$. Then we can take $C'$ to be $\inf_I\psi_{xx}$.

It follows that $u$ lies in $L^2(I,e^{-\psi})$. Taking $\delta, \frac{d}{dx}$ in the sense of distribution on $L^2(I,e^{-\psi})$, we have $(\frac{d}{dx}(-\delta u),\alpha) = (v,\alpha)$ for any $\alpha \in\mathscr{C}_c^{\infty}(I)$. Note that $\mathscr{C}_c^{\infty}(I)$ is dense, let $g = -\delta u$ then $g$ is what we want.



#### Hormander's estimate

$\psi$ smooth subharmonic on $\mathbb{C}$. Then for any $v$ smooth on $\mathbb{C}$, there exists smooth $u$ on $\mathbb{C}$ such that $\frac{\partial}{\partial \bar{z}}u = v$, with $\int |u|^2e^{-\phi}\leq \int \frac{|v|^2}{\psi_{z\bar{z}}}e^{-\phi}$. 

##### Bochner formula -- complex case

* $(|\alpha|^2e^{-\phi})_{z\bar{z} } = (|\delta\alpha|^2 +2Re((\delta\alpha)_{\bar{z}} \bar{\alpha} ) + |\alpha_{\bar{z}}|^2 + \psi_{z\bar{z}}|\alpha|^2)e^{-\psi}$.
* If $\alpha$ has compact support then $\int |\delta \alpha|^2 e^{-\psi} = \int|\alpha_{\bar{z}}|^2 e^{-\psi} + \int \psi_{z\bar{z}} |\alpha|^2 e^{-\psi}$.

*Proof.*

* $(\alpha e^{-\psi})_z = (\alpha_z-\alpha\psi_z)e^{-\psi} = \delta\alpha\cdot e^{-\psi}$, where $\delta\alpha = \alpha_z - \alpha \psi_z$ ; 
  *  $(\bar{\alpha}e^{-\psi})_{\bar{z}} = \overline{\delta\alpha}\cdot e^{-\psi}$.
* $(|\alpha|^2e^{-\psi})_{\bar{z}} = (\alpha \cdot {\bar\alpha e^{-\psi}})_{\bar{z}} = \alpha_{\bar{z}}\cdot \bar\alpha e^{-\psi}+\alpha\cdot \overline{\delta\alpha}\cdot e^{-\psi}$.
  * $\frac{\partial}{\partial z} LHS = (\bar{\alpha}\cdot (\alpha_\bar{z}e^{-\psi}))_z + (\overline{\delta \alpha}\cdot (\alpha e^{-\psi}))_z$
  * $(\bar{\alpha}\cdot (\alpha_\bar{z}e^{-\psi}))_z = \bar{\alpha}_z \alpha_{\bar{z}}e^{-\psi} + \bar\alpha \delta \alpha_{\bar z} e^{-\psi}$.
  * $(\overline{\delta \alpha}\cdot (\alpha e^{-\psi}))_z = \alpha_z \cdot \overline{\delta\alpha} e^{-\psi} + |\delta\alpha|^2 e^{-\psi}$.
  * Note: $[\delta,\frac{\partial}{\partial \bar{z}}]\alpha = \psi_{z\bar z}\cdot \alpha$.

* When $\alpha$  is a test function, $(\alpha,\beta_{\bar z}) = \int \alpha \overline{\beta_{\bar z}}e^{-\psi} = \int \alpha e^{-\psi}\cdot\frac{\partial }{\partial z}\bar{\beta} = 0 - \int \bar{\beta}\frac{\partial}{\partial z}(\alpha e^{-\psi}) = -\int \bar{\beta}\cdot \delta\alpha\cdot e^{-\psi} = (\delta \alpha, \beta) $.

##### Proof of Hormander estimate

Define bilinear $b(\alpha,\beta) = \int \delta \alpha \cdot \overline{\delta \beta} e^{-\psi}.$ Then $b(\alpha,\alpha)\geq |(\alpha,v)|/\int \frac{|v|^2}{\psi_{xx}}e^{-\psi}$ by Bochner fromla. Then we can solve $b(\cdot, u) = (\cdot, v)$ with $b(u,u) = \|\delta u\|^2_{\psi} \leq \int \frac{|v|^2}{\psi_{z\bar z}}e^{-\psi}$. That means $-(\alpha,\frac{\partial}{\partial \bar z}\delta u) = (\delta \alpha, \delta u) = (\alpha, v)$, so $-\delta u$ is the desired solution.



### $L^2$ on compact complex manifolds

#### Bochner formula on complex manifolds



* 整理昨天讨论班的note
* 写complex prekopa theorem
* 写complex manifold case的note
* 读一下泛函分析, 准备一下习题课




