>[!note]
>Un sistema di controllo è un sistema composto dal sistema da controllare, un controllore e le loro connessioni.
>![[Pasted image 20260422173343.png|center]]
>
>
>Ricordiamo che nei sistemi reali agiscono, oltre agli ingressi e lo stato, i disturbi.

Nell'ipotesi che sia tutto lineare, per il principio di sovrapposizione degli effetti:
![[Pasted image 20260422173724.png]]
Dove normalmente $H(s)$ è un filtro passa basso, e quindi $d(t)$ sono componenti a bassa frequenza.

I sistemi di controllo possono essere ad anello aperto oppure ad anello chiuso.

### Sistemi di controllo ad anello aperto
>[!note]
>In caso di sistema ad anello aperto, un controllore $R(s)$ a monte rispetto al sistema definisce $u(t)$ in base al riferimento $y°(t)$.
>
>![[Pasted image 20260605145736.png|center]]

Supponiamo che $d\simeq0$, si ha che: $$y(t)=R(s)G(s)y°(t)$$
Per rendere $y(t)=y°(t)$, allora è necessario che: $$R(s)= \frac{1}{G(s)}$$
Tuttavia, si hanno dei problemi, per esempio nei sistemi instabili avvengono delle cancellazioni non lecite, oppure se il modello nominale è diverso dal modello reale.

Se esiste un disturbo non misurabile, allora si possono avere dei problemi siccome questo non può essere attenuato. Se invece è misurabile o stimabile si può usare un compensatore di disturbo $C(s)$:
![[Pasted image 20260605145458.png|center|697]]

Se inoltre, $G(s)$ è strettamente propria, si può definire, con $T$ molto piccola: $$R(s)= \frac{G(s)}{1+ Ts}\implies R(S)G(s)= \frac{1}{1+ Ts}$$
Che è un filtro passa basso con banda molto alta.

### Sistemi di controllo ad anello chiuso
>[!note]
>![[Pasted image 20260605150012.png|center]]
>In generale nei sistemi di controllo ad anello chiuso, se $G(s)$ è instabile, è possibile tramite retroazione stabilizzare il sistema complessivo. In generale, possiamo dire che la funzione di uscita è data da: $$Y(t)= \underbrace{\frac{\text{F. di andata}}{1+L(s)}}_{\text{funzione di sensibilità complementare }F(s)}Y^{\circ}(t)+\underbrace{\frac{1}{1+L(s)}}_{\text{funzione di sensibilità }S(s)}d(t)$$
>Dove $L(s)$ è la funzione di anello. Notiamo che $F(s)+S(s)=1\quad\forall s$. L'obiettivo di un sistema di controllo è che: $$Y(t)\simeq Y^{\circ}(t)\quad \forall d(t)$$

Si progettano quindi $R(s)$ tale che $|F(j\omega)|\simeq 1$ nella banda di frequenze in cui $|Y^{\circ}(j\omega)|\neq0$, e $|S(j\omega)|\simeq 0$ nella banda di frequenze in cui $|D(j\omega)|\neq0$. Quindi possiamo dire che $F(s)$ deve essere un filtro bassa basso, e $S(s)$ un filtro passa alto.

>[!tip] Retroazione positiva
>Dati $P$ ed $N$, con $P$ numero di poli di $L(s)$ con $\text{Re}(s)>0$, e $N$ numero di giri del diagramma di Nyquist di $-L(s)$ attorno a $-1$, se il sistema ha retroazione positiva si ha che è asintoticamente stabile, altrimenti non lo è.
>
>$N$ è anche il numero di giri che il diagramma di Nyquist di $L(s)$ compie attorno a $+1$.
>
>![[Pasted image 20260605164412.png|center]]

>[!tip] Prodotto per guadagno
>Dati $P$ ed $N$, con $P$ numero di poli di $kL(s)$ (e quindi di $L(s)$) con $\text{Re}(s)>0$, e $N$ numero di giri del diagramma di Nyquist di $kL(s)$ attorno a $-1$, o di giri di $L(s)$ attorno a $- \frac{1}{k}$, se il sistema ha retroazione positiva si ha che è asintoticamente stabile, altrimenti non lo è.
>
>![[Pasted image 20260605164832.png|center]]

### Stabilità robusta
>[!note]
>Consideriamo due sistemi $L(s)$ reale non noto e $L^{\circ}(s)$ modello nominale di $L(s)$. La differenza tra questi due è detto errore di modello. Consideriamo per questi esempi: $$L(s)=L^{\circ}(s)\Delta(s)$$

>[!tip] Incertezza costante
>Sia $\Delta(s)=k\quad k\geq 1$, e siano per ipotesi $L^{\circ}(s)$ non abbia poli nell'origine ($P=0$), sia strettamente propria e abbia $\mu>0$.
>
>In questo caso abbiamo $N=P=0$, e pertanto la stabilità asintotica del sistema se e solo se $-1<x$, e quindi: $$- \frac{1}{k}<x\implies |x|< \frac{1}{k}\implies k < \frac{1}{|x|}= k_{m}$$
>Dove $k_{m}$ è detto margine di guadagno.
>
>Si nota che quando non ho attraversamento del semiasse reale negativo $k_{m}=\infty$

>[!tip] Incertezza con ritardo
>Sia $\Delta(s)=e^{-j\Delta\varphi}\quad \Delta\varphi\geq0$, che ha come effetto di causare un ritardo di $\Delta\varphi$, e siano per ipotesi $L^{\circ}(s)$ non abbia poli nell'origine ($P=0$), sia strettamente propria e abbia $\mu>1$. Affinché $N=P$ è necessario che ci sia un attraversamento in $\varphi_{c}=kL(j\omega_{c})\in[- \pi,0]$, dove $|L(j\omega_{c})|=1$. Per avere stabilità robusta è necessario che: $$\varphi_{c}-\Delta \varphi>- \pi\implies \Delta\varphi<\pi-|\varphi_{c}|=\varphi_{m}$$
>Dove $\varphi_{m}$ è il massimo sfasamento sopportabile.
>
>Si nota che se $\mu\in(0,1)$, si ha che $\varphi_{m}=\infty$.

### Criterio di Bode
>[!note]
>![[Pasted image 20260605172628.png|center]]
>
>Consideriamo un sistema ad anello chiuso con funzione di andata $L(s)$. Se $L(s)$ è strettamente propria, non abbia poli con parte reale strettamente positiva ($P=0$), e abbia un solo attraversamento dell'asse a $0\text{ dB}$ da parte del diagramma di Bode del modulo, allora: $$\text{Sistema di controllo as. stabile}\iff\begin{cases}
>\mu_{c}>0\\\varphi_{m}>0
>\end{cases}$$

