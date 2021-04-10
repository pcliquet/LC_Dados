# Classificador Automático de Sentimento
[Prof. Maria Kelly](https://github.com/KellyVene), [Insper](https://github.com/Insper), 2021.

### Proposta do projeto
Você foi contratado por uma empresa parar analisar como os clientes estão reagindo a um determinado produto no Twitter. A empresa deseja que você: crie um programa que selecione algumas mensagens disponíveis no Twitter, as quais mencionam esse particular produto; e classifique esses tweets como "relevante" ou "irrelevante", pelo menos.

Com isso, essa empresa deseja que mensagens relevantes, que denigrem o nome do produto, ou que mereçam destaque, por exemplo, disparem um foco de atenção da área de marketing. Como aluno de Ciência dos Dados, você lembrou do Teorema de Bayes, mais especificamente do Classificador Naive-Bayes, que é largamente utilizado em filtros anti-spam de e-mails, por exemplo. Esse classificador permite calcular qual a probabilidade de uma mensagem ser relevante dada as palavras em seu conteúdo.

Para realizar o MVP (minimum viable product) do projeto, você precisa implementar uma versão do classificador que "aprende" o que é relevante com uma base de treinamento e compara a performance dos resultados com uma base de testes. Após validado, o seu protótipo poderia, porque não, também capturar e classificar automaticamente as mensagens da plataforma.


### Qualidade do classificador
![Histomgrama da qualidade do classificador](plots/qualidade.png)


### Conclusão

Nesse projeto, utilizamos o método Naive Bayes com suavização de Laplace para categorização automática de relevância de tweets, mas o modelo se mostrou rudimentar para a classificar frases que possam conter significados subjetivos. Pois a classificação dessas frases através da probabilidade de cada palavra independente, elimina qualquer relação intrínseca entre as palavras que compõem o significado diretamente condizente com a classificação esperada da frase. A partir dessas observações, é esperado que o nosso modelo não consiga classificar com acurácia a maior parte dos tweets selecionados. 

Um dos motivos se deu pelo desbalanceamento na seleção dos tweets que construíam os dicionários de palavras que usamos para treinar o nosso classificador. Esse desbalanceamento é uma diferença na quantidade de palavras nos dicionários de ocorrência entre cada categoria, consequentemente, o classificador tornou tendenciosos os resultados obtidos do modelo.

Essa tendência impossibilita usar o próprio classificador para criar novas amostras de treinamento, porque ao adicionar novas amostras é necessário que essa amostra seja classificada manualmente a fim de manter um resultado coerente com o esperado. Dessa forma, uma incoerência no resultado pode gerar uma imprecisão em novos resultados gerados pelo modelo, criando respostas mais imprecisas a cada nova classificação.

Embora este projeto não tenha uma aplicação prática confiável, o método de classificação automática pode ser muito útil em contextos menos complexos. Um  exemplo de aplicação seria, em uma barra para pesquisa de nomes, um modelo que seleciona nomes em uma lista com base em uma pesquisa e a correlação dos caracteres. Um caso teórico nesse exemplo acima seria a pessoa por “Pedra” (um nome não conhecido), a máquina iria sugerir “Pedro” (nome conhecido e semelhante).

A explicação para nosso classificador ser limitado é encontrada na definição do conceito rede neural (neural network) explicada na página do SAS (2021). Isso porque nosso classificador possui apenas uma função (ou neurônio) que ao receber uma entrada (input) determina uma saída (output).

Para melhorar esse classificador, podemos ampliar a rede de neurônios do nosso modelo. Uma rede neural é composta de funções, que chamamos de neurônios.  Um neurônio recebe uma informação e, através de uma lógica própria, gera um resultado. Neste projeto, um único neurônio recebe uma frase e retorna se ela é relevante ou não.

Quando criamos uma rede neural ela irá receber o input, ele será processado pelo primeiro neurônio, e seu resultado passará por outros neurônios, e assim, sucessivamente, até retornar um output. No nosso classificador podemos usar o neurônio que classifica relevância, outro que identifica a classe gramatical de cada palavra na frase, outro que identifica a interação entre essas palavras e por último se essa interação é positiva ou negativa. Portanto, o modelo não irá só dizer apenas a relevância de um tweet, mas ele seria capaz de dizer se é uma crítica ou um elogio.

Contudo, nós poderíamos auxiliar uma empresa desenvolvedora de um produto a identificar se seus usuários estão satisfeitos ou não, os problemas mais frequentes e onde eles recebem mais elogios. Acreditamos que o método de classificação automática de frases facilita encontrar e solucionar problemas; consequentemente, a empresa terá mais facilidade em resolvê-los e, portanto, será mais bem vista!


### Referências:

**A practical explanation of a Naive Bayes classifier**. 2017. Disponível em: https://monkeylearn.com/blog/practical-explanation-naive-bayes-classifier. Acesso em: 09 abr. 2021.

RASCHKA, Sebastian. **Naive Bayes and Text Classification I**: Introduction and Theory. 04 out. 2014. Disponível em: https://arxiv.org/pdf/1410.5329.pdf. Acesso em: 09 abr. 2021.

**Neural Networks - What are they and why do they matter? | SAS**. 2021. Disponível em: https://www.sas.com/en_us/insights/analytics/neural-networks.html. Acesso em: 09 abr. 2021.
