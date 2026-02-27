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


## Etapas do processamento de texto
### 1️⃣ Tokenização
- O texto é dividido em unidades menores chamadas tokens (palavras, partes de palavras ou caracteres)  
    - Cada token é convertido em um ID numérico que o modelo consegue processar  
    - Exemplo: "Olá, como você está?" → [243, 567, 8910, ...]
    - Mais informações [aqui](/teoria/tokenização.md#tokenização).
### 2️⃣ Embedding
- Os tokens são transformados em vetores numéricos (embeddings)  
    - Esses vetores capturam significados semânticos e relações entre palavras  
        - Usa como base o [teorema de Manifold](/teoria/tensores.md#teorema-de-manifold) que permite usar as dimensões para reduzir o tamanho total.
    - Tokens semelhantes ficam mais próximos no espaço vetorial
        - O processo pode ser visto com detalhes [aqui](/teoria/tensores.md#entendendo-tensores)    
### 3️⃣ Processamento pelo Transformer
- O modelo aplica múltiplas camadas de atenção para entender o contexto
    - A arquitetura Transformer analisa relações entre todas as palavras da frase simultaneamente
    - O mecanismo de autoatenção identifica quais palavras são mais relevantes para cada parte do texto
### 4️⃣ Compreensão Contextual
- O modelo refina iterativamente sua representação do texto
    - Cada camada adiciona mais contexto e nuances à compreensão
    - Informações sobre sintaxe, semântica e intenção são extraídas
### 5️⃣ Geração Autoregressiva
- O modelo começa a gerar a resposta token por token
    - Para cada novo token, considera todo o contexto anterior (sua pergunta + o que já gerou)
    - Usa probabilidades para escolher o próximo token mais adequado
### 6️⃣ Decodificação
- Estratégias como amostragem ou beam search são usadas para selecionar tokens
    - Parâmetros como temperatura controlam a criatividade vs. determinismo
    - O modelo pode reavaliar escolhas anteriores durante a geração
### 7️⃣ Pós-processamento
- Os tokens gerados são convertidos de volta para texto legível
    - Pequenos ajustes podem ser aplicados (formatação, remoção de tokens especiais)

### 8️⃣ Entrega da Resposta
- O texto final é apresentado a você de forma organizada e coerente