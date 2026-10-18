# Análise de Dados do Campeonato Brasileiro Série A 

## Sobre o projeto

Este projeto tem como objetivo explorar os dados do Campeonato Brasileiro Série A entre 2003 e 2024, buscando identificar padrões de desempenho, características das campanhas campeãs e relações entre indicadores esportivos.

A análise foi desenvolvida em Python, utilizando a biblioteca Pandas para manipulação dos dados e Matplotlib para visualização dos resultados.

O projeto busca transformar os dados em informações compreensíveis, por meio de perguntas analíticas, validação de dados e interpretação dos resultados.

## Objetivos

- Investigar as características estatísticas das campanhas campeãs.
- Comparar o desempenho dos campeões com o dos demais participantes.
- Analisar a associação entre indicadores esportivos e a posição final.
- Investigar a evolução do desempenho dos campeões ao longo das temporadas.
- Identificar equipes com maior frequência de títulos e presença entre os primeiros colocados.
- Investigar campanhas que se destacam em indicadores específicos.

## Base de dados

A base utilizada contém 450 registros referentes a times e temporadas, abrangendo o período de 2003 a 2024.

Cada registro representa o desempenho de um time em uma temporada, incluindo informações sobre classificação, pontos, partidas disputadas, vitórias, empates, derrotas e gols.

**Principais variáveis:**

| Variável | Descrição |
|---|---|
| `season` | Temporada do campeonato |
| `team` | Nome do time |
| `place` | Posição final na classificação |
| `points` | Pontuação registrada |
| `played` | Partidas disputadas |
| `won` | Vitórias |
| `draw` | Empates |
| `loss` | Derrotas |
| `goals` | Gols marcados |
| `goals_taken` | Gols sofridos |
| `goals_diff` | Saldo de gols |

## Ferramentas e tecnologias

- Python
- Pandas
- Matplotlib
- Jupyter Notebook

## Etapas da análise

### 1. Entendimento e qualidade dos dados

Inspeção da estrutura da base, verificação de valores ausentes e duplicidades e validação da consistência entre partidas disputadas, vitórias, empates, derrotas e pontos.

### 2. Criação de indicadores

Foram criados indicadores para comparar o desempenho dos times ao longo das temporadas do Campeonato Brasileiro Série A.

### Percentual de vitórias

Representa a proporção de partidas disputadas que terminaram em vitória.

**Como calcular:**

`Percentual de vitórias = (Vitórias ÷ Partidas disputadas) × 100`

**Exemplo:** um time que venceu 20 das 38 partidas disputadas teve um percentual de vitórias de **52,63%**.

**O que esse indicador revela?** Permite comparar o desempenho dos times independentemente do número de partidas disputadas.

### Média de gols marcados por partida

Indica quantos gols, em média, um time marcou por jogo.

**Como calcular:**

`Média de gols marcados = Gols marcados ÷ Partidas disputadas`

**Exemplo:** um time que marcou 60 gols em 38 partidas teve uma média de **1,58 gol por partida**.

**O que esse indicador revela?** Ajuda a avaliar a eficiência ofensiva das equipes.

### Média de gols sofridos por partida

Indica quantos gols, em média, um time sofreu por jogo.

**Como calcular:**

`Média de gols sofridos = Gols sofridos ÷ Partidas disputadas`

**Exemplo:** um time que sofreu 30 gols em 38 partidas teve uma média de **0,79 gol sofrido por partida**.

**O que esse indicador revela?** Permite comparar o desempenho defensivo das equipes. Em geral, quanto menor o valor, melhor o desempenho defensivo.

### Aproveitamento de pontos

Representa o percentual de pontos conquistados em relação ao máximo de pontos possíveis, considerando o sistema de três pontos por vitória.

**Como calcular:**

`Aproveitamento (%) = (Pontos conquistados ÷ (3 × Partidas disputadas)) × 100`

**Exemplo:** um time que conquistou 70 pontos em 38 partidas teve um aproveitamento de **61,40%**.

**O que esse indicador revela?** Mostra quanto do total de pontos disponíveis foi conquistado pela equipe.


### 3. Análise exploratória e comparativa

O projeto investiga as seguintes questões:

- **Perfil dos campeões:** quais são as características estatísticas das campanhas que conquistaram o título?
- **Campeões versus demais times:** quais diferenças são observadas nos indicadores de desempenho?
- **Ataque, defesa e classificação:** como os gols marcados, os gols sofridos e o saldo de gols se associam à posição final?
- **Evolução histórica:** como os indicadores dos campeões variaram entre as temporadas?
- **Consistência histórica:** quais equipes conquistaram mais títulos e apareceram com maior frequência entre os quatro primeiros colocados?
- **Campanhas excepcionais:** quais temporadas se destacam em indicadores como pontuação, percentual de vitórias e desempenho defensivo?

### 4. Técnicas utilizadas

- Estatística descritiva: média, mediana, quartis e desvio padrão.
- Filtragem e agrupamento de dados com Pandas.
- Comparação de indicadores entre grupos.
- Correlação de Spearman.
- Análise temporal.
- Identificação exploratória de valores atípicos pelo intervalo interquartil (IQR).
- Visualização de dados com gráficos.

## Principais resultados preliminares

Na comparação descritiva entre campeões e não campeões, foram observadas as seguintes médias:

| Indicador | Campeões | Não campeões |
|---|---:|---:|
| Percentual de vitórias | 59,52% | 35,59% |
| Gols marcados por partida | 1,76 | 1,25 |
| Gols sofridos por partida | 0,93 | 1,30 |

A análise preliminar também identificou:

- Flamengo de 2019 como a campanha com maior percentual de vitórias entre os campeões: 73,68%.
- São Paulo de 2007 como a campanha com menor média de gols sofridos: 0,50 por partida.
- Corinthians e Palmeiras com quatro títulos cada no período analisado.
- Palmeiras com 11 presenças entre os quatro primeiros colocados.

Esses resultados são descritivos e se referem exclusivamente ao período e aos registros analisados.

## Qualidade dos dados e limitações

Durante a validação, foram identificadas divergências entre a pontuação registrada e a pontuação calculada pela regra de três pontos por vitória e um por empate.

Essas divergências precisam ser investigadas na fonte original antes de utilizar a pontuação como base para conclusões definitivas.

Além disso, o formato da competição e a quantidade de partidas variaram ao longo do período. Por isso, indicadores por partida e percentuais são importantes para comparações históricas.

As correlações apresentadas não demonstram causalidade. A base contém dados agregados por time e temporada, o que limita investigações sobre partidas individuais e fatores específicos de cada confronto.

## Aprendizados

Este projeto permitiu praticar:

- Manipulação e exploração de dados com Pandas.
- Criação e interpretação de indicadores.
- Validação da consistência de uma base de dados.
- Análise comparativa e correlação.
- Construção de perguntas analíticas.
- Comunicação de resultados e reconhecimento de limitações.

## Conclusão do projeto

A análise dos dados do Campeonato Brasileiro Série A, no período de 2003 a 2024, permitiu identificar diferenças de desempenho entre as equipes campeãs e os demais participantes.

Os resultados preliminares indicaram que os campeões apresentaram maior percentual de vitórias, maior média de gols marcados por partida e menor média de gols sofridos. Além disso, a análise de correlação de Spearman apontou uma forte associação entre o percentual de vitórias e a posição final na classificação.

A investigação histórica também permitiu identificar campanhas de destaque, como a do Flamengo em 2019, que apresentou o maior percentual de vitórias entre os campeões da base, e a do São Paulo em 2007, que registrou a menor média de gols sofridos por partida.

Além dos resultados esportivos, o projeto reforçou a importância da validação e da qualidade dos dados. Foram identificadas divergências entre a pontuação registrada e a pontuação calculada a partir de vitórias e empates, demonstrando a necessidade de investigar inconsistências antes de utilizá-las para fundamentar conclusões definitivas.

Conclui-se, de forma preliminar, que as campanhas campeãs analisadas foram caracterizadas por indicadores superiores de desempenho ofensivo e defensivo em comparação aos demais participantes. Entretanto, os resultados descrevem associações observadas na base e não permitem estabelecer relações de causalidade.

---

Desenvolvido como parte da minha jornada de aprendizado em Análise de Dados e Ciência de Dados.