>[!note]
>L'insieme di relazioni formali che esprimono, quantitativamente e qualitativamente, come le uscite sono influenzate dagli ingressi è detto modello del sistema.

>[!example] Memoria di un computer
>Siano:
>- $m(t)$: Dati in ram.
>- $a(t)$: Dati allocati all'istante $t$.
>- $d_{m}(t)$: Dati deallocati all'istante $t$ in ram.
>- $s(t)$: Dati sul disco.
>- $d_{s}(t)$: Dati deallocati all'istante $t$ sul disco.
>- $u(t)$: Dati spostati dalla memoria fisica alla memoria ram, manipolabile.
>
>Possiamo definire l'equazione: 
>$$\begin{cases}
>m(t+1) &= m(t)+a(t)-dm(t)+u(t) \\
>s(t+1) &= s(t)-ds(t)-u(t)
>\end{cases}\qquad t\in\mathbb{N}$$
>Questa, siccome il tempo è discreto, è detta equazione alle differenze, e in forma matriciale è:
>$$\begin{pmatrix}m(t+1)\\s(t+1)\end{pmatrix}=\begin{pmatrix}1&0\\0&1\end{pmatrix}\begin{pmatrix}m(t)\\s(t)\end{pmatrix}+\begin{pmatrix}1&-1&0&1\\0&0&-1&-1\end{pmatrix}\begin{pmatrix}a(t)\\dm(t)\\ds(t)\\u(t)\end{pmatrix}$$

### Stato dei modelli
>[!note]
>Lo stato è una variabile, la cui conoscenza all'istante iniziale è necessaria per caratterizzare l'andamento delle variabili del sistema a fronte di un ingresso dato.
>
>Le variabili di stato $x_{1},\cdots, x_{n}$ sono poste nel vettore $\overrightarrow{x}$, inoltre $n$ è detto ordine del sistema.
>
>La forma dell'equazione di stato è: $$\begin{cases}
>\stackrel{\circ}{x}&=f(x(t),u(t), t)\quad&\text{se }t\in\mathbb{R} \\
>x(t+1)&=f(x(t),u(t),t)\quad&\text{se }t\in\mathbb{N}
>\end{cases}$$
>La generica funzione $f$ dipende da $t$ se esistono parametri variabili nel tempo.
>La forma dell'equazione di uscita è invece:
>$$y(t)=g(x(t),u(t),t)\qquad t\in\mathbb{R}\lor t\in\mathbb{N}$$

Definendo una condizione iniziale $x(t_{0})=x_{0}$ e $u(t)\quad\forall t$, è possibile simulare il sistema. Chiamiamo $x(t)$ movimento dello stato, e $y(t)$ movimento dell'uscita.

>[!tip] Equilibrio
>Definiamo il movimento di equilibrio, per sistemi tempo-invarianti, come segue.
>
>Dato un ingresso costante $u(t)=\overline{u}\quad\forall t$, per modelli a tempo continuo, l'equilibrio è definito come: $$\stackrel{\circ}{x}(t)=f(\overline{x},\overline{u})=0$$
>Le soluzioni di questa equazione hanno cardinalità qualsiasi (Si possono avere dalla nessuna soluzione alle infinite soluzioni).
>Per i modelli a tempo discreto invece si ha: $$\stackrel{\circ}{x}(t)=A \overline{x}+B\overline{u}=0\iff A\overline{x}=-B\overline{u}$$
>Se $\text{Rk}(A)=n$ allora $\overline{x}=A^{-1}B\overline{u}$, altrimenti se $\text{Rk}(A)<n$ allora non esiste equilibrio. In caso di equilibrio questo è verificato se: $$\overline{x}=f(\overline{x},\overline{u})$$

### Classificazione dei modelli
>[!note]
>I modelli, secondo diversi criteri, possono essere:
>- **Tempo discreto** se $t\in\mathbb{N}$, **Tempo continuo** se $t\in\mathbb{R}$.
>- **Ordine del modello**: numero di variabili di stato $n$.
>- **Strettamente proprio** se $g(x(t),u(t),t)=g(x(t),t)$, **Proprio non strettamente** altrimenti.
>- **Tempo invariante** se $f(x(t),u(t),t)=f(x(t),u(t))$ e $g(x(t),u(t),t)=g(x(t),u(t))$, **Tempo variante** altrimenti.
>- **Lineare** se $f(x(t),u(t),t)= A(t)\cdot x(t)+B(t)\cdot u(t)$ e $g(x(t),u(t),t)= C(t)\cdot x(t)+D(t)\cdot u(t)$, con $\vec{x}\in\mathbb{R}^{n}$, $\vec{u}\in\mathbb{R}^{m}$ e $y\in\mathbb{R}^{p}$, e di conseguenza $A(t)\in\mathbb{R}^{n\times n}$, $B(t)\in\mathbb{R}^{n\times m}$, $C(t)\in\mathbb{R}^{p\times n}$ e $D(t)\in\mathbb{R}^{p\times m}$, **Non lineare** altrimenti.
>- **Dinamico** se ha variabili di stato, **Statico** altrimenti.
>- **SISO** (Single Input - Single Output) se $m=p=1$, **MIMO** (Multiple Input - Multiple Output) altrimenti.

### Stabilità di un modello
>[!note]
>Definiamo il movimento in esame $x(t)$:
>$$\begin{cases}
>x(t_{0})=x_{0} \\
>u(t)\quad\forall t
>\end{cases}\Longrightarrow x(t)\quad t\in\mathbb{R}$$
>Definiamo adesso un movimento perturbato, cioè il movimento definito con: $$x(t_{0})=\stackrel{\sim}{x_{0}}\neq x_{0}$$
>![[Pasted image 20260224103521.png|center]]
>
>Formalmente diciamo che, $x(t)$ è stabile se:
>$$\begin{align*}
>\forall\varepsilon>0\quad\exists \delta>0&\quad\text{t.c.} \\
>&\forall\stackrel{\sim}{x_{0}}\neq x_{0} \quad||x_{0}-\stackrel{\sim}{x_{0}}||<\delta\ \Longrightarrow ||x(t)-\stackrel{\sim}{x}(t)||<\varepsilon\quad \forall t
>\end{align*}$$
>Altrimenti $x(t)$ è instabile.
>Inoltre diciamo che $x(t)$ è asintoticamente stabile se $x(t)$ è stabile e: $$||x(t)-\stackrel{\sim}{x}(t)||\stackrel{t\to\infty}{\to}0\qquad\forall x_{0}\in\text{Intorno di } x_{0}$$
>Se l'intorno è $\mathbb{R}^{n}$ allora si parla di stabilità asintotica globale, altrimenti si parla di stabilità asintotica locale.

