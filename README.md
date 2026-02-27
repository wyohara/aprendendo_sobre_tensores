# Aprendendo sobre Tensores 🧠📊

Bem-vindo ao repositório **Aprendendo sobre Tensores**! Este projeto tem como objetivo desmistificar o funcionamento de redes neurais profundas através do estudo e manipulação de tensores, a estrutura de dados fundamental para o deep learning.

O conteúdo didático está organizado em tópicos progressivos, cada um com seu próprio arquivo, facilitando o aprendizado passo a passo.

## 📚 Sobre o Projeto

Aqui você encontrará explicações claras e exemplos práticos sobre:

- O que são tensores e por que eles são essenciais em redes neurais
- Operações básicas e avançadas com tensores
- Construção de camadas de redes neurais usando tensores
- Implementação de um modelo simples do zero (sem frameworks de alto nível)

Todo o código é escrito em **Python**, utilizando bibliotecas de código aberto, e é mantido de forma aberta para que qualquer pessoa possa estudar, modificar e reutilizar.


# Entendendo tensores
Quando pensando em números podemos organizar em dimensões:  
1. ***Escalar:*** é um número por si só.  
    - Ex.: $25$;  
2. ***Vetor***: é uma lista de números.  
    - Ex: $[5, 3, 6, 35]$  
    - Vetores possuem apenas 1 dimensão  
3. ***Matriz***: é uma tabela de números com duas coordenadas, a *linha* e a *coluna*.  
    - Ex: $[[3, 5], [8, 12]]$
    - Matrizes possuem apenas 2 dimensões  
4. ***Tensores***: é uma generalização com 3 ou mais dimensões.  


## Por qual motivo usamos tensores?
Computadores operam com números, não com palavras. Por isso, antes de pensar em trabalhar com um modelo de linguagem com um texto, nós precisamos converter palavras em representações numéricas. Mas não podemos converter diretamente cada palavra para um número - isso resultaria em um vetor gigantesco e esparso.  
Para contornar essa limitação, vamos fazer uma representação compacta focada em manter as relações entre as palavras do texto.  Isso só é possível usando o [Teorema de Manifold](#teorema-de-manifold), que traz a ideia de que dados extensos podem ser compactados a medida que reduzimos as dimensões.  

Vamos pensar nas palavras gato, cachorro, leão, carro e caneta em um tensor de 3 dimensões:
```
gato: (1, 0, 0.3) # animal, pequeno, pouco perigoso    
cachorro: (1, 0.4, 0.4) # animal, médio, médio perigoso
leão: (1, 1, 1) #animal, grande, perigoso
carro: (0, 1, 0.2) # não animal, grande, pouco perigoso    
caneta: (0, 0, 0) # não animal, pequeno, inofensivo
```
Perceba que:    
- Palavras com significado próximo (como gato e cachorro) têm vetores parecidos.
- Palavras distintas (caneta e leão) ficam distantes nesse espaço tridimensional.  

Na prática a criação dessas relações não é feita manualmente, mas sim computacionalmente por treinamento (embeding). Quanto a semelhança, computacionalmente e matematicamente poderiamos calcular a semelhança usando álgebra linear, principalmente pela ***regra dos cossenos***.  

### Teorema de Manifold
> "Pense em uma folha de papel A4, ela esticada irá ocupar apenas duas dimensões, o comprimento(eixo X) e a largura (eixo Y) e uma altura quase desprezível (eixo Z). Agora se amassarmos a folha de papel em uma bola ela irá ter um comprimento  e larguras menores, porém irá ter uma nova dimensão importante, a <ins>*altura*</ins>."  

Tendo essa premissa em mente se criarmos novas dimensões de análise podemos reduzir o tamanho de um texto para um tamanho muito menor, e essas novas dimensões irão guardar apenas as relações entre as palavras do texto original. 
#### Aplicação do teorema de manifold
- Um exemplo de aplicação do teorema de manifold é o RGB.  
    - O RGB pode ser visto como um tensor de 3 dimensões, cada dimensão representando uma cor: Vermelho, Verde e Azul.  
    - Cada cor a partir do RGB pode ser definida com uma quantidade de vermelho, verde e azul assim usando apenas 3bytes, um para cada posição do Tensor.  
    - Parece pouco mas como cada cor vai de 0 a 255 teremos cerca de 16,7 milhões de cores:
    $$ 256 \cdot 256 \cdot 256 \approx 16,7 M$$

#### Manifold aplicado no texto
- O vocabulário português tem cerca de 380000 palvras e para analisar um texto de 30000 palavras (cerca de 100 páginas):
    - Para analisar a relação das palavras vamos criar uma lista $V$ com 380000 posições. 
        - Nessa lista todos os valores são 0 e somente a posição da palavra terá um número que representa a sua relação com as palavras em volta:
        $$4bytes \cdot 380000 \approx 1,5 MB$$
        - Como o texto tem 30000 palavras cada linha será a posição da palava no texto. Ex: primeira palavra na linha um, segunda palavra na linha 2 e assim segue...
        - E cada coluna será o valor da palavra na lista $V$. Assim geramos uma matriz de 30000 linhas e 380000 colunas
        - O tamanho dessa nova matriz será:
        $$1,5MB \cdot 30000 = 45,6GB$$
        - Assim a matriz de entrada terá 45,6 Gb de tamanho!. É imenso!
- Agora no mesmo se usarmos um tensor de 500 dimensões  
    - um tensor $T$ de 500 dimensões com 4 bytes em cada posição:
    $$500*4 = 2Kb$$
    - como temos 38000 palavras no vocabulário iremos ter 380000 tensores $T$:
    $$2Kb \cdot 380000 = 760 Mb$$
    - Assim a matriz de vocabulário terá 760 Mb para todas as palavras!
    - se quisermos analisar o texto de 30000 palavras basta pegar o tensor T que corresponde a palavra:
    $$ 2Kb \cdot 30000=60Mb$$
    - Assim, para representar o mesmo texto precisaremos de apenas $60Mb$. ***Uma redução de quase 760 vezes!***
