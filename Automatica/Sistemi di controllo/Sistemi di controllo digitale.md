>[!note]
>Piuttosto che usare un regolatore $R(s)$ analogico, più conveniente usare un regolatore digitale, che si compone di un campionatore $C$, un regolatore $R$ e un mantenitore $M$. L'obiettivo è rendere questo sistema il più vicino possibile ad un regolatore analogico.
>
>![[Pasted image 20260607190539.png|center]]

### Trasformata zeta
>[!note]
>Sia $e^{*}(k)$ un segnale campionato. Definiamo la sua trasformata zeta come: $$E^{*}(z)=\mathcal{Z}(e^{*}(k))=\sum\limits_{k=0}^{+\infty}e^{*}(k)z^{-k}$$
>Questa è una funzione fratta: $$E^{*}(z)= \frac{N(z)}{D(z)}\qquad z\in\mathbb{C}$$

>[!tip] Proprietà
>Siano $s_{1}^{*}(k),s_{2}^{*}(k)\in\mathbb{C}$, e $\alpha,\beta\in\mathbb{C}$. Si ha che la trasformata zeta è lineare: $$\mathscr{L}(\alpha s_{1}^{*}(k)+ \beta s_{2}^{*}(k))= \alpha\mathscr{L}(s_{1}^{*}(k))+\beta \mathscr{L}(s_{2}^{*}(k))$$
>Sia $s^{*}(k)\in\mathbb{C}$, $\alpha\in\mathbb{C}$ e $S(z)$ la sua trasformata. Si ha che: $$\begin{align*}
>&\mathcal{Z}(s^{*}(k-1))= z^{-1}S^{*}(z)\\
>&\mathcal{Z}(s^{*}(k+1))=z\cdot S(z)-z\cdot S(0)\\
>&
>\end{align*}$$

### Funzione di trasferimento a tempo discreto
>[!note]
>Sia un sistema a tempo discreto caratterizzato da: $$\begin{cases}
>x^{*}(k+1)&= Ax^{*}(k)+Bu^{*}(k) \\
>y^{*}(k)&=Cx^{*}(k)+Du^{*}(k) 
>\end{cases}$$
>Dalla trasformata zeta possiamo ricavare che: $$Y^{*}(z)=\underbrace{C(zI-A)^{-1}z}_{\mathcal{Z}(y_{L}^{*}(k))}X^{*}(0)+\underbrace{(C(zI-A)^{-1}B+D)}_{\mathcal{Z}(y^{*}_{F}(k))=G^{*}(z)}U^{*}(z)$$
>Dove $G^{*}(z)$ è la funzione di trasferimento a tempo discreto.

Vale ancora che tutti i poli sono autovalori della matrice $A$, pertanto: $$|\text{poli}|<1\quad\text{cond. necessaria per asintotica stabilità}$$
>[!tip] Rappresentazione esterna nel tempo
>Sia: $$Y^{*}(z)= \frac{\beta_{0}+\beta_{1}z^{-1}+\cdots \beta_{u}z^{-u}}{1+ \alpha_{1}z^{-1}+\cdots+ \alpha_{v} z^{-v}}U^{*}(z)$$
>Tramite l'antitrasformata zeta è possibile trovare la rappresentazione esterna nel tempo: $$\begin{align*}
>y^{*}(k)&= - \alpha_{1}y^{*}(k-1)-\cdots-\alpha_{v}y^{*}(k-v)\\
>&=+\beta_{0}u^{*}(k)+ \beta_{1}u^{*}(k-1)+\cdots+ \beta_{u}u^{*}(k-u) 
>\end{align*}$$

### Discretizzazione di $R(s)$
>[!note]
>Supponiamo di voler discretizzare un integratore con $R(s)= \frac{1}{s}$, con $$u(t)=\int_{0}^{t}e(\tau)\text{ d}\tau$$
>Possiamo ricavare che: $$u^{*}(k)=u(kT_{s})\simeq u^{*}(k)+ (\alpha e^{*}(k)+(1-\alpha)e^{*}(k-1))T_{s}$$
>E di conseguenza che: $$U^{*}(z)= \underbrace{\frac{\alpha+(1-\alpha)z^{-1}}{1-z^{-1}}}_{R^{*}(z)}E^{*}(z)$$

Si ha che: $$\begin{align*}
&R(s)\text{ razionale}\implies R^{*}(z)\text{ razionale}\\
&R(s)\text{ propria e di ordine }n\implies R^{*}(z)\text{ propria e di ordine }n\text{ (se }\nexists\text{ poli in }s= \frac{1}{\alpha T_{s}}\text{)}\\
&R(s)\text{ stabile}\implies R^{*}(z)\text{ stabile se }\alpha= \frac{1}{2},1\text{ oppure }\alpha=0\text{ e } T_{s}\text{ sufficientemente piccolo}  
\end{align*}$$

### Campionatore
>[!note]
>Quando campioniamo un segnale utilizziamo il teorema di Shannon per costruire il segnale campionato, e utilizziamo un filtro anti aliasing per ridurre il rumore: $$F_\text{AA}(s)= \frac{1}{1+\frac{s}{\omega_{\text{AA}}}}$$
>Con $\omega_{s}> 2\omega_{\text{AA}}$ e generalmente $\omega_{\text{AA}}\in[10 \omega_{c},20\omega_{c}]$.

>[!tip] Teorema di Shannon
>Dato un segnale $e(t)$ di banda $[0,\overline{\omega}]$ esso è univocamente ricostruibile dalla sua versione campionata se: $$\omega_{s}= \frac{2\pi}{T_{s}}>2 \overline{\omega}\iff T_{s}< \frac{\pi}{\overline{\omega}}$$