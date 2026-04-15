>[!note]
>Sia $f(t)\in\mathbb{C}$ un segnale complesso, con $f(t)=0$ per $t<0$. Definiamo la trasformata di Laplace: $$F(s)=\mathscr{L}(f(t))=\int_{0^{-}}^{+\infty}f(t)e^{-st}\text{ d}t \qquad s\in\mathbb{C}$$

Sia la funzione scalino definita come: $$\text{sca}(t)=\begin{cases}
1\qquad& t\geq0 \\
0\qquad& t<0
\end{cases}$$
Possiamo dire che: $$F(s)=\int_{0^{-}}^{+\infty}\text{sca}(t)e^{-st}\text{ d}t= \frac{1}{s}$$
In generale per le trasformate consideriamo $\text{Re}(s)>\overline{\sigma}$, dove $\overline{\sigma}$ è detta ascissa di convergenza.

>[!tip] Proprietà
>Siano $f(t),g(t)\in\mathbb{C}$, e $\alpha,\beta\in\mathbb{C}$. Si ha che la trasformata di Laplace è lineare: $$\mathscr{L}(\alpha f(t)+ \beta g(t))= \alpha\mathscr{L}(f(t))+\beta \mathscr{L}(g(t))$$
>Sia $f(t)\in\mathbb{C}$, $\alpha\in\mathbb{C}$ e $F(s)$ la sua trasformata. Si ha che: $$\begin{align*}
>\mathscr{L}(f(t-\tau))&=  e^{-s \tau}F(s)\\
>\mathscr{L}(e^{\alpha t}f(t))&= F(s-\alpha)\\
>\mathscr{L}(\stackrel{\circ}{f}(t))&= sF(s)-f(0)\\
>\mathscr{L}\left(\int_{0}^{t} f(\tau)\text{ d}t \right)&=  \frac{1}{s}F(s)\\
>\mathscr{L}(tf(t))&=  - \frac{\partial}{\partial s}F(s)
>\end{align*}$$

>[!tip] Trasformate di segnali notevoli
>$$\begin{align*}
>\mathscr{L}(\text{sca}(t))&= \frac{1}{s}\\
>\mathscr{L}(e^{\alpha t}\cdot\text{sca}(t))&=  \frac{1}{s-\alpha}\quad \alpha\in\mathbb{C}\\
>\mathscr{L}(\cos(\omega  t)\cdot\text{sca}(t))&= \frac{s}{s^{2}+\omega^{2}}\\
>\mathscr{L}(\sin(\omega t)\cdot\text{sca}(t))&= \frac{\omega}{s^{2}+\omega^{2}}\\
>\mathscr{L}(e^{\alpha t}\cos(\omega t)\text{sca}(t))&=  \frac{s-\alpha}{(s-\alpha)^{2}+\omega^{2}}\\
>\mathscr{L}(e^{\alpha t}\sin(\omega t)\text{sca}(t))&=  \frac{\omega}{(s-\alpha)^{2}+\omega^{2}}\\
>\mathscr{L}(t\cdot\text{sca}(t))&= \frac{1}{s^{2}}
>\end{align*}$$

La trasformata di Laplace è razionale, e quindi: $$F(s)= \frac{N(s)}{D(s)}$$
Chiamiamo le radici di $N(s)$ come zeri di $F(s)$, mentre chiamiamo le radici di $D(s)$ come i poli di $F(s)$.

### Teoremi della trasformata
>[!note]
>Sia $F(s)=\mathscr{L}(f(t))$, con $F(s)$ aventi poli in $s=0$ oppure $\text{Re}(s)<0$, e con grado di $D(s)$ maggiore o uguale del grado di $N(s)$. Si ha che: $$\lim_{t\to+\infty}f(t)=\lim_{s\to0^{+}}s F(s)$$
>In caso $D(s)$ abbia grado strettamente maggiore di $N(s)$, allora si ha che: $$\lim_{t\to0^{+}}f(t)=\lim_{s\to+\infty}s F(s)$$
>Questi sono detti rispettivamente teorema della risposta finale e teorema della risposta iniziale.

### Antitrasformata
>[!note]
>Definiamo l'antitrasformata di una trasformata $F(s)$ come: $$f(t)=\mathscr{L}^{-1}(F(s))= \frac{1}{2\pi j}\int_{\sigma-j\infty}^{\sigma+j\infty}F(s)e^{st}\text{ d}s\qquad \sigma\in\mathbb{R}$$

Utilizzando il metodo dei fratti semplici è possibile evitare questa formula.

>[!tip] Metodo dei residui
>Sia $F(s)= \frac{N(s)}{(s+p_{1})\cdots(s+p_{n})}\quad p_{i}\neq p_{j}$. Sapendo che $\text{grado}(n)<\text{grado}(D)$, possiamo dire che: $$F(s)= \frac{\alpha_{1}}{s+p_{1}}+\cdots \frac{a_{n}}{s+p_{n}}$$
>Calcoliamo quindi: $$F(s)\cdot (s+p_{i})\bigg|_{s=-p_{i}}= \alpha_{i}$$

