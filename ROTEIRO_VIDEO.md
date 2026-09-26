# Roteiro do vídeo — Pesquisa em IA e adoção corporativa

**Disciplina:** Análise e Visualização de Dados em Python  
**Duração planejada:** aproximadamente 11 minutos e 15 segundos  
**Limite do trabalho:** 12 minutos  
**Integrantes:**

- Integrante 1: **[NOME]**
- Integrante 2: **[NOME]**
- Integrante 3: **[NOME]**

**Material apresentado:** [`Projeto_Aplicado_AI_Index.ipynb`](Projeto_Aplicado_AI_Index.ipynb)

## Distribuição do tempo

| Tempo | Responsável | Conteúdo |
|---|---|---|
| 00:00–03:30 | Integrante 1 | Apresentação, contexto, dados e pergunta analítica |
| 03:30–07:15 | Integrante 2 | Qualidade, preparação e análise exploratória |
| 07:15–11:15 | Integrante 3 | Correlação, codificação, conclusões e limitações |
| 11:15–12:00 | Margem | Transições, pausas ou pequenos imprevistos |

---

## 1. Integrante 1 — Contexto, problema e dados

### 00:00–00:30 — Abertura

**Exibir:** título do notebook.

> Olá. Neste projeto, investigamos a relação entre a evolução da pesquisa em inteligência artificial e a adoção de IA no ambiente corporativo. Utilizamos dados públicos do *AI Index Report 2026*, produzido pelo Stanford Institute for Human-Centered Artificial Intelligence.
>
> O trabalho foi desenvolvido em Python, principalmente com as bibliotecas Pandas, NumPy, Matplotlib e Scikit-Learn.

### 00:30–01:20 — Contexto e relevância

**Exibir:** seção “Contexto e métodos”.

> O AI Index reúne indicadores sobre pesquisa, desenvolvimento tecnológico, economia, educação, governança e outros aspectos da inteligência artificial.
>
> Nosso recorte relaciona dois fenômenos. O primeiro é a produção mundial de publicações de IA em Ciência da Computação. O segundo é a proporção de organizações que afirma utilizar IA em pelo menos uma função de negócio.
>
> Consideramos essa análise relevante porque a produção científica contribui para o desenvolvimento de conhecimentos e técnicas, enquanto a adoção corporativa representa a aplicação dessas tecnologias pelas organizações. Entretanto, os dados utilizados são agregados e não permitem afirmar que um fenômeno causa diretamente o outro.

### 01:20–02:00 — Pergunta analítica

**Exibir:** pergunta central e pressupostos-chave.

> Nossa pergunta analítica central é: “Como evoluíram as publicações mundiais de IA em Ciência da Computação e a proporção de organizações que usam IA, e que associação exploratória aparece nos anos coincidentes de 2017 a 2024?”
>
> A hipótese inicial era que as duas séries poderiam crescer conjuntamente à medida que a IA se desenvolvesse e se difundisse. Porém, duas variáveis que crescem ao longo do tempo podem apresentar correlação elevada apenas por compartilharem uma tendência temporal. Por isso, analisamos tanto os níveis anuais quanto as variações de um ano para o seguinte.

### 02:00–02:50 — Origem e escopo dos dados

**Exibir:** tabela “Arquivos escolhidos”.

> Utilizamos três arquivos. A figura 1.6.1 contém o volume mundial e a participação das publicações de IA entre 2013 e 2024. A figura 1.6.9 contém a composição das publicações por setor e região em 2024. Por fim, a figura 4.3.1 apresenta o uso organizacional de IA entre 2017 e 2025 e o uso de IA generativa entre 2023 e 2025.
>
> Os dados de publicações têm origem no OpenAlex. O relatório considera publicações em inglês classificadas como relacionadas à IA pelo CSO Classifier. Já os dados de adoção vêm das pesquisas anuais *State of AI*, da McKinsey & Company, e são autorrelatados pelos participantes.

### 02:50–03:30 — Unidade de análise e transição

**Exibir:** tabela com dimensões dos conjuntos.

> A unidade utilizada na correlação é o ano. Portanto, não estamos relacionando empresas individuais com artigos específicos. Estamos comparando duas séries globais produzidas por fontes e populações diferentes.
>
> A série de publicações possui dados até 2024, enquanto a adoção corporativa chega a 2025. Para não estimar ou inventar o valor de publicações de 2025, a análise conjunta utiliza somente o intervalo comum de 2017 a 2024, totalizando oito observações.
>
> A seguir, vamos apresentar a avaliação da qualidade e a preparação desses dados.

---

## 2. Integrante 2 — Qualidade, preparação e exploração

### 03:30–04:25 — Auditoria de qualidade

**Exibir:** tabelas de valores ausentes e duplicidades.

> Inicialmente, avaliamos tipos de dados, valores ausentes, cardinalidade e registros duplicados. Os três arquivos selecionados não possuem valores ausentes nem duplicatas exatas.
>
> Mesmo assim, encontramos repetições na coluna de ano. Elas não representam registros duplicados. No arquivo de publicações, cada ano aparece duas vezes porque estão armazenadas duas métricas: o número de publicações em milhares e a participação das publicações de IA no total de Ciência da Computação. No arquivo de adoção, alguns anos aparecem nas séries de IA geral e de IA generativa. Por isso, a chave correta é a combinação de ano e rótulo.

### 04:25–05:15 — Transformações realizadas

**Exibir:** reconstrução da série de publicações.

> O principal problema estrutural estava na figura 1.6.1. A mesma coluna numérica armazenava contagens e proporções. Para separar as métricas, classificamos valores maiores que 1 como número de publicações em milhares e valores entre 0 e 1 como participação.
>
> Antes de reorganizar a tabela, validamos que cada ano possuía exatamente um valor de cada tipo. Depois, aplicamos uma operação de *pivot*, produzindo uma linha por ano e uma coluna para cada métrica.
>
> Nas demais bases, convertemos anos e medidas para tipos numéricos, verificamos se todas as proporções estavam entre zero e um e confirmamos que as participações setoriais somavam 100% em cada região. Não foi necessário imputar valores nem remover registros.

### 05:15–05:55 — Outliers

**Exibir:** gráfico de inspeção de valores extremos pelo IQR.

> Também investigamos possíveis outliers com o critério do intervalo interquartil, conhecido como IQR. Esse método sinalizou os anos de 2017, 2024 e 2025 na série de adoção.
>
> Esses valores não foram removidos, porque correspondem ao início e ao final de uma tendência plausível de crescimento. Em uma série temporal, um valor extremo pode representar uma mudança real e não um erro de medição. Assim, usamos a sinalização apenas como diagnóstico.

### 05:55–06:45 — Evolução temporal

**Exibir:** gráfico “Pesquisa em IA e adoção organizacional: evolução temporal”.

> Na análise exploratória, observamos que as publicações mundiais de IA cresceram de aproximadamente 102 mil em 2013 para quase 258 mil em 2024. Houve crescimento na maior parte do período, com um pequeno recuo em 2022.
>
> A adoção organizacional de IA passou de 20% dos respondentes em 2017 para 88% em 2025. Entretanto, essa evolução não foi contínua: ocorreram recuos em 2020 e 2022. A adoção de IA generativa, disponível apenas a partir de 2023, passou de 33% para 79% em 2025.

### 06:45–07:15 — Resultado do período comum

**Exibir:** tabela dos anos alinhados ou manter o gráfico temporal.

> Considerando somente o período comum de 2017 a 2024, as publicações passaram de 116,9 mil para 257,9 mil, um crescimento de 120,5%. No mesmo intervalo, o uso organizacional de IA passou de 20% para 78%, um aumento de 58 pontos percentuais.
>
> Esses resultados indicam crescimento geral das duas séries. Na próxima parte, verificamos se seus movimentos anuais também foram semelhantes.

---

## 3. Integrante 3 — Associação, codificação e conclusões

### 07:15–08:05 — Dispersão e correlação dos níveis

**Exibir:** gráfico de dispersão com os anos identificados.

> O gráfico de dispersão relaciona o volume de publicações e a adoção corporativa em cada ano coincidente. Visualmente, os pontos apresentam uma tendência positiva: anos com mais publicações geralmente também apresentaram maior adoção.
>
> A correlação de Pearson entre os níveis anuais foi 0,81, enquanto a correlação de Spearman foi aproximadamente 0,73. Esses resultados representam uma associação positiva relativamente alta. Contudo, a amostra possui somente oito observações e as duas variáveis apresentam tendência temporal.

### 08:05–08:55 — Variações anuais

**Exibir:** gráfico “As variações anuais não se movem de forma fortemente sincronizada”.

> Para reduzir o efeito da tendência comum, calculamos a primeira diferença, ou seja, quanto cada indicador mudou em relação ao ano anterior.
>
> A correlação de Pearson entre essas variações foi somente 0,28. Isso mostra que anos com aumentos maiores na produção científica não apresentaram, de forma consistente, aumentos maiores na adoção corporativa.
>
> Portanto, a correlação elevada nos níveis parece ser parcialmente explicada pelo fato de as duas séries crescerem ao longo do tempo. O resultado não comprova que o aumento das publicações tenha causado a adoção pelas empresas.

### 08:55–09:35 — Composição setorial da pesquisa

**Exibir:** gráfico de publicações por setor e região.

> Como análise complementar, examinamos quem produz as publicações de IA. Em 2024, a academia representava a maior parcela nos Estados Unidos, na Europa e na China.
>
> A indústria possuía uma participação relativamente maior nos Estados Unidos, com aproximadamente 24,5%. Na China, o governo apresentava participação mais expressiva, de aproximadamente 25,1%. Esses resultados demonstram que a composição da pesquisa varia entre as regiões, mesmo com a predominância da academia.

### 09:35–10:15 — Codificação categórica

**Exibir:** seção de one-hot encoding e comparação antes/depois.

> Para demonstrar a preparação de atributos categóricos para aplicações de aprendizado de máquina, selecionamos as variáveis setor e área geográfica.
>
> As duas são nominais e não possuem uma ordem natural. Por isso, utilizamos one-hot encoding em vez de codificação ordinal. Cada categoria foi convertida em uma coluna binária, indicando sua presença ou ausência.
>
> A tabela original possuía três colunas, das quais duas eram categóricas. Depois da transformação, obtivemos oito colunas numéricas. Essa estrutura poderia ser utilizada por algoritmos de aprendizado de máquina, embora a quantidade atual de observações seja insuficiente para treinar um modelo confiável.

### 10:15–11:00 — Resposta, limitações e aplicação futura

**Exibir:** seção “Conclusões e aplicações futuras”.

> Em resposta à pergunta central, concluímos que a produção mundial de publicações de IA e a adoção corporativa cresceram de forma globalmente alinhada entre 2017 e 2024. A associação entre seus níveis foi positiva e alta, mas a associação entre suas variações anuais foi fraca.
>
> Entre as principais limitações estão o pequeno número de anos, o uso de indicadores globais agregados, a ausência de pareamento entre empresas e publicações e o caráter autorrelatado da pesquisa de adoção. Além disso, publicações medem volume, mas não necessariamente qualidade, impacto ou transferência de tecnologia.
>
> Como aplicação futura, uma base por país, setor e ano poderia ser utilizada para estimar níveis de adoção a partir de indicadores como publicações, patentes, investimento, infraestrutura e capital humano. Nesse cenário, seria importante utilizar validação temporal, treinando o modelo em anos anteriores e avaliando em anos posteriores.

### 11:00–11:15 — Encerramento

**Exibir:** título ou síntese do notebook.

> Assim, o principal resultado do projeto não é apenas a existência de uma correlação, mas a diferença entre uma tendência compartilhada e movimentos anuais efetivamente sincronizados. Obrigado.

---

## Orientações para a gravação

- Preencher os nomes dos integrantes neste roteiro e no notebook.
- Fazer um ensaio cronometrado; o objetivo é permanecer entre 10:45 e 11:30.
- Não ler tabelas inteiras. Destacar apenas os valores mencionados no roteiro.
- Aumentar o zoom do notebook para que títulos, eixos e resultados sejam legíveis no vídeo.
- Deixar todas as células executadas antes de iniciar a gravação.
- Usar transições curtas: o próximo integrante deve começar assim que o anterior terminar.
- Cada integrante deve compreender a análise completa, mesmo apresentando apenas uma parte.
- Não afirmar causalidade. Utilizar expressões como “associação”, “relação exploratória” e “os dados sugerem”.

## Respostas rápidas para possíveis perguntas

**Por que o relatório de 2026 não possui publicações de 2025?**  
O ano do relatório é o ano de publicação. Indicadores bibliométricos exigem tempo para indexação e consolidação; a série disponibilizada termina em 2024.

**Por que não usamos 2025 na correlação?**  
Porque a adoção possui 2025, mas a série de publicações não. A correlação deve utilizar observações pareadas do mesmo ano.

**Por que calcular as variações anuais?**  
Porque duas séries crescentes podem apresentar correlação alta apenas pela passagem do tempo. As primeiras diferenças ajudam a avaliar se seus ritmos anuais também se movem juntos.

**Por que não removemos os outliers?**  
Porque os valores sinalizados são plausíveis e aparecem nas extremidades de uma série com tendência. Não há evidência de que sejam erros.

**Por que usar one-hot encoding?**  
Porque setor e região são categorias nominais, sem uma ordem natural. Atribuir números ordenados criaria uma relação artificial entre elas.

**A análise comprova que mais pesquisa causa maior adoção?**  
Não. Os dados são agregados, observacionais e provenientes de fontes diferentes. Eles permitem descrever associação, mas não estabelecer causalidade.
