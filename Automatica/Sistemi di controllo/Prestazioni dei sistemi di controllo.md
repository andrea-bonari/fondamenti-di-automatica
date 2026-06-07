>[!note]
>Consideriamo il seguente sistema di controllo:
>![[Pasted image 20260605173515.png]]
>
>Dove $e_{m}(t)$ è l'errore di controllo misurato: $$e_{m}(t)=e(t)-n(t)$$
>![[Pasted image 20260605173633.png]]
>Questo è sistema è modellizzabile come: $$\begin{pmatrix}Y(s)\\E(s)\end{pmatrix}=\begin{pmatrix}F(s)&S(s)&-F(s)\\S(s)&-S(s)&F(s)\end{pmatrix}\begin{pmatrix}Y^{\circ}(s)\\D(s)\\N(s)\end{pmatrix}$$

### Prestazioni statiche
>[!note]
>Analizziamo le prestazioni statiche sotto le ipotesi di applicabilità del criterio di Bode. Si richiede che: $$e(t)\stackrel{t\to\infty}{\to}0\quad\text{oppure}\quad||e(t)||<\varepsilon$$
>A fronte di segnali esogeni $y^{\circ}(t)$, $d(t)$ e $n(t)$ tali che:
>$$Y^{\circ}(s)= \frac{c_{1}}{s^{r_{1}}}\qquad D(s)= \frac{c_{2}}{s^{r_{2}}}\qquad N(s)= \frac{c_{3}}{s^{r_{3}}}$$
>Sappiamo che: $$E(s)=\underbrace{S(s)Y^{\circ}(s)}_{E_{1}(s)}-\underbrace{S(s)D(s)}_{E_{2}(s)}+\underbrace{F(s)N(s)}_{E_{3}(s)}$$
>Si ha per $i=1,2$ che: $$E_{i}(s)=\pm S(s) \frac{C_{i}}{s^{r_{i}}}\implies e_{i}(t)\stackrel{t\to\infty}{\to}e_{i\infty}=\lim_{s\to 0}s E_{i}(s)= C_{i}\lim_{s\to 0} \frac{s^{g-r_{i}+1}}{s^{g}+\mu_{L}}$$
>Per $r=1$ abbiamo come riferimento uno scalino: $$e_{i\infty}=\begin{cases}
>0\qquad& g_{L}>0\\ \frac{c_{i}}{1+\mu_{L}}&g_{L}=0
>\end{cases}$$
>Mentre, in generale, per $r>1$: $$e_{i\infty}=\begin{cases}
>0\qquad&g_{L}>r_{i}-1\\ \frac{c_{i}}{\mu_{L}}&g_{L}=r_{i}-1\\\infty& 0\leq g_{L}<r_{i}-1
>\end{cases}$$
>Per quanto riguarda ad $E_{3}(s)$ invece: $$e_{3}(t)\to e_{3\infty}=\begin{cases}
>1\qquad &g_{L}>0\land r_{3}=1 \\
>\frac{\mu_{L}}{1+\mu_{L}}& g_{L}=0\land r_{3}=1 \\
>\infty&r_{3}>1
>\end{cases}$$

Consideriamo $d(t)=n(t)=0$, ed analizziamo $y^{\circ}(s)=\overline{y}^{\circ}\text{sca}(t)$. Si ha che: $$y(t)\to y_{\infty}=\mu_{F}\overline{y}^{\circ}=\begin{cases}
\frac{\mu_{L}}{1+\mu_{L}}\overline{y}^{\circ}\quad &g_{L}=0\\\overline{y}^{\circ}&g_{L}>0
\end{cases}$$
### Prestazioni dinamiche
>[!note]
>Dati $d(t)=n(t)=0$, e $y^{\circ}(t)=\overline{y}^{\circ}\text{sca}(t)$, si vuole trovare li tempo di assestamento $T_\text{ass}$ e la sovraelongazione percentuale $S\%$.
>
>![[Pasted image 20260605185315.png|center]]
>
>Per farlo approssimiamo $F(s)$ ai poli dominanti. Per farlo, possiamo dire che: $$F(s)\simeq \frac{\mu_{F}}{1+\frac{s}{\omega_{C}}}\qquad\text{oppure}\qquad F(s)\simeq \frac{\mu_{F}}{1+2 \frac{\xi}{\omega_{C}}s+ \frac{s^{2}}{\omega_{C}^{2}}}$$
>Nel primo caso si ha: $$T_\text{ass}= \frac{5}{\omega_{C}}\qquad S\%=0$$
>Mentre nel secondo si ha: $$T_\text{ass}= \frac{5}{\omega_{C}\xi}\qquad S\%=100 e^{-\frac{\xi\pi}{\sqrt{1-\xi^{2}}}}\qquad T_{p}= \frac{2\pi}{\omega_{C}\sqrt{1-\xi^{2}}}$$
>In caso $\varphi_{m}< \frac{5}{12}\pi$ si ha la seconda approssimazione, in caso contrario si ha la prima. Si ha che: $$\xi= \frac{1}{2}\sqrt{2+2\cos\varphi_{c}}= \frac{1}{2}\sqrt{2(1-\cos\varphi_{m})}=\sin\left(\frac{\varphi_{m}}{2}\right)$$
>

### Attenuazione di disturbi e rumori di misura
>[!note]
>Siano note le trasformate di Fourier di $d(t)$ e $n(t)$, sappiamo che: $$$$