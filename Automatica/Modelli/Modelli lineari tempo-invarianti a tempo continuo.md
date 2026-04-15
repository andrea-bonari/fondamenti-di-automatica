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
>Definiamo il suo movimento libero come:
>$$\begin{cases}
>x_{L}(t_{0})=x_{0} \\
>u_{L}(t)=0
>\end{cases}\bigg|\Longrightarrow\begin{matrix}x_{L}(t)\\y_{L}(t)\end{matrix}$$
>Definiamo inoltre il suo movimento forzato come:
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
### Studio del movimento
>[!note]
>Sia $\stackrel{\circ}{x}(\tau)=ax(\tau)+bu(\tau)\quad a,b\in\mathbb{R}$. Per calcolare $x(t)$, dati $x(t_{0})=x_{0}$ e $u(t)$ usiamo l'equazione di Lagrange:
>$$x(t)=\underbrace{e^{a(t-t_{0})}x(t_{0})}_{x_{L}(t)}+\int_{t_{0}}^{t}be^{a(t-\tau)}u(\tau)\text{ d}\tau$$
>Nel caso vettoriale, quindi con $\stackrel{\circ}{x}(\tau)=Ax(\tau)+Bu(\tau)\quad A,B\in\mathbb{R}^{n\times n}$. Si ha quindi che: $$x(t)=\underbrace{e^{A(t-t_{0})}x(t_{0})}_{x_{L}(t)}+\int_{t_{0}}^{t}Be^{A(t-\tau)}\cdot u(\tau)\text{ d}\tau$$
>Con:
>$$x_{L}(t)=\gamma_{1}e^{\lambda_{1}t}+\cdots+\gamma_{1\mu}e^{\lambda_{\mu}t}$$
>Dove $\lambda_{i}\in\mathbb{C}$ sono gli autovalori di $e^{At}$, e $e^{\lambda_{i}}t$ modi propri del sistema.

>[!example] Dimostrazione
>Il caso lineare è dimostrato [qui](https://andrea-bonari.github.io/analisi-matematica-2/Equazioni-differenziali/EDO-del-primo-ordine/EDO-del-primo-ordine).
>Per quanto riguarda il caso vettoriale, ricordando che $A^{k}=T^{-1}A_{0}^{k}T$, con $A_{0}$ matrice diagonale.
>Per la definizione di matrice esponenziale possiamo dire che: $$e^{At}=A^{A_{0}t}=\text{diag}(e^{\lambda_{1}t},\cdots,e^{\lambda_{\mu}t})\qquad \lambda_{i}\in\mathbb{C}$$
>Quindi il movimento libero diventa: $$x_{L}(t)=x_{0}e^{At}=T^{-1}e^{A_{0}t}T$$

Analizziamo un modo qualsiasi di un sistema. Si ha che: $$\lambda_{i}=\alpha +j\omega\iff e^{\lambda_{i}t}=e^{(\alpha+j\omega)t}=e^{\alpha t}\left(\cos(\omega t)+j\sin(\omega t)\right)$$
Possiamo dire che:
- Per $\alpha=0$ allora il modo è limitato.
- Per $\alpha<0$ si ha che il modo converge a $0$.
- Per $\alpha>0$ si ha che il modo diverge.

>[!tip] Caso generale
>Abbiamo finora visto il caso diagonalizzabile. Nel caso di non diagonalizzabilità si può usare la forma di Jordan. In questo caso si usa la regola generale, dove i modi propri corrispondenti ad un autovalore $\lambda_{i}$ con $n_{i}< g_{i}$ sono:
>$$e^{\lambda_{i}t}, te^{\lambda_{i}t},\cdots t^{n_{i}-g_{i}}e^{\lambda_{i}t}$$
>In questo caso per $\alpha\geq0$ il modo diverge, mentre per $\alpha<0$ il modo converge a $0$.
>

Si ha quindi che il movimento libero:
- Converge a $0$ se e solo se $\text{Re}(\lambda_{i})<0\quad\forall i=1,\cdots,\mu$.
- È limitato quando $\begin{cases}\text{Re}(\lambda_{i})<0\quad&n_{i}\neq g_{i}\\\text{Re}(\lambda_{i})=0\quad&n_{i}=g_{i}\end{cases}\quad \forall i=1,\cdots,\mu$
- Diverge quando $\exists\lambda_{i}\quad\text{t.c.}\quad\text{Re}(\lambda_{i})>0$ oppure $\exists \lambda_{i}\quad\text{t.c.}\quad \text{Re}(\lambda_{i})=0\quad n_{i}>g_{i}$.

>[!tip] Tempo del sistema
>Consideriamo un generico sistema con $x_{L}(t)=x_{0}e^{a t}$, si ha che per $a<0$ questo converge a $0$. Per studiare in quanto tempo $x_{L}(t)$ raggiunge l'$\varepsilon\space\%$ del valore iniziale si impone: $$x_{L}(\overline{t})=x_{0}e^{a\overline{t}}= \frac{\varepsilon x_{0}}{100}$$
>Risolvendo questa equazione si nota che: $$\overline{t}=\frac{\left|\log\left(\frac{\varepsilon}{100}\right)\right|}{|a|}=\tau\left|\log\left(\frac{\varepsilon}{100}\right)\right|$$
>Con $\tau$ costante di tempo del sistema.

### Stabilità
>[!note]
>Sia $x(t)$ un generico movimento, e $\stackrel{\sim}{x}(t)$ il suo movimento perturbato.
>Si ha che $x(t)$ è stabile se e solo se: $$\forall\varepsilon>0\quad\exists \delta\qquad ||x_{0}-\stackrel{\sim}{x}_{0}||<\delta,\quad||\underbrace{x(t)-\stackrel{\sim}{x}(t)}_{e^{At}(x_{0}-\stackrel{\sim}{x}_{0})=\delta x_{0}\cdot e^{At}}||<\varepsilon$$
>Si ha che se $\delta x_{0}\cdot e^{At}$ è limitato oppure tende a zero, allora $x(t)$ è stabile.
>Alternativamente se $\delta x_{0}\cdot e^{At}$ diverge allora $x(t)$ è instabile.

La stabilità di $x(t)$ dipende solamente dagli autovalori $\lambda_{i}$, e quindi possiamo definire il seguente criterio:
$$\begin{align*}
\text{Sistema asintoticamente stabile}&\iff\text{Re}(\lambda_{i})<0\quad\forall i=1,\cdots,\mu\\
\text{Sistema instabile}&\iff\exists \lambda_{i}\quad\text{t.c.}\quad \text{Re}(\lambda_{i})>0
\end{align*}$$

Inoltre, per sistemi asintoticamente stabili, se per $t\to\infty$ si ha $x_{L}(t)\to0$, allora $x(t)\to x_{F}(t)$.

>[!tip] Equilibri
>Se $\det(A)=\sum\limits_{i=1}^{\mu}\lambda_{i}^{n_{i}}\neq0$ allora $A$ è invertibile, e pertanto: $$\exists! \overline{x}=-A^{-1}B\overline{u}$$
>Con $\overline{x}$ equilibrio asintoticamente stabile. Si ha quindi che per $x_{0}\neq \overline{x}$ e $u(t)=\overline{u}$: $$x(t)-\overline{x}\stackrel{t\to+\infty}{\to}0$$

Si ha inoltre, che per sistemi asintoticamente stabili, se $u(t)$ è limitato in ampiezza $|u(t)|\leq\overline{u}$, allora anche $x_{F}(t)$ lo è. In questo caso la stabilità è detta bounded-input bounded-state (BIBS).

### Stabilità asintotica
>[!note]
>Dal criterio per stabilità asintotica $\text{Re}(\lambda_{i})\quad\forall i=1,\cdots,\mu$ possiamo definire i seguenti criteri:
>$$\begin{align*}
>\text{tr}(A)&=\sum\limits_{i=1}^{\mu}n_{i}\lambda_{i}<0\qquad&\text{necessaria non sufficiente}\\
>\text{sgn}(\det(A))&= (-1)^{n}\qquad&\text{necessaria non sufficiente}\\\\
>\text{segni del polinomio }&\text{caratteristico concordi}\qquad&\text{necessaria non sufficiente}\\
>\\\text{criterio }&\text{di Routh}&\text{necessaria e sufficiente}
>\end{align*}$$

>[!tip] Criterio di Routh
>Sia dato il polinomio caratteristico di una matrice $A\in\mathbb{R}^{n\times n}$: $$\det(\lambda I-A)=a_{0}\lambda^{n}+a_{1}\lambda^{n-1}+\cdots+a_{n}$$
>Si crea da questo la tabella di Routh-Hurwitz, una tabella definita in modo ricorsivo da $a_{i}\quad i=0,\cdots,n$. Questa è triangolare ed è composta da $n+1$ righe. Le prime due righe sono composte da:
>$$\begin{matrix}a_{0}&a_{2}&a_{4}&\cdots\\a_{1}&a_{3}&a_{5}&\cdots\end{matrix}$$
>Date le due righe precedenti queste si definiscono nel seguente modo:
>$$\begin{matrix}h_{1}&h_{2}&h_{3}&h_{4}&\cdots\\k_{1}&k_{2}&k_{3}&k_{4}&\cdots\\l_{1}&l_{2}&l_{3}&\cdots\end{matrix}\qquad\qquad l_{i}=- \frac{1}{k_{1}}\det\begin{pmatrix}h_{1}&h_{i+1}\\k_{1}&k_{i+1}\end{pmatrix}$$
>In caso $k_{1}=0$ allora la tabella si dice non ben definita.
>
>Il numero di cambiamenti di segno della prima tabella è pari al numero di autovalori $\lambda_{i}$ con $\text{Re}(\lambda_{i})>0$
>
>Una volta definita la tabella, il sistema è asintoticamente stabile se e solo se: $$\text{Sistema asintoticamente stabile}\iff\begin{cases}
>\text{Tabella ben definita} \\
>\text{Coefficienti della prima colonna di segno concorde}
>\end{cases}$$

### Modelli equivalenti
>[!note]
>Siano un modello: $$\begin{cases}
>\stackrel{\circ}{x}=Ax+Bu \\
>y=Cx+Du
>\end{cases}$$
>E sia $\stackrel{\sim}{x}=Qx$ con $Q$ matrice invertibile. Si ha quindi che: $$\begin{cases}
>\stackrel{\stackrel{\circ}{\sim}}{x}=\stackrel{\sim}{A}\stackrel{\sim}{x}+\stackrel{\sim}{B}u \\
>y=\stackrel{\sim}{C}\stackrel{\sim}{x}+\stackrel{\sim}{D}u
>\end{cases}$$
>Dove $\stackrel{\sim}{A}=QAQ^{-1}$, $\stackrel{\sim}{B}=QB$, $\stackrel{\sim}{C}=CQ^{-1}$ e $\stackrel{\sim}{D}=D$.

Notiamo che $\stackrel{\sim}{A}=QAQ^{-1}$ implica la similitudine di $A$ e $\stackrel{\sim}{A}$ e pertanto hanno gli stessi modi propri. Inoltre, se $Q=T$ allora $\stackrel{\sim}{A}$ è $A$ diagonalizzata.