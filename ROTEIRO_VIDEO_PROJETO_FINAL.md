# Roteiro do vídeo — Investimentos e adoção corporativa de IA

**Notebook apresentado:** `projeto final.ipynb`
**Integrantes:** Alanna Chaves, Carla Nascimento e Cristina Camacho
**Duração planejada:** aproximadamente 10 minutos
**Limite do trabalho:** 12 minutos

## Pergunta do trabalho

> Em que medida o volume de investimentos em inteligência artificial é classificado e está associado ao ritmo de adoção de IA no período de 2013 a 2024?

O vídeo deve explicar que os investimentos possuem dados de 2013 a 2024, mas a adoção geral de IA começa em 2017. Portanto, a classificação utiliza 2013–2024 e a associação utiliza o período comum de 2017–2024.

## Distribuição do tempo

| Tempo | Pessoa | Parte |
|---|---|---|
| 0:00–3:10 | Alanna | Contexto, pergunta, bases e qualidade dos dados |
| 3:10–6:20 | Carla | Classificação dos investimentos e valores extremos |
| 6:20–9:40 | Cristina | Adoção, associação, conclusões e limitações |
| 9:40–10:00 | Grupo | Encerramento |

## 1. Alanna — contexto, pergunta e preparação (0:00–3:10)

### 0:00–0:25 — Abertura

**Mostrar:** título e resumo executivo do notebook.

**Fala sugerida:**

> Olá. Nós somos Alanna Chaves, Carla Nascimento e Cristina Camacho. Nosso projeto analisa como os investimentos em inteligência artificial são classificados e se o seu volume está associado ao ritmo de adoção corporativa de IA. Utilizamos dados públicos do AI Index Report 2026, publicado pelo Stanford HAI.

### 0:25–1:15 — Pergunta e recorte temporal

**Mostrar:** seção “Pergunta de pesquisa”.

**Fala sugerida:**

> Nossa pergunta é: em que medida o volume de investimentos em inteligência artificial é classificado e está associado ao ritmo de adoção de IA no período de 2013 a 2024?
>
> Foi necessário separar dois recortes. Os investimentos possuem dados de 2013 a 2024, mas a série de adoção geral de IA começa em 2017. Por isso, usamos todo o período para classificar os investimentos e os oito anos de 2017 a 2024 para calcular a associação.

### 1:15–2:05 — Fontes e estrutura

**Mostrar:** tabela dos arquivos e saída da estrutura das bases.

**Fala sugerida:**

> Utilizamos dois arquivos do capítulo de Economia. O primeiro apresenta quatro classificações de investimento corporativo em IA e tem como fonte a Quid. O segundo apresenta a proporção de organizações que usam IA em pelo menos uma função e tem como fonte a pesquisa da McKinsey.
>
> Depois do filtro, a base de investimentos possui 48 linhas, correspondentes a quatro categorias em cada um dos doze anos. A base de adoção possui oito observações anuais.

### 2:05–2:55 — Qualidade e transformações

**Mostrar:** tabela de qualidade e célula de padronização.

**Fala sugerida:**

> Verificamos valores ausentes, linhas duplicadas e chaves duplicadas. Não encontramos ocorrências desses problemas. A grade de investimentos está completa. A ausência de adoção entre 2013 e 2016 não é um valor nulo: são anos não medidos e, por isso, não foram preenchidos com zero.
>
> Traduzimos as categorias, transformamos o tipo de investimento em variável categórica e convertemos a adoção da escala entre zero e um para percentual.

### 2:55–3:10 — Transição

> Com os dados preparados, classificamos o volume investido e analisamos sua evolução. A Carla apresentará esses resultados.

## 2. Carla — classificação dos investimentos (3:10–6:20)

### 3:10–4:00 — Volume acumulado por classificação

**Mostrar:** tabela-resumo e gráfico de barras horizontais.

**Fala sugerida:**

> Entre 2013 e 2024, as quatro categorias somaram 1.619,34 bilhões de dólares. Investimento privado foi a maior classificação, com 760,23 bilhões, equivalente a 46,95% do total. Fusões e aquisições vieram em seguida, com 628,54 bilhões e 38,81%.
>
> Juntas, essas duas categorias concentraram 85,76% do volume acumulado. Participação minoritária respondeu por 7,64%, e oferta pública por 6,60%.

### 4:00–4:55 — Evolução anual

**Mostrar:** gráfico de linhas por classificação.

**Fala sugerida:**

> O gráfico de linhas mostra que o investimento privado cresceu de forma mais contínua e chegou a 151,48 bilhões de dólares em 2024. Fusões e aquisições atingiram seu maior valor em 2021 e depois diminuíram, embora continuassem relevantes.
>
> Participação minoritária apresenta um pico isolado em 2020, enquanto oferta pública alcança seu maior valor em 2021.

### 4:55–5:35 — Composição anual

**Mostrar:** gráfico de barras empilhadas.

**Fala sugerida:**

> As barras empilhadas mostram tanto o crescimento do investimento total quanto a mudança de composição. O maior total do recorte ocorreu em 2021. Em 2024, o total foi de 253,02 bilhões de dólares, com predominância do investimento privado.

### 5:35–6:05 — Valores extremos

**Mostrar:** tabela do IQR e boxplot.

**Fala sugerida:**

> Aplicamos o intervalo interquartil para identificar valores extremos. Foram sinalizados o pico de participação minoritária em 2020 e o de oferta pública em 2021. Também foram sinalizados os valores inicial e final da adoção. Esses pontos foram mantidos porque correspondem a registros válidos das fontes e fazem parte da evolução analisada.

### 6:05–6:20 — Transição

> Depois de classificar os investimentos, comparamos sua evolução com o ritmo de adoção corporativa de IA. A Cristina apresentará essa análise.

## 3. Cristina — adoção, associação e conclusões (6:20–9:40)

### 6:20–7:00 — Ritmo de adoção

**Mostrar:** gráfico “Organizações que usam IA em ao menos uma função”.

**Fala sugerida:**

> A adoção corporativa de IA passou de 20% dos respondentes em 2017 para 78% em 2024, um aumento de 58 pontos percentuais. O crescimento não foi contínuo: houve recuos em 2020 e 2022, seguidos por uma alta mais intensa em 2024.

### 7:00–7:50 — Evolução no período comum

**Mostrar:** gráfico com os dois painéis temporais.

**Fala sugerida:**

> No período comum de 2017 a 2024, o investimento corporativo total passou de 53,72 para 253,02 bilhões de dólares, crescimento de 371%. O investimento privado passou de 25,72 para 151,48 bilhões, crescimento de 489%.
>
> Os gráficos mostram que investimento e adoção apresentam tendência geral de alta, mas também possuem oscilações e não se movimentam de forma idêntica em todos os anos.

### 7:50–8:40 — Correlação

**Mostrar:** os dois gráficos de dispersão.

**Fala sugerida:**

> Calculamos a correlação de Pearson nos oito anos comuns. Entre investimento total e adoção, o resultado foi 0,56. Entre investimento privado e adoção, o resultado foi 0,76.
>
> As duas correlações são positivas, e a associação é maior para o investimento privado. Isso significa que anos com maior investimento tendem a coincidir com maior adoção. Entretanto, correlação não significa causalidade.

### 8:40–9:00 — Codificação categórica

**Mostrar brevemente:** saída da célula de *one-hot encoding*.

**Fala sugerida:**

> Para tratar a variável categórica, aplicamos one-hot encoding. Cada tipo de investimento foi transformado em uma coluna binária, sem impor uma ordem artificial entre as categorias. Essa transformação prepara a base para possíveis modelos futuros.

### 9:00–9:25 — Resposta à pergunta

**Mostrar:** seção “Conclusões”.

**Fala sugerida:**

> Respondendo à pergunta, os investimentos se distribuem em quatro categorias, com forte concentração em investimento privado e fusões e aquisições. No período de 2017 a 2024, o volume investido apresentou associação positiva com a adoção corporativa de IA. A associação foi mais elevada para o investimento privado, com correlação de 0,76.

### 9:25–9:40 — Limitações

**Mostrar:** seção “Limitações”.

**Fala sugerida:**

> As principais limitações são os oito anos comuns, as metodologias diferentes das fontes, o caráter global dos indicadores e a tendência de crescimento presente nas séries. Além disso, os valores de investimento não foram ajustados pela inflação. Por esses motivos, não afirmamos que o investimento causou o aumento da adoção.

## 4. Encerramento do grupo (9:40–10:00)

**Mostrar:** resumo executivo.

**Fala sugerida:**

> Em síntese, o trabalho identificou como os investimentos em IA estão classificados e encontrou associação positiva entre investimento e adoção corporativa no período comparável, com resultado mais forte para o investimento privado. Obrigada pela atenção.

## Checklist antes da gravação

- Executar o notebook de cima para baixo e confirmar que todas as saídas aparecem.
- Deixar visível a diferença entre o período da classificação, 2013–2024, e o período da correlação, 2017–2024.
- Não afirmar que a correlação demonstra causalidade.
- Evitar ler tabelas completas; destacar somente os valores usados na conclusão.
- Manter os gráficos no zoom necessário para que títulos e rótulos sejam legíveis.
- Cada integrante deve ensaiar sua parte para respeitar o tempo.
- Conferir áudio, nomes das integrantes e tela compartilhada.
- Manter a gravação abaixo de 12 minutos.
