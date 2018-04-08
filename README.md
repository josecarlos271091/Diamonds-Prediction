# Diamonds-Prediction
Prevendo o preço de diamantes:

Visão geral do projeto
Uma empresa de jóias quer dar um lance para comprar um grande conjunto de diamantes, mas não tem certeza de quanto deve ser esse lance. Neste projeto, você vai usar os resultados de um modelo preditivo para fazer uma recomendação sobre o quanto a empresa de jóias deve oferecer para os diamantes.

Detalhes do projeto
Um distribuidor de diamantes decidiu recentemente sair do mercado e colocou um conjunto de 3.000 diamantes para leilão. Vendo isso como uma grande oportunidade para expandir seu estoque, uma empresa de jóias mostrou interesse em fazer uma oferta. Para decidir quanto deve ser esse lance, você usará um grande banco de dados de preços de diamante para construir um modelo para prever o preço de um diamante com base em seus atributos. Então você usará os resultados desse modelo para fazer uma recomendação sobre quanto a empresa deve licitar.

Passo 1 – Entendendo os dados: Há dois conjuntos de dados. diamonds.csv contém os dados usados para construir o modelo de regressão. new_diamonds_new.csv contém os dados dos diamantes que a empresa gostaria de comprar. Ambos os conjuntos de dados contêm dados de quilates, cortes e clareza para cada diamante. Apenas o conjunto de dados diamonds.csv tem preços. Você vai prever os preços para o conjunto de dados new_diamonds.csv.

Carat representa o peso do diamante, e é uma variável numérica.
Cut representa a qualidade do corte do diamante, e varia entre 5 categorias: justo, bom, muito bom, ideal e premium. No projeto zero, essas categorias foram representadas por uma variável ordinal de 1 a 5. Você pode decidir usar a variável ordinal ou categórica.
Clarity representa a pureza interna do diamante, e se enquadra em 8 categorias: I1, SI2, SI1, VS2, VS1, VVS2, VVS1 e IF (em ordem de menor a maior pureza). No projeto zero, essas categorias foram representadas por uma variável ordinal, de 1 a 8. Você pode decidir usar a variável ordinal ou categórica.
Colorrepresenta a cor do diamante e é classificado como D a J, sendo D o mais incolor (e valioso) e J o mais amarelo.
Passo 2 – Construir o modelo: No projeto zero os resultados foram fornecidos, mas agora você começa a calculá-los. Algumas coisas são diferentes desta vez.

Você tem mais potenciais variáveis preditoras
Agora você sabe como usar variáveis categóricas, então não precisa confiar apenas em variáveis ordinais.
Percorra os passos que aprendeu durante o curso para construir o modelo e criar uma equação de regressão.

IMPORTANT: Ao usar o Alteryx, você não precisa criar manualmente variáveis temporárias antes de construir o modelo. Se você selecionar uma variável categórica, como corte ou clareza, o Alteryx criará automaticamente as variáveis "dummy" e fornecerá a saída de regressão correta. Apenas lembrando, o Alteryx cria a equação para você no relatório da ferramenta de Regressão Linear. A ferramenta de Regressão LInear funciona apenas quando a variável preditora é um número, algumas vezes, no momento de carregar o arquivo, o Alteryx não interpreta o campo da forma como deveria. Para resolver isso você pode utilizar a ferramenta "AutoField" entre a fase de carregar o arquivo e a fase de regressão linear.

Passo 3 – Calcule o preço previsto para o diamante: Para cada diamante, conecte os valores para cada uma das variáveis na equação. Em seguida, resolva a equação para obter o preço do diamante estimado ou previsto. Para fazer isso no Alteryx utilize a ferramenta Score.

Passo 4 – Faça uma recomendação: Agora que você tem o preço previsto para cada diamante é hora de calcular o preço do lance para todo o conjunto. Nota: O preço do diamante que o modelo prediz representa o preço de varejo final que o consumidor pagará. A empresa geralmente compra diamantes de distribuidores em 70% do preço, de modo que seu preço de oferta recomendado deve representar isso. Para fazer isso no Alteryx, utilize a ferramenta "Summarize" para somar o valor total dos preços previstos e depois utilize a ferramenta "Fórmula" para pegar apenas os 70%.