>[!note]
>Consideriamo una funzione di trasferimento in forma di Bode: $$G(j\omega)= \frac{\mu}{(j\omega)^{g}}\cdot\frac{\prod(1+\tau_{i}j\omega)}{\prod(1+T_{i}j\omega)}\cdot\frac{\prod\left(1+2 \frac{\zeta_{i}}{\alpha_{n_{i}}}j\omega + \frac{(j\omega)^{2}}{\alpha_{n_{i}}^{2}}\right)}{\prod \left(1+ 2 \frac{\xi}{\omega_{n_{i}}}j\omega+ \frac{(j\omega)^{2}}{\omega_{n_{i}}^{2}}\right)}$$
>È possibile tracciare due diagrammi di Bode del modulo e della fase sulla carta semilogaritmica:
>![[Pasted image 20260420154705.png|center]]
>La cui asse delle ascisse è $\omega$ (in $\frac{\text{rad}}{\text{s}}$) in scala logaritmica.
>
>Per prima cosa si indica un fondoscala $\omega_{0}=10^{k}$, indicata in un punto qualsiasi della carta, in dei punti che precedono un intervallo più largo. In questo formato, la distanza tra due punti $\omega_{1}>\omega_{0}$ è data da: $$\alpha\log_{10}\omega_{1}=\log_{10}\omega_{0}$$
>Si ha che la distanza tra una pulsazione $\omega_{0}$ e la pulsazione $10$ volte più avanti è detto una decade.
>![[Pasted image 20260420155507.png|center]]
>Per tracciare il diagramma del modulo troviamo la funzione di trasferimento in decibel: $$\begin{align*}
>|G(j\omega)|_{\text{dB}}&= 20\log_{10}|G(j\omega)|\\
>&=20\log_{10}|\mu|+\sum\limits20\log|1+j\omega\tau_{i}|-\sum\limits20\log|1+j\omega T_{i}|\\
>&\space-\sum\limits20\log_{10}\left|1- \frac{\omega^{2}}{\alpha_{n_{i}}^{2}}+2j\zeta_{i} \frac{\omega}{\alpha_{n_{i}}}\right|-\sum\limits20\log_{10}\left|1- \frac{\omega^{2}}{\omega_{n_{i}}^{2}}+2j\xi_{i} \frac{\omega}{\omega_{n_{i}}}\right|\\
>&\space-g20\log_{10}(\omega)
>\end{align*}$$
>Mentre per tracciare il diagramma della fase troviamo la funzione di trasferimento: $$\begin{align*}
>\angle G(j\omega)&= k\mu+\sum\limits\angle(1+j\omega \tau_{i})-\sum\limits\angle(1+j\omega T_{i})\\
>&\space-\sum\limits\angle\left(1- \frac{\omega^{2}}{\alpha_{n_{i}}^{2}}+ 2 \frac{\zeta}{\alpha_{n_{i}}}\omega \right)-\sum\limits\angle\left(1- \frac{\omega^{2}}{\omega_{n_{i}}^{2}}+ 2 \frac{\zeta}{\omega_{n_{i}}}\omega \right)\\
>&\space-g\angle(j\omega)
>\end{align*}$$
>Da queste funzioni si studiano poi separatamente i contributi asintoticamente, per poi tracciare il diagramma.

>[!tip] Tracciamento del diagramma del modulo
>Il diagramma del modulo asintotico si traccia con i seguenti criteri. Di base per $\omega< \frac{1}{|\tau|}, \frac{1}{|T|}, \omega_{n}, \alpha_{n}$ il grafico è una semiretta di pendenza $-g \times 20 \frac{\text{dB}}{\text{dec}}$ il cui prolungamento prende valore $|\mu|_{\text{dB}}$ in $\omega=1$.
>
>In $\omega= \frac{1}{|\tau|}$ la pendenza della spezzata aumenta di $20 \frac{\text{dB}}{\text{dec}}$, in $\omega= \frac{1}{|T|}$ la pendenza della spezzata diminuisce di $20 \frac{\text{dB}}{\text{dec}}$, in $\omega=\alpha_{n}$ la pendenza della spezzata aumenta di $40 \frac{\text{dB}}{\text{dec}}$, e infine in $\omega=\omega_{n}$ la pendenza della spezzata diminuisce di $40 \frac{\text{dB}}{\text{dec}}$.

>[!tip] Tracciamento del diagramma della fase
>Come per il diagramma del modulo il tratto iniziale ha fase: $$\angle\mu=\begin{cases}
>0°\quad&\mu>0 \\
>-180°\quad&\mu<0
>\end{cases}$$
>A questo si somma il termine $-g\cdot 90°$.
>Successivamente in corrispondenza di di $\omega= \frac{1}{|\tau|}$ si somma $\text{sgn}(\tau)\cdot 90°$ o $0$ se $\tau=0$, in $\omega= \frac{1}{|T|}$ si somma $-\text{sgn}(T)\cdot 90°$ o $0$ se $T=0$, in corrispondenza di $\omega=\alpha_{n}$ si somma $180°$ se $\xi\geq0$ o $-180°$ altrimenti, infine in corrispondenza di $\omega_{n}$ si somma $-180°$ se $\xi\geq0$ o $180°$ altrimenti.

Consideriamo la funzione di trasferimento ritardo:
$$G_{D}(s)=e^{-s\tau}$$
Questo ha: $$\begin{align*}
|G_{D}(j\omega)|&= 1\\
\angle G_{D}(j\omega)&= -\omega\tau
\end{align*}$$
Che è difficilmente rappresentabile sul diagramma di Bode.

### Sistemi a fase minima
>[!note]
>Consideriamo una funzione di trasferimento $G(s)$. Questa si dice a fase minima se $\mu>0$, i ritardi sono assenti, $\tau,T>0$ e $\xi,\zeta\geq0$.
>
>Se un sistema è a fase minima il diagramma asintotico della fase può essere ricavato da quello del modulo.

![[Pasted image 20260422172514.png]]

