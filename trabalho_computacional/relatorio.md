# Modelo SIR
 SIR (onde <span style="color:lightgreen">S - sucetiveis, I - infecciosas, R - recuperadas e N - numero total de individuos</span>) consiste em descrever um comportamenteo medio de uma populacao com uma doenca infecciosa.

 ## Processo de infeccao

 A cada encontro de um S com outro individuo este tem $\frac{I}{N}$ probabilidade de pegar a doenca. Podemos modelar esta variacao de S como:

 $$ \frac{dS}{dt} = -\beta S\frac{I}{N}$$

 onde $\beta$ eh um multiplicador qualquer. Este eh o modelo de decremento da poplacao sucetivel para a populacao infectada. Como todos que saem de S vao para I temos que:

 $$ \frac{dI}{dt} = \beta S\frac{I}{N} - \gamma I$$

onde $\gamma I$ eh o total de pessoas que saem de I a vao para R por intervalo de tempo. Isso tbm nos da a variacao de recuparados:

$$ \frac{dR}{dt} = \gamma I$$

Podemos reescrever isso tudo como o conjunto:

$$\begin{cases} \frac{dS}{dt} = -\beta S\frac{I}{N}\\
\frac{dI}{dt} = \beta S\frac{I}{N} - \gamma I\\
\frac{dR}{dt} = \gamma I
\end{cases}$$

que podemos normalizar da sequinte forma:

$$\begin{cases} \frac{dS}{dt} = -\beta \frac{S}{N}\frac{I}{N} = \beta \bold{S}\bold{I}\\
\frac{1}{N}\frac{dI}{dt} = \beta S\frac{I}{N} - \gamma I = \beta \bold{S}\bold{I} - \gamma \bold{I}\\
\frac{1}{N}\frac{dR}{dt} = \gamma \frac{I}{N}
\frac{1}{N} = \gamma \bold{I}\end{cases}$$

onde as letras em negrito indicam valores de 0 a 1.

Além disso vamos definir novas parâmetros a partir dos parâmetros β e γ originais r0 = β/γ e Tinf = γ/1 . Esse novos parâmetros tem uma interpretação mais
natural. O r 0 é conhecido como número de reprodução basal e representa o
número de pessoas que um doente iria infectar em média durante o curso de sua
doença. Esse é um número que ouvimos muito falar nos jornais. Se for menor
que 1 quer dizer que a doença “diminuindo”, já se for maior que 1 a epidemia
está se alastrando. Já o T inf representa o tempo médio que a pessoa fica infec-
ciosa, ou seja a duração média que um doente fica ativamente transmitindo a
doença. Em função desses parâmetros o modelo final fica:

$$\begin{cases}
\frac{d\bold{S}}{dt} = \frac{r_0}{T_{inf}} \bold{S}\bold{I}\\
\frac{d\bold{I}}{dt} = \frac{r_0}{T_{inf}} \bold{S}\bold{I} - \frac{1}{T_{inf}} \bold{I}\\
\frac{d\bold{R}}{dt} = \frac{1}{T_{inf}} \bold{I}
\end{cases}$$


## Modelo SEIR
Modelo utilizado onde <span style="color:lightgreen">E - expostos</span> e trata-se de um estagio intermediario entre S e I onde o virus esta incubado mas nao transmissivel.

$$\begin{cases}
\frac{d\bold{S}}{dt} = \frac{r_0}{T_{inf}} \bold{S}\bold{I}\\
\frac{d\bold{E}}{dt} = \frac{r_0}{T_{inf}} \bold{S}\bold{I} - \frac{1}{T_{inc}} \bold{E}\\
\frac{d\bold{I}}{dt} = \frac{r_0}{T_{inc}} \bold{S}\bold{I} - \frac{1}{T_{inf}} \bold{I}\\
\frac{d\bold{R}}{dt} = \frac{1}{T_{inf}} \bold{I}
\end{cases}$$

$$r_{0} = \frac{\beta}{\gamma}$$
$$T_{inc} = \frac{1}{\delta}$$
$$T_{inf} = \frac{1}{\gamma}$$

onde $T_{inc}$ eh a taxa de incubacao e as contas foram tiradas das seguintes expressoes:

$$\begin{cases}
\frac{dS}{dt} = -\beta S\frac{E}{N}\\
\frac{dE}{dt} = \beta S\frac{E}{N} - \delta E\\
\frac{dI}{dt} = \delta E\frac{I}{N} - \gamma I\\
\frac{dR}{dt} = \delta I
\end{cases}$$





