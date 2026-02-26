# Álgebra Linear
Conteúdo básico e simplificado de álgebra linear.  
Fonte: [UFRJ](https://ic.ufrj.br/~collier/lectures/ala.pdf)

## Sumário  
1. [Introdução e conceitos Básicos](#Introdução_e_conceitos_Básicos) 
2. [Projeções Ortogonais](#Projeções_Ortogonais)



## Introdução e Conceitos Básicos
- Um **<ins>Vetor<ins>** é um segmento de reta orientado que possui as características:  
    - ***<ins>Comprimento</ins>*** - O tamanho do do vetor, geralmente chamado de <ins>módulo ou norma</ins>. denotado por $||v||$;   
        *"Se imaginar uma estrada reta infinita indo do leste ao oeste, o comprimento seria a <ins>distância percorrida</ins>"*      
    - **<ins>Direção</ins>** - a reta imaginária onde o vetor se encontra;  
        - *"Na mesma estrada reta infinita a <ins>direção é a própria estrada</ins>"*    
    - **<ins>Sentido</ins>** - o lado que o vetor segue dentro da reta imaginária;  
        - *"Na mesma estrada reta infinita o <ins>sentido é o lado que você segue</ins>. Por exemplo, uma viagem do Leste para o Oeste"*  
    - **<ins>Origem</ins>** - O ponto inicial onde <ins>consideramos a origem do vetor</ins>, simbolizado por "$O$".
        - A origem é um ponto artificial, que determinamos na álgebra linear. 
    - **<ins>Vetor unitário</ins>** - O vetor onde seu <ins>módulo igual a 1</ins>.  
        - Representa somente a <ins>*Direção*</ins> e <ins>*Sentido*</ins>. 
        - *"Podemos imaginar o Vetor unitário como uma seta que apenas <ins>indica o caminho</ins>"*
        - Seu valor é dado pelo <ins>*vetor divido pelo módulo*</ins>:  
    $$ u = \frac{v}{||{v}||} $$

    ### Calculando o vetor unitário:  
    - Imagine um vetor na posição $v=(3, 4)$ no plano:  
    - O valor de $||v||$ será:  
    $$||v||=\sqrt{(3^2+4^2)} = \sqrt{(9+16)} = \sqrt{25} = 5 $$
    - Em seguida dividimos o vetor $v$ pelo seu módulo $||v||$:
    $$u=\frac{v}{||{v}||} = (\frac{3}{5},\frac{4}{5}) = (0.6, 0.8)$$
    - Confirmando que $(0.6,0.8)$ é o vetor unitário:  
    $$||u|| = \sqrt{(0.6)^2+(0.8)^2} = \sqrt{0.36+0.64} = \sqrt{1} = 1$$
    - Logo, $(0.6, 0.8)$ é o vetor unitário de $(3, 4)$


### Operações com Vetores
- <ins>**Soma de vetores**</ins> - Usa a [Regra do Paralelogramo](https://pt.wikipedia.org/wiki/Regra_do_paralelogramo): 
        $$(a+b)^2 = a^2 + b^2 + 2 \cdot a \cdot b \cdot \cos \theta$$  
<img style="background:white" src="../img/algebra_linear_1.svg" alt="regra do paralelogramo" width="300">    
- <ins>**Subtração de vetores**</ins> é dado por $a$ - $b$. Para obter $- b$ basta inverter o seu sentido.  
<img style="background:white"  src="../img/algebra_linear_2.svg" alt="subtração de vetores" width="300">  
    - *Atenção*: $a - b$ é diferente de $b - a$
    - EXEMPLO:  dado vetor $a=(2,3)$ e $b=(1,2)$, $a-b$ será:
        $$-b=-(1,2)=(-1,-2)$$
        $$a-b = (2,3) + (-1,-2) = ((2-1),(3-2))=(1,1)$$
        - Agora no caso de $b-a$ o resultado será:
        $$-a=-(2,3)=(-2,-3)$$
        $$b-a = (1,2) + (-2,-3) = ((1-2),(2-3))=(-1,-1)$$

- As operações de soma e subtração ainda podem ser simplificadascomo uma operação de multiplicação de um vetor $λ$ e o vetor $v$.  
    - A generalização para $λ$ só é válida se obedecer as seguintes regras:  
        - *$1 \cdot v = v$*; 
        - *$0 \cdot v = 0$*;
        - *$λ ∈ \mathbb{R}$*
        - *$λ(u + v) = λu + λv$*;
            - com *$λ ∈ \mathbb{R}$*
        - *$(λ + µ)u = λu + µu$*;
            - com *$µ ∈ \mathbb{R}$*
        - *$(λµ)u = λ(µu)$*;
    - Dado o os vetor $u=(2,5)$ e $v=(3,−1)$:
        - A soma será:
        $$u+v=(1 \cdot u) +(1 \cdot v)$$
        - A subtração será:
        $$u-v=(1 \cdot u) +(-1 \cdot v)$$

### Projeções Ortogonais
- Caso posicionemos um vetor $v$ em um vetor $u$, iremos obter a *projeção de $v$ em $u$.*
    - ***Projeção ortogonal*** é um componente que representa a sombra que projeta $v$ na direção de $u$.
    - O comprimento desse módulo é dado por:
     $$ Proj_{\mathbf{u}}(v) = ∥v∥ · | cos \theta|$$
    - Observações quanto ao ângulo $\theta$:
        - Caso $\cos \theta > 0$ o ângulo é agudo ($<90°$) e mesmo sentido que $u$
        - Caso $\cos \theta < 0$ o ângulo é obtuso ($>90°$) e sentido oposto a $u$
- O segmento da projeção tem tamanho *$∥v∥ · | \cos \theta|$*, onde o ângulo *$θ$* é o ângulo entre $v$ e $u$.  
    $$ Proj_{\mathbf{u}}(v) = ∥v∥ · | cos \theta|$$
     <img style="background:white" src="../img/algebra_linear_3.svg" alt="subtração de vetores" width="300">    
    
    - Observações quanto ao ângulo $\theta$:
        - Caso $\cos \theta$ seja positivo, o ângulo é agudo (menor que 90°)
        - Caso $\cos \theta$ seja negativo, o ângulo é obtuso (maior que 90°)
    - Se o vetor u for um vetor unitário *$(∥v∥ · | \cos \theta|) \cdot u$* é colinear a *$u$*.
        - <ins>*Colinear*</ins> - dois vetores quaisquer tem a mesma *<ins>direção</ins>*  
    - Se o vetor $u$ não for vetor unitário o valor da projeção será:  
    $$ Proj_{\mathbf{u}}(v) = ∥v∥ \cdot \cos θ \cdot \frac{\vec{u}}{||\vec{u}||}$$
    





        





 


    