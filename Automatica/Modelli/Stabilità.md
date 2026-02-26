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

