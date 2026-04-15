>[!note]
>Nei modelli non lineari non vale il principio di sovrapposizione degli effetti, e pertanto non sono definibili movimento libero e forzato, non si può usare l'equazione di Lagrange, e quindi la stabilità dei movimenti non è caratterizzabile allo stesso modo.
>
>È possibile usare il processo di linearizzazione per studiare questi modelli non lineari.

### Linearizzazione
>[!note]
>Consideriamo un modello non lineare generico tempo-invariante: $$\begin{cases}
>\stackrel{\circ}{x} = f(x,u) \\
>y= g(x,u)
>\end{cases}$$
>Definiamo quindi una condizione di equilibrio tramite: $$\stackrel{\circ}{x}=f(\overline{x},\overline{u})=0$$
>In caso di più equilibri scegliamo un $\overline{x}$ da studiare e quindi la coppia di equilibrio $(\overline{x},\overline{u})$. A questo punto approssimiamo $f(x,u)$ e $g(x,u)$ tramite serie di Taylor al primo ordine:
>$$\begin{align*}
>f(x,u)&\simeq f(\overline{x},\overline{u})+ \overbrace{\frac{\partial f}{\partial x}\bigg|_{(\overline{x},\overline{u})}}^{A(\overline{x},\overline{u})}(x-\overline{x})+ \overbrace{\frac{\partial f}{\partial u}\bigg|_{(\overline{x},\overline{u})}}^{B(\overline{x},\overline{u})}(u-\overline{u})\\
>g(x,u)&\simeq g(\overline{x},\overline{u})+ \underbrace{\frac{\partial g}{\partial x}\bigg|_{(\overline{x},\overline{u})}}_{C(\overline{x},\overline{u})}(x-\overline{x})+ \underbrace{\frac{\partial g}{\partial u}\bigg|_{(\overline{x},\overline{u})}}_{D(\overline{x},\overline{u})}(u-\overline{u})
>\end{align*}$$
>Definiamo quindi $\delta x=x-\overline{x}$, $\delta u=u -\overline{u}$ e $\delta y=y-\overline{y}$. E ricaviamo quindi: $$\begin{align*}
>\delta \stackrel{\circ}{x}&\simeq  A(\overline{x},\overline{u}) \delta x+ B(\overline{x},\overline{u}) \delta u\\
>\delta y&\simeq C(\overline{x},\overline{u}) \delta x + D(\overline{x},\overline{u}) \delta u
>\end{align*}$$
>Che è un modello lineare.

Tutto questo è valido finché $\delta u$ e $\delta x$ sono piccoli. Tuttavia $\delta x$ è piccolo solamente se il modello linearizzato è asintoticamente stabile.

Si ha che l'equilibrio $(\overline{x},\overline{u})$ è asintoticamente stabile se $A(\overline{x},\overline{u})$ ha autovalori con $\text{Re}(\lambda_{i})<0$. Altrimenti risulta instabile se in $A(\overline{x},\overline{u})$ $\exists \lambda_{i}\quad\text{t.c.}\quad \text{Re}(\lambda_{i})>0$.

Se $\exists \lambda_{i}\quad\text{t.c.}\quad \text{Re}(\lambda_{i})=0$ allora è impossibile stabilire se si tratta di instabilità, stabilità o stabilità asintotica con il modello linearizzato senza approfondire.

>[!tip] Equilibri asintoticamente stabili
>Gli equilibri asintoticamente stabili si dicono globali se $\forall x(\cdot)\quad x(t)\to \overline{x}$, altrimenti si dicono locali se $\forall x(\cdot)\in X\text{ limitato}\quad x(t)\to \overline{x}$.

### Metodo grafico
>[!note]
>Il metodo grafico è un metodo per approfondire lo studio della stabilità nei casi scalari ($n=1$). Per farlo si studiano gli zeri e i segni della funzione $z=f(x,\overline{u})$. Gli $0$ rappresentano gli equilibri del sistema, mentre le aree positive/negative del grafico indicano la tendenza a crescere/decrescere verso gli equilibri.
>
>Nello specifico si guardi [qui](https://andrea-bonari.github.io/analisi-matematica-2/Equazioni-differenziali/Studio-qualitativo/EDO-del-primo-ordine-autonome).

