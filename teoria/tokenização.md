# Tokenização
Essa técnica surgiu a partir de uma necessidade básica: computadores não conseguem reconhecer palavras. Então para que possamos transmitir um texto para o computador compreender precisamos criar tokens numéricos, onde é possível aplicar cálculos matemáticos e inferir dados usando estatísticas ou álgebra linear.  
```
Texto = "Olá, mundo!"
Tokens = ["Olá", ",", "mundo", "!"]
Tokens = [15678, 11, 2345, 30]
```
Pontos importantes sobre a tokenização:  
- **Uma palavra** não necessáriamente vai gerar **um token**;  
- Palavras compostas ou muito grandes podem gerar mais de um token;  
- Existem tokens especiais de marcação para inferência, como a marcação de início e fim de texto, pedido do usuario, resposta do modelo entre outros.  
- O token gerado depende do contexto onde está a palavra e isso depende de muito treinamento.  
- Quando fornecemos **palavras desconhecidas** o tokenizador quebra a palavra em trechos com tokens conhecidos.  

## Técnicas de tokenização
### Tokenização por palavras (Word Based)
A forma mais intuitiva de tokenização, onde divide o texto por palavra e pontuação.  
- Não consegue lidar com palavras desconhecidas;  
- Pode ou não ignorar pontuação;  
```
"Eu amo inteligência artificial" -> ["Eu", "amo", "inteligência", "artificial", "!"]
```
### Tokenização por caracteres (Character-Based)
Divide o texto em caracteres individuais.  
- Usado apenas para gerar poucas centenas de tokens;  
- capaz de lidar com todas as palavras;  
- quanto maior o texto, mais difícil o processamento;  
```
"casa" -> ["c", "a", "s", "a"]
```
### Tokenização Morfológica  (Morphological)
Usa as regras linguísticas para dividir as palavras.
- Extremamente preciso
- Precisa de um conhecimento profundo do idioma
- Restrito a um idioma
- Difícil de generalizar para outros idiomas
```
"inesperadamente" → ["in", "esper", "ada", "mente"]
```

### Tokenização por Subpalavras (Subword Tokenization)
Busca o equilíbrio entre tokenização por palavra e por caractere. Possuem várias formas de aplicação:  
#### Character-Level Encoding 
- Converte os caracteres para unicode;  
- Começa separando caracteres individuais e vai mesclando os caracteres a medida que verifica a frequÊncia;
- Exige muito treinamento
- Consegue trabalhar com subpalavras e palavras desconhecidas
```
"baixo" (antes do treino ou palavra rara) -> ["b", "a", "i", "x", "o"]
"baixo" (após treino) -> ["baix", "o"] ou ["baixo"] se for uma palavra comum
```

#### WordPiece
Semelhante ao BPE mas usa análise estatística para gerar os tokens.  
- Usado por BERT, DistilBERT
- Usa o símbolo `##` para indicar continuação de palavra
```
"jogando" -> ["jog", "##ando"]
```
#### Byte-Level BPE
Semelhante ao Character-Level BPE, porém opera a nível de byte. 
- ***Usado pelos modelos de ML modernos: GPT, DeepSeek, LLaMA, RoBERTa***
- Palavras são separadas em bytes que a medida que ocorre o treinamento cria-se tokens mais representativos.
- Opera em cima do UTF-8 e permite trabalhar com qualquer idioma, inclusive com emoji;  
- capaz de tratar ruídos e erro de digitação.  
```
Frase: "Olá 😊"
Conversão para bytes (UTF-8):
    "O" → 0x4F (79)
    "l" → 0x6C (108)
    "á" → 0xC3 0xA1 (dois bytes: 195, 161)
    espaço → 0x20 (32)
    "😊" → 0xF0 0x9F 0x98 0x8A (quatro bytes: 240, 159, 152, 138)
Sequência de bytes: [79, 108, 195, 161, 32, 240, 159, 152, 138]
Depois do BPE: tokens como [79,108] ("Ol"), [195,161] ("á"), [240,159,152,138] ("😊"), etc.
```