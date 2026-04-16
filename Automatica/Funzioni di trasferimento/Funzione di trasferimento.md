>[!note]
>Sia un sistema lineare tempo-invariante continuo: $$\begin{cases}
>\stackrel{\circ}{x}(t)=Ax(t)+Bu(t) \\
>y(t)=Cx(t)+Du(t)
>\end{cases}$$
>Siano note $x(0)=x_{0}$ e $U(s)=\mathscr{L}(u(t))$. Si ha che, applicando le trasformate di Laplace: $$\begin{align*}
>\mathscr{L}(\stackrel{\circ}{x})=A\mathscr{L}(x)+B\mathscr{L}(u)\\
>\mathscr{L}(y)=A\mathscr{L}(x)+D\mathscr{L}(u)
>\end{align*}$$
>Si ha che: $$\begin{align*}
>sX(s)-x_{0}=AX(s)+BX(s)&\iff X(s)=(sI-A)^{-1}(x_{0}+BU(s))\\
>Y(s)=CX(s)+DU(s)&\iff C(sI-A)^{-1}x_{0}+(\underbrace{C(sI-A)^{-1}b+D}_{\text{Funzione di trasferimento}})U(s)
>\end{align*}$$
>Nello specifico, chiamiamo la funzione di trasferimento come $G(s)$.

>[!tip] Modelli equivalenti
>Siano $m_{1}$ e $m_{2}$ due modelli equivalenti. Si ha che questi hanno uguale funzione di trasferimento.

La funzione di trasferimento è razionale, in particolare il suo denominatore è il polinomio caratteristico di $A$: $$G(s)= \frac{N(s)}{D(s)}= \frac{N(s)}{p_{A}(s)}$$
Il denominatore della funzione di trasferimento $D(s)$ ha un grado $u\leq n$. Nello specifico $u<n$ se e solo se esistono stati non osservabili o non raggiungibili, altrimenti $u=n$.

Inoltre ricordiamo che i poli sono gli autovalori del sistema.

>[!tip] Stabilità asintotica
>È condizione necessaria per stabilità asintotica del sistema che $\text{Re}(s)<0$ per tutti i poli della funzione di trasferimento. Questa condizione diventa anche sufficiente quando $u=n$.

### Forma di Nyquist e forma di Bode
>[!note]
>Data una funzione di trasferimento $G(s)$, questa si può portare in forma di Nyquist:
>$$G(s)=\frac{\rho}{s^{g}}\cdot \frac{\prod (s+z_{i})}{\prod(s+p_{i})}\cdot\frac{\prod(s^{2}+2\zeta_{i}\alpha_{n_{i}}s+\alpha_{n_{i}}^{2})}{\prod(s^{2}+2\xi_{i}\omega_{n_{i}}s+\omega_{n_{i}}^{2})}$$
>Oppure in forma di Bode:
>$$G(s)= \frac{\mu}{s^{g}}\cdot\frac{\prod(1+\tau_{i}s)}{\prod(1+T_{i}s)}\cdot\frac{\prod\left(1+2 \frac{\zeta_{i}}{\alpha_{n_{i}}}s + \frac{s^{2}}{\alpha_{n_{i}}^{2}}\right)}{\prod \left(1+ 2 \frac{\xi}{\omega_{n_{i}}}s+ \frac{s^{2}}{\omega_{n_{i}}^{2}}\right)}$$
>Con $\rho$ costante di trasferimento, $\mu$ guadagno generalizzato, $g$ tipo della funzione di trasferimento, $-z_{i}$ zeri reali, $-p_{i}$ poli reali, $\tau_{i}$ costanti di tempo dello zero, $T_{i}$ costante di tempo del polo, $|\zeta_{i}|<1,|\xi_{i}|<1$ smorzamenti e $\omega_{n_{i}},\alpha_{n_{i}}$ pulsazioni naturali.

Si ha da queste formule che i poli complessi coniugati sono: $$s=-\xi_{i}\omega_{n_{i}}\pm j\omega_{n_{i}}\sqrt{1-\xi_{i}^{2}}$$
Mentre gli zeri complessi coniugati sono: $$s=\zeta_{i}\alpha_{n_{i}}\pm j\alpha_{n_{i}}\sqrt{1-\zeta_{i}^{2}}$$
### Risposta allo scalino
>[!note]
>Studiamo la risposta dell'uscita di sistemi asintoticamente stabili. Definiamo quindi: $$\begin{align*}
>y_{\infty}=\lim_{t\to\infty} y(t)\qquad&\text{Valore di regime}\\
>y_{\max}=\max_{t\geq0}y(t)\qquad&\text{Valore massimo}\\
>S\%= 100\cdot \frac{y_{\max}-y_{\infty}}{y_{\infty}}\qquad&\text{Sovraelongazione massima percentuale}\\
>|y(t)-y_{\infty}|< \frac{\varepsilon}{100}y_{\infty}\quad\forall t\geq T_{\alpha_\varepsilon}\qquad&\text{Tempo di assestamento}\\
>T_{p}\text{ Distanza temporale tra due massimi dell'uscita }\qquad&\text{Periodo di oscillazione}
>\end{align*}$$

Dato $G(s)$ (dopo aver svolto le opportune cancellazioni polo-zero), i poli dominanti sono i poli complessi nettamente più vicini all'asse immaginario rispetto agli altri.

La risposta allo scalino di un sistema con poli dominanti può essere approssimata con quella di un sistema con funzione di trasferimento avente soltanto il polo dominante e il guadagno pari a quello di partenza. È quindi opportuno tener conto di zeri che abbiano distanza dall'asse immaginario confrontabile o minore con quella dei poli dominanti, oppure che abbiano parte reale positiva.

Qualora ci siano coppie polo-zero vicini tra loro nel piano complesso con parte reale negativa, è possibile forzare la cancellazione mantenendo invariati gli altri parametri (tra i quali il guadagno) per ottenere un modello approssimato di ordine ridotto ma con caratteristiche simili a quello di partenza.