>[!note]
>Consideriamo un modello lineare tempo-invariante a tempo continuo:
>$$\begin{cases}
>\stackrel{\circ}{x}=Ax+Bu \\
>y=Cx+Du
>\end{cases}$$

>[!tip] Equilibri
>L'equilibrio è dato dall'equazione: $$\overline{x}=-A^{-1}B\overline{u}\iff A\text{ invertibile}\iff \text{Rk}(A)=n$$

>[!tip] Principio di Sovrapposizione degli Effetti (PSE)
>Definiamo due movimenti:
>$$\begin{align*}
>\begin{cases}
>x(t_{0})=x_{1}(\cdot)\\
>u_{1}(t)
>\end{cases}\bigg|\Longrightarrow \begin{matrix}x_{1}(t)\\y_{1}(t)\end{matrix}\\
>\begin{cases}
>x(t_{0})=x_{2}(\cdot)\\
>u_{2}(t)
>\end{cases}\bigg|\Longrightarrow \begin{matrix}x_{2}(t)\\y_{2}(t)\end{matrix}
>\end{align*}$$
>Se definiamo:
>$$\begin{cases}x(t)=\alpha x_{1}(\cdot)+ \beta x_{2}(\cdot) \\u(t)= \alpha u_{1}(t) + \beta u_{2}(t)\end{cases}$$
>Allora: 
>$$\begin{cases}
>x(t)=\alpha x_{1}(t)+ \beta x_{2}(t) \\
>y(t)= \alpha y_{1}(t)+ \beta y_{2}(t)
>\end{cases}$$

>[!example] Dimostrazione
>Consideriamo:
>$$\begin{align*}
\stackrel{\circ}{x}&= Ax(t_{0})+ Bu(t_{0})\\
&= A(\alpha x_{1}(\cdot)+ \beta x_{2}(\cdot))+ B(\alpha u_{1}(\cdot)+ \beta u_{2}(\cdot))\\
&= A(\alpha x_{1}(\cdot)+ \beta u_{1}(\cdot))+ B(\alpha x_{2}(\cdot)+ \beta u_{2}(\cdot))\\
&= \alpha\stackrel{\circ}{x}_{1}(\cdot)+ \beta \stackrel{\circ}{x}_{2}(\cdot)
\end{align*}$$

### Movimento libero o forzato
>[!note]
>Considerato un movimento:
>$$\begin{cases}
>x(t_{0})=x_{0} \\
>u(t)
>\end{cases}\bigg|\Longrightarrow \begin{matrix}
>x(t) \\
>y(t)
>\end{matrix}$$
>Definiamo il movimento libero come:
>$$\begin{cases}
>x_{L}(t_{0})=x_{0} \\
>u_{L}(t)=0
>\end{cases}\bigg|\Longrightarrow\begin{matrix}x_{L}(t)\\y_{L}(t)\end{matrix}$$
>Definiamo inoltre il movimento forzato come:
>$$\begin{cases}
>x_{L}(t_{0})=0 \\
>u_{L}(t)=u
>\end{cases}\bigg|\Longrightarrow\begin{matrix}x_{F}(t)\\y_{F}(t)\end{matrix}$$

Per il PSE si ha che si ha che: $$\begin{cases}
x(t_{0})=x_{L}(t_{0})+ x_{F}(t_{0}) \\
u(t)= u_{F}(t_{0})+ u_{L}(t_{0})
\end{cases}\Longrightarrow
x(t) =x_{L}(t)+x_{F}(t) \\
y(t)$$
### Calcolo dei movimenti
>[!note]
>Consideriamo $\stackrel{\circ}{x}(\tau)=ax(\tau)+bu(\tau)\quad a,b\in\mathbb{R}$, per calcolare $x(t)$ dati $x(t_{0})=x_{0}$ e $u(t)$. Moltiplichiamo tutti i fattori per $e^{-a\tau}$:
>$$\stackrel{\circ}{x}(\tau)e^{-a\tau}- a x(\tau)e^{-a\tau}= bu(\tau)e^{-a \tau}$$
>Che si semplifica in: $$\frac{\text{d}}{\text{d}\tau}\left(x(\tau)e^{-a\tau}\right)=bu(\tau)e^{-a\tau}$$
>Integrando entrambi i lati:
>$$\int_{t_{0}}^{t}\frac{\text{d}}{\text{d}\tau}\left(x(\tau)e^{-a\tau}\right)\text{ d}\tau=\int_{t_{0}}^{t}bu(\tau)e^{-a\tau}\text{ d}\tau$$
>Che si semplifica in:
>$$x(t)e^-{a t}=x(t_{0})e^{-a t_{0}}+\int_{t_{0}}^{t}bu(\tau)e^{-a \tau}\text{ d}\tau$$
>Infine:
>$$x(t)=\underbrace{e^{a(t-t_{0})}x(t_{0})}_{x_{L}(t)}+\int_{t_{0}}^{t}e^{a(t-\tau)}bu(\tau)\text{ d}\tau$$
>Questa è detta equazione di Lagrange.

Consideriamo un movimento libero ($t_{0}=0$):

$$x_{L}(t)=e^{at}x_{0}$$
Per $a=0$ si ha movimento libero costante.
Per $a>0$ si ha comportamento divergente
Per $a<0$ si ha comportamento convergente a 0.

Studiamo il caso negativo, in quanto tempo $x_{L}(t)$ raggiunge l'$\varepsilon$% del valore iniziale?

$$x_{L}(\overline{t})=e^{a \overline{t}}x_{0}= \frac{\varepsilon}{100} x_{0}$$
Si nota subito che il problema non dipende dalla condizione iniziale.
$$|a|\overline{t}=\left|\log\left( \frac{\varepsilon}{100}\right)\right|\Longrightarrow \overline{t}= \frac{|\log\left(\frac{\varepsilon}{100}\right)|}{|a|}=\overline{\tau}\left|\log\left( \frac{\varepsilon}{100}\right)\right|$$
Con $\tau$ costante di tempo del sistema.

Se per esempio $\varepsilon=1$, allora $\overline{t}\cong 5\overline{\tau}$.

---

Consideriamo il caso vettoriale, l'equazione di Lagrange sarà:
$$x(t)=e^{A(t-t_{0})}x_{0}+ \int_{t_{0}}^{t}e^{A(t-t_{0})}Bu(\tau)\text{ d}\tau$$

