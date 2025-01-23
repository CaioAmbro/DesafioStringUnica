# Desafio da String Única

## Desafio:
### O sistema de uma loja recebe inputs de strings únicas e inteiras de endereços. É necessário que esse endereço seja armazenado em duas colunas, endereço e número. 

### Portanto, se faz necessário escrever um código simples que processe dois níveis de entrada e retorne esses campos na saída.

### Entrada: string de endereço com os dados concatenados.
### Saída: string da rua e string do número da rua.



### Nível 1: Casos simples: Entrada e saída

- "Campo Amado 339"    ->    ("Campo Amado", "339")

- "Rua Babaçu 500"    ->    ("Rua Babaçu", "500")

- "Avenida Cambuí 804B"    ->    ("Avenida Cambuí", "804B")




### Nível 2: Casos complexos Entrada e saída
- "Rio Branco Número 23"    ->    ("Rio Branco", "23")

- "Calle Sagasta, 26"    ->    ("Calle Sagasta", "26")

- "Calle 44 No 1991"    ->    ("Calle 44", "1991")

- "100 Broadway Av"    ->    ("Broadway Av", "100")

- "Quirino do Santos 23 B"    ->    ("Quirino do Santos", "23 B")

- "4, Rue de la République"    ->    ("Rue de la République", "4")

## Minha solução: RegEx:

Para a solução do **caso simples**, um simples código de python que separa os elementos da string e evidência o último como o número do endereço ja é suficiente. Você consegue conferir nos documentos compartilhados.

Já para a solução do **caso complexo**, se fossemos utilizar a mesma lógica do código simples, a complexidade aumentaria bastante, o que torna essa opção indesejada.

Ai que entra o **RegEx** (Expressão Regular / Regular Expression), que é uma solução que trabalha com alta complexidade em cadeias de caracteres. Pode ser utilizada para diversas finalidades, como para encontrar caracteres especificos, palavras ou padrões de caracteres.

Link para entender melhor as Expressões Regulares:   [wikipedia/ExpressãoRegular](https://pt.wikipedia.org/wiki/Express%C3%A3o_regular)

Existem diversas plataformas e ferramentas que auxiliam no entendimento e na utilização dessa solução pela internet. 
Como por exemplo o site [REGEXR](https://regexr.com/ ) que trás a operação da expressão regular de forma mais visual e intuitiva.

Dentro do universo regex, existe a **biblioteca RE python**  que trabalha com operação de expressão regular, e foi a biblioteca que utilizei para resolver os casos complexos.

Link da Biblioteca RE: [python.org/re](https://docs.python.org/pt-br/3/library/re.html) 

Utilizando RE junto ao python, com uma única variável poderosa podemos criar diversas camadas de exigências e restrições dentro de uma string concatenada.

### Exemplo da variável regex que utilizei:

- variável = r'^(.*?)(?:\s+(?:No|N|n|no|NO|Num|Número|Numero|num|número|numero#)?\s*(\d+\s*[A-Za-z]?))$'

Seria dificil explicar em detalhes tudo o que ela faz, mas num resumo, é capaz de identificar o que seria o número do endereço tanto no começo como no final da string, remove qualquer tipo de palavra que não seja parte do endereço, como "número", remove caracteres indesejados, trata os espaços em branco etc. E tudo isso em uma quantidade de linhas de código consideravelmente menor do que utilizando outros métodos.

Essa variável foi criada especificamente para resolver os casos complexos do Desafio da String Única, mas as possibilidades são infinitas.
