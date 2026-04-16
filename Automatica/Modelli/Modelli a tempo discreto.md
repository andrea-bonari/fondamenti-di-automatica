>[!note]
>I modelli a tempo discreto sono modelli descritti da equazioni di stato del tipo: $$x(t+1)=f(x(t),u(t),t)\qquad t\in\mathbb{N}$$
>Nel caso lineare tempo invariante allora questa diventa: $$x(t+1)=Ax(t)+Bu(t)\qquad t\in\mathbb{N}$$

>[!tip] Equilibri
>Nei sistemi tempo invarianti fissiamo $u(t)=\overline{u}\quad\forall t$, e quindi $x(t+1)=f(\overline{x},\overline{u})$.
>
>Nei modelli lineari si ha: $$\overline{x}=A\overline{x}+B\overline{u}$$
>E quindi l'equilibrio esiste se e solo se $I-A$ è invertibile: $$\overline{x}=(I-A)^{-1}B\overline{u}\iff \det(I-A)=\prod_{i=1}^{\mu}(1-\lambda_{i})^n_{i}\neq0$$

>[!tip] Movimenti
>Nei sistemi lineari tempo invarianti, fissati $x(0)=x_{0}$ e $u(t)\quad\forall t$, possiamo dire che: $$x(t)=\underbrace{A^{t}x_{0}}_{\text{Movimento libero}}+\underbrace{\sum\limits_{i=0}^{t-1}A^{t-i-1}Bu(i)}_{\text{Movimento forzato}}$$
>Definiamo il movimento perturbato come il movimento con stesso $u(t)$ e $x(0)=\stackrel{\sim}{x}_{0}\neq x_{0}$: $$\stackrel{\sim}{x}(t)=A^{t}\stackrel{\sim}{x}_{0}+\sum\limits_{i=0}^{t-1}A^{t-i-1}Bu(i)$$
>Notando che: $$x(t)-\stackrel{\sim}{x}(t)=A^{t}(x_{0}-\stackrel{\sim}{x}_{0})$$
>Nel caso scalare possiamo dire che per $|a|>1$ allora $|\delta x(t)|$ diverge, per $|a|=1$ allora $\delta x(t)$ è limitato e per $|a|<1$ allora $\delta x(t)\stackrel{t\to+\infty}{\to}0$.
>
>Nel caso vettoriale si trovano gli autovalori di $A^{t}$, detti modi $\lambda_{i}^{t}=\rho_{i}^{t}e^{j\theta t}\in\mathbb{C}$. Quindi si studia la modulante reale di tutti $\rho^{t}_{i}$. Per $\rho_{i}>1$ $\lambda_{i}^{t}$ è divergente, per $\rho_{i}=1$ $\lambda_{i}^{t}$ è limitato e per $\rho_{i}<1$ $\lambda_{i}^{t}\stackrel{t\to+\infty}{\to}0$.
>
>Nel caso non diagonalizzabile ($\lambda_{i}$ con $n_{i}> g_{i}$) i modi saranno: $$\lambda_{i}^{t},t\lambda_{i}^{t},\cdots, t^{n_{i}-g_{i}}\lambda_{i}^{t}$$
>Nei nodi composti $t^{k}\lambda_{i}^{t}$, per $\rho_{i}\geq1$ allora diverge, altrimenti per $\rho_{i}<1$ allora converge.
>
>Quindi la condizione necessaria e sufficiente per l'asintotica stabilita è: $$|\lambda_{i}|<1\qquad \forall i=1,\cdots,\mu$$
>Mentre per la condizione sufficiente per l'instabilità è: $$\exists \lambda_{i}\quad\text{t.c.}\quad |\lambda_{i}|>1$$

### Studio della stabilità
>[!note]
>Esistono diversi metodi per lo studio per l'analisi della stabilità di modelli a tempo discreto. Ricordando la forma del polinomio caratteristico: $$p(\lambda)=\det(\lambda I-A)=a_{0}\lambda^{n}+a_{1}\lambda^{n-1}+\cdots+a_{n}$$
>Tra questi troviamo: $$\begin{align*}
>\left|\frac{a_{1}}{a_{0}}\right|<n\quad \left| \frac{a_{n}}{a_{0}}\right|<1\qquad&\text{necessaria non sufficiente}\\
>a_{0}\sum\limits_{i=0}^{n}a_{i}>0\qquad&\text{necessaria non sufficiente}\\
>a_{0}>a_{1}>\cdots>a_{n}>0\qquad&\text{sufficiente}\\
>\sum\limits_{i=1}^{n}|a_{i}|<a_{0}\qquad&\text{sufficiente}\\
>\text{criterio di Jury}\qquad&\text{sufficiente}
>\end{align*}$$

>[!tip] Criterio di Jury
>Dopo aver definito il polinomio caratteristico si definisce la tabella di Jury, una tabella triangolare di $n+1$ righe costruita in modo ricorsivo, la prima riga sarà costituita da: $$\begin{matrix}a_{0}&a_{1}&a_{2}&\cdots&a_{n}\end{matrix}$$
>La riga $k+1$-esima si costruisce dalla $k$-esima: $$\begin{matrix}k_{1}&k_{2}&\cdots&k_{n-1}&k_{n}\\l_{1}&l_{2}&\cdots&l_{n-1}\end{matrix}\qquad\qquad l_{i}= \frac{1}{k_{1}}\det\begin{pmatrix}k_{1}&k_{n-i+1}\\k_{n}&k_{i}\end{pmatrix}$$
>Se $k_{1}=0$ allora la tabella si dice non ben definita.
>
>Il criterio di Jury ci dice che il sistema è asintoticamente stabile se e solo se: $$\begin{cases}
>\text{tabella ben definita} \\
>\text{tutti i coefficienti hanno segno concorde}
>\end{cases}$$
>Per $n=2$, quindi $p(\lambda)=\lambda^{2}+a\lambda+ b$, si deve avere che: $$\text{sistema asintoticamente stabile}\iff |a|<(1+b)$$

### Linearizzazione
>[!note]
>Il processo di linearizzazione è analogo a quello in tempo continuo.

