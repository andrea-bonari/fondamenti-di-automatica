>[!note]
>Uno schema a blocchi è una rappresentazione grafica di un sistema dinamico che descrive le relazioni funzionali tra i suoi componenti, evidenziando il flusso dei segnali e le operazioni matematiche che li trasformano.
>
>![[Pasted image 20260420122129.png|center]]

Gli elementi principali degli schemi a blocchi sono:
- Blocco funzionale
- Segnale
- Nodo di somma/differenza
- Nodo di diramazione

>[!tip] Blocchi in serie
>Consideriamo due sistemi $\varphi_{1}$ e $\varphi_{2}$:
>$$\begin{align*}
>\varphi_{1}:\begin{cases}
>\stackrel{\circ}{x}_{1}=A_{1}x_{1}+B_{1}u_{1}\\
>y_{1}=C_{1}x_{1}+D_{1}u_{1}
>\end{cases}\\
>\varphi_{2}:\begin{cases}
>\stackrel{\circ}{x}_{2}=A_{2}x_{2}+B_{2}u_{2}\\
>y_{2}=C_{2}x_{2}+D_{2}u_{2}
>\end{cases}
>\end{align*}$$
>E il sistema complessivo $\varphi$ dato da:
>![[Pasted image 20260420123023.png|center]]
>Possiamo dire che la sua equazione di stato sarà data da:
>$$\varphi:\begin{cases}
>\stackrel{\circ}{x}=\begin{pmatrix}A_{1}&0\\B_{2}C_{1}&A_{2}\end{pmatrix}x&+\begin{pmatrix}B_{1}\\B_{2}D_{1}\end{pmatrix}u \\
>y=\begin{pmatrix}D_{2}C_{1}&C_{2}\end{pmatrix}x&+\begin{pmatrix}D_{2}D_{1}\end{pmatrix}u
>\end{cases}$$
>Siccome $A=\begin{pmatrix}A_{1}&0\\B_{2}C_{1}&A_{2}\end{pmatrix}$ è una matrice a blocchi triangolare ha $n=n_{1}+n_{2}$ autovalori, corrispondenti agli autovalori di $A_{1}$ e $A_{2}$.
>
>Se consideriamo invece le funzioni di trasferimento $G_{1}(s)$ e $G_{2}(s)$, possiamo dire che: $$G(s)=G_{1}(s)\cdot G_{2}(s)= \frac{N_{1}(s)N_{2}(s)}{D_{1}(s)D_{2}(s)}$$
>
>Certe volti questo prodotto porta a cancellazioni, se queste coinvolgono poli con $\text{Re}(s)\geq0$ allora la cancellazione non è lecita.

>[!tip] Blocchi in parallelo
>Consideriamo due sistemi $\varphi_{1}$ e $\varphi_{2}$:
>$$\begin{align*}
>\varphi_{1}:\begin{cases}
>\stackrel{\circ}{x}_{1}=A_{1}x_{1}+B_{1}u_{1}\\
>y_{1}=C_{1}x_{1}+D_{1}u_{1}
>\end{cases}\\
>\varphi_{2}:\begin{cases}
>\stackrel{\circ}{x}_{2}=A_{2}x_{2}+B_{2}u_{2}\\
>y_{2}=C_{2}x_{2}+D_{2}u_{2}
>\end{cases}
>\end{align*}$$
>E il sistema complessivo $\varphi$ dato da:
>![[Pasted image 20260420124349.png|center]]
>Possiamo dire che la sua equazione di stato sarà data da:
>$$\varphi:\begin{cases}
>\stackrel{\circ}{x}=\begin{pmatrix}A_{1}&0\\0&A_{2}\end{pmatrix}x&+\begin{pmatrix}B_{1}\\B_{2}\end{pmatrix}u \\
>y=\begin{pmatrix}C_{1}&C_{2}\end{pmatrix}x&+\begin{pmatrix}D_{2}+D_{1}\end{pmatrix}u
>\end{cases}$$
>Siccome $A=\begin{pmatrix}A_{1}&0\\0&A_{2}\end{pmatrix}$ è una matrice a blocchi diagonale ha $n=n_{1}+n_{2}$ autovalori, corrispondenti agli autovalori di $A_{1}$ e $A_{2}$.
>
>Se consideriamo invece le funzioni di trasferimento $G_{1}(s)$ e $G_{2}(s)$, possiamo dire che: $$G(s)=G_{1}(s)+ G_{2}(s)= \frac{N_{1}(s)D_{2}(s)+N_{2}(s)D_{1}(s)}{D_{1}(s)D_{2}(s)}$$
>Certe volti questo prodotto porta a cancellazioni, se queste coinvolgono poli con $\text{Re}(s)\geq0$ allora la cancellazione non è lecita. Le cancellazioni possono avvenire se e solo se $G_{1}(s)$ e $G_{2}(s)$ hanno poli in comune.

>[!tip] Blocchi in retroazione
>Consideriamo due sistemi $\varphi_{1}$ e $\varphi_{2}$:
>$$\begin{align*}
>\varphi_{1}:\begin{cases}
>\stackrel{\circ}{x}_{1}=A_{1}x_{1}+B_{1}u_{1}\\
>y_{1}=C_{1}x_{1}+D_{1}u_{1}
>\end{cases}\\
>\varphi_{2}:\begin{cases}
>\stackrel{\circ}{x}_{2}=A_{2}x_{2}+B_{2}u_{2}\\
>y_{2}=C_{2}x_{2}+D_{2}u_{2}
>\end{cases}
>\end{align*}$$
>E il sistema complessivo $\varphi$ dato da:
>![[Pasted image 20260420125728.png|center]]
>Possiamo dire che la sua equazione di stato sarà data da:
>$$\varphi:\begin{cases}
>\stackrel{\circ}{x}=\begin{pmatrix}A_{1}-B_{1}D_{2}C_{1}&-B_{1}C_{2}\\B_{2}C_{1}&A_{2}\end{pmatrix}x&+\begin{pmatrix}B_{1}\\0\end{pmatrix}u \\
>y=\begin{pmatrix}C_{1}&0\end{pmatrix}x&+\begin{pmatrix}0\end{pmatrix}u
>\end{cases}$$
>La matrice $A$ ha $n=n_{1}+n_{2}$ autovalori, in generale diversi dagli autovalori di $A_{1}$ e $A_{2}$.
>
>Se consideriamo invece le funzioni di trasferimento $G_{1}(s)$ e $G_{2}(s)$, possiamo dire che: $$G(s)= \frac{G_{1}(s)}{1+\underbrace{G_{1}(s)G_{2}(s)}_{L(s)\text{ funzione d'anello}}}= \frac{N_{1}(s)D_{2}(s)}{N_{1}(s)N_{2}(s)+D_{1}(s)D_{2}(s)}$$
>Possono esserci cancellazioni se e solo se esistono zeri di $G_{1}(s)$ uguali a poli di $G_{2}(s)$, se queste coinvolgono poli con $\text{Re}(s)\geq0$ allora la cancellazione non è lecita.
>
>In caso la retroazione sia positiva allora la funzione di trasferimento diventa: $$G(s)= \frac{G_{1}(s)}{1-G_{1}(s)G_{2}(s)}$$