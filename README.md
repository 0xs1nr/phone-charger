# Fonte de Tensao Ajustável

## Descricao

Fonte de tensao retificadora ajustável de 3V a 12V.

## Circuito no Falstad
![](assets/images/falstad.svg)
https://www.falstad.com/s.php?s=vwAQug

## Schematic
![](assets/images/schematic.png)

## Board
![](assets/images/board.png)

## Video
https://youtu.be/eRgzaxABTt8

## Tabela de Gastos

|Quantidade|Componente|Valor|
|----------|----------|-----|
|1|Protoboard BB-01 400P|R$ 23,80|
|1|Capacitor 1000uF|R$ 3,20|
|1|Potenciômetro B10k|R$ 7,00|
|1|Resistor 100Ω|R$ 0,07|
|1|Resistor 120Ω|R$ 0,07|
|1|Resistor 1kΩ|R$ 0,07|
|1|Resistor 5.5kΩ|R$ 0,07|
|1|Resistor 22kΩ|R$ 0,07|
|4|Diodo Retificador 1N4007|R$0,20|
|1|LED|R$0,50|R$0,50
|1|Diodo Zener 1N4743|R$0,50
|1|Transistor NPN|R$2,60|
Total: R$38,75

## Calculo dos componentes

### Transformador

-Fonte AC $127V_{rms}$ ($60Hz$)\
-Transformador com razão 1:7

Tensão no secundário do transformador: $127V \times 1/7 \approx 18V_{rms}$
Tensão de pico no secundário: $V_{pico} = 18V \times \sqrt{2} \approx 25.4V$

### Ponte retificadora

Queda de tensão na ponte retificadora: $\approx 1.4V$ ($0.7V$ cada diodo).

Tensão de entrada no filtro: $ 25.4V - 1.4V \approx 24V_{pico}$

### Capacitor

-Capacitor Eletrolítico de $1000\mu F$.

Cálculo do Ripple:
-Carga máxima requerida: $100mA$ \
-Retificação de onda completa (frequência de ripple de $120Hz$):

$$\Delta V = \frac{I}{f \cdot C} = \frac{0.1A}{120Hz \cdot 0.001F} \approx 0.83V_{pp}$$

Uma variação de apenas $0.83V$ na linha de $24V$ representa um ripple de menos de 4%.

### Zener

-Resistor Limitador de $1k\Omega$\
-Diodo Zener de $13V$.

Para fornecer até $12V$ na saída, o circuito precisa de uma tensão de referência um pouco maior, devido à queda ($ \approx 0.7V$) do transistor de saída. Assim, um Zener de $13V$ é a escolha ideal.

### Divisor de Tensão

-Potenciômetro de $10k\Omega$\
-Resistor de piso de $5.5k\Omega$.

O divisor é alimentado pela tensão fixa de $13V$ do Zener e define a tensão da base ($V_{base}$) do transistor.

Tensão Máxima = $13V$

Tensão de saída máxima $= 13V - V_{transistor} = 13V - 0.7V = \mathbf{12.3V}$ (Atende o requisito de $12V$).

Tensão Mínima (Potenciômetro no mínimo - $10k\Omega$ na malha superior):
A tensão lida será apenas a queda sobre o resistor de piso ($5.5k\Omega$):


$$V_{base(min)} = 13V \times \left( \frac{5.5k\Omega}{10k\Omega + 5.5k\Omega} \right) = 13 \times \frac{5.5}{15.5} \approx 4.61V$$

Tensão de saída mínima $= 4.61V - 0.7V = \mathbf{3.91V}$.
## Alunos

* Ryan Sulino Arrua - 16900070

* Lucas Vinicius da Costa - 16885265

* Luíz Filipe Sa Vioto - 16886252

* Luis Gustavo Vieira Antoniosi - 17067476

