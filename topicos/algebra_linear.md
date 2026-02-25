# Álgebra Linear
Conteúdo básico e simplificado de álgebra linear.  
Fonte: [UFRJ](https://ic.ufrj.br/~collier/lectures/ala.pdf)

## Sumário  
1. [Introdução e conceitos Básicos](#Introdução_e_conceitos_Básicos) 
2. [Projeções Ortogonais](#Projeções_Ortogonais)



## Introdução e conceitos Básicos
1. Um <ins>**Vetor**</ins> é, essencialmente, um segmento de reta orientado e possui as características:  
    - <ins style='color:red'>**Comprimento**</ins> - O tamanho do do vetor, geralmente chamado de <span style='color:orange'>módulo ou norma</span>. denotado por "||v||";   
        - *"Se pensar em uma estrada reta infinita indo do leste ao oeste, o comprimento seria a <ins>distância percorrida</ins>"*      
    - <ins style='color:red'>**Direção**</ins> - a reta imaginária onde o vetor se encontra;  
        - *"Na mesma estrada reta infinita a <ins>direção é a própria estra</ins>"*    
    - <ins style='color:red'>**Sentido**</ins> - o lado que o vetor segue dentro da reta imaginária.  
        - *"Na mesma estrada reta infinita o <ins>sentido é o lado que você segue</ins>. Por exemplo, uma viagem do Leste para o Oeste"*  
    - <ins style='color:red'>**Origem**</ins> - O ponto inicial onde todos os vetores se originam. Simbolizado por "O".  
    - <ins style='color:red'>**Vetor unitário**</ins> ( $\vec{u}$) 
        - O vetor onde seu <span style='color:orange'>módulo ou norma é igual a 1</span>.  
        - Representa somente a <ins style='color:red'>**Direção**</ins> e <ins style='color:red'>**Sentido**</ins>. 
            - *"Seria como uma seta que apenas indica o caminho"*
        - Seu valor é dado por:  
    $$ \vec{u} = \frac{\vec{v}}{\|\vec{v}\|} $$


2. Operações com Vetores
    -   A <ins>soma de vetores</ins> usa a regra do paralelogramo  
        *"$(u+v)^2 = u^2 + v^2 + 2 \cdot u \cdot v \cdot \cos \theta$."*  

        <img style="background:white" src="../img/algebra_linear_1.svg" alt="regra do paralelogramo" width="300">    
    
    - A <ins>subtração de vetores</ins> é dado por ${\vec{v}}$ - ${\vec{u}}$. Obter - ${\vec{u}}$ basta inverter o seu sentido.  
     <img style="background:white"  src="../img/algebra_linear_2.svg" alt="subtração de vetores" width="300"> 
        - <span style='color:yellow'>**Cuidado:** ${\vec{v}}$ - ${\vec{u}}$ é diferente de ${\vec{u}}$ - ${\vec{v}}$ </span>
    - As operações acima ainda podem ser simplificadas, basta generalizar que a operação será uma <span style="color:orange">multiplicação entre um vetor λ e ${\vec{v}}$</span>.  
        - A generalização só é valida de obedecer as regras:  
            - *$1 · u = u$*; 
            - *$0 · u = 0$*;
            - *$λ ∈ R$*
            - *$λ(u + v) = λu + λv$*;
                - com *$λ ∈ R$*
            - *$(λ + µ)u = λu + µu$*;
                - com *$µ ∈ R$*
            - *$(λµ)u = λ(µu)$*;

## Projeções Ortogonais
1. Conceitos Básicos
    - Caso posicionemos um vetor ${\vec{v}}$ em cima de um vetor ${\vec{u}}$, iremos obter a projeção de ${\vec{v}}$ em ${\vec{u}}$.
    - O segmento da projeção tem tamanho *$∥v∥ · | cos θ|$*, onde o ângulo *$θ$* é o ângulo entre ${\vec{v}}$ e ${\vec{u}}$.  
    $$ Proj_{\mathbf{u}}(v) = ∥v∥ · | cos θ|$$
     <img style="background:white" src="../img/algebra_linear_3.svg" alt="subtração de vetores" width="300">    
    
    - Observações quanto ao ângulo $θ$:
        - Caso *$cos θ$* seja positivo, o ângulo é agudo (menor que 90°)
        - Caso *$cos θ$* seja negativo, o ângulo é obtuso (maior que 90°)
    - <span style="color:orange">Se o vetor u for um **vetor unitário** *$(∥v∥ · | cos θ|)·u$* é colinear a *$u$*.</span>
        - <ins>**Colinear**</ins> - dois vetores quaisquer tem a mesma *<ins>direção</ins>*  
    - <span style="color:orange">Se o vetor u **não for vetor unitário** o valor da projeção será:  
    $$ Proj_{\mathbf{u}}(v) = ∥v∥ · | cos θ| · \frac{\vec{u}}{\|\vec{u}\|}$$
    





        





 


    