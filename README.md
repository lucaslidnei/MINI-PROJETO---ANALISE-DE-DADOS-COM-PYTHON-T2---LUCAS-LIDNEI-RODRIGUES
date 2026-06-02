### MINI PROJETO - ANALISE DE DADOS COM PYTHON T2 - LUCAS LIDNEI RODRIGUES
**Curso:** Análise de Dados com Python [T2] | Módulo 1 - Semana 07
**Aluno:** Lucas Lidnei Rodrigues

Mini-Projeto Avaliativo da matéria de Manipulação de Dados com Python e SQL. 

## --- Objetivo

Projeto de análise exploratória de dados com aplicação de método ETL (Extract, Treatment, Load) de um dataset de varejo. O script realiza a importação e inspeção inicial dos dados até o tratamento, limpeza e geração de estatísticas descritivas, seguindo uma estrutura organizada em Sprints.

## --- Estrutura do Projeto

Mini Projeto/
|-- data/
|    -- Base_varejo_raw_.csv
|-- notebooks/
|    -- exploracao.ipynb
|-- outputs/
|    -- Base_verejo_limpa.csv
|-- README_LucasLidneiRodrigues_AnaliseComPython[T2].md
|-- README.md
|-- requeriments.txt

## SPRINTS

# --- Sprint 1 - Importação de Dados
- Leitura do arquivo CSV com `pandas`
- Identificação de colunas válidas
- Análise inicial:
  - head
  - info
  - valores nulos
- Exibição das primeiras linhas, tipos de dados, valores nulos, e total de registros


# --- Sprint 2 - Tratamento de Dados
- Realizda cópia da base raw para nova base, para não alterar os dados originais
- Remoção das colunas sem dados
- Conversão da coluna 'DATA' para o tipo 'datetime' ('dd/mm/yyyy')
- Conversão das colunas de identificadores ('CO_ID', 'CL_ID', 'PR_ID', 'CL_EC', 'CL_FHL') para inteiro
- Padronização das colunas de texto ('CL_GENERO', 'CL_SEG', 'PR_CAT', 'PR_NOME') para letras maiúsculas sem espaços extras


# --- Sprint 3 - Identificação e limpeza de nulos e duplicadas
- Identificação de valores nulos por coluna
- Contagem de linhas duplicadas
- Validação de registros com '#N/D'
- Remoção de linhas 100% duplicadas
- Substituição do termo '#N/D' para 'NAO INFORMADO'


# --- Sprint 4 - Estatísticas Descritivas
- Análise do número de filhos por cliente ('CL_FHL'), considerando apenas um registro por 'CL_ID':

Métrica | Descrição
- Média | Média de filhos por cliente
- Mediana | Mediana de filhos por cliente
- Moda | Valor(es) mais frequente(s)
- Desvio Padrão | Dispersão em torno da média
- Mínimo / Máximo | Estremos da distribuição
- Quartis (Q1, Q2, Q3) | Divisão percentilar

Inclui gráfico de distribuição do número de filhos por cliente


# --- Sprint 5 - Relatório e Documentação
- Análise da base de dados com aplicação de agrupamento de dados com groupby:

Métrica | Descrição
- Agrupamento 1 | Compras únicas realizadas por Gênero
- Agrupamento 2 | Iens comprados por Categoria de Produto
- Agrupamento 3 | Compras únicas realizadas por Segmento de Cliente
- Agrupamento 4 | Top 10 produtos mais comprados
- Agrupamento 5 | Total de compras por trimestre

- Foi realizada a extração da base de dados tratada para usos futuros

## --- Insights Finais e Sugestões

**INFORMAÇÕES OBTIDAS**
- A base possui **18.471 compras unicas** feita por **1.000 clientes unicos**;
- O Gênero Feminino realizou **9.615** representando **52%** do total de compras. O Gênero Masculino realizou **8.856** representando **48%** do total de compras;
- A categoria com maior quantidade de itens vendidos foi **ALIMENTOS** com **384.197 itens**, seguida por **HIGIENE** com **137.702 itens** e **LIMPEZA** com **128.632 itens**;
- Os segmentos de clientes que mais realizam compras são **B** com **11.843 compras** realizadas, seguido pelo **C** com **5.136 compras**;
- A maioria dos clientes (527), não possuem ou não informaram ter filhos, tendo uma mediana de **0** filhos e uma média de **1,14** filhos;
- No período analisado é possível verificar sazionalidade nas vendas, com picos entre o final do 4º trimestre e inicio do 2º trimestre.
- A base não possui coluna de valor de venda, então impossibilitando análises sobre faturamento, ticket média, etc.

**SUGESTÕES**
- Recomenda-se tratar a base categorizando os 3.650 registro que não possuiam descrição;
- Recomenda-se incluir coluna com informações sobre o preço de venda, pois enriquecerá a análise dos dados e possibilitará mais insights relevantes para o negócio;
- Com base nos dados obitidos é possível traçar estratégias de marketing para segmentação por classe, gênero, filhos e itens vendidos.
- Com base nos dados de sazionalidade das vendas, pode-se aplicar politicas de abastecimento nos períodos com maior demanda.


## --- Pré-requisitos
- Python 3.8 ou superior
- Pandas
- Matplotlib
- Seasborn


## --- Base de Dados

A base utilizada é um arquivo CSV com separador ';' e as seguintes colunas principais:

| coluna | Descrição |
| 'CO_ID' | Identificador da compra |
| 'CL_ID' | Identificador do cliente |
| 'PR_ID' | Identificador do produto |
| 'DATA' | Data da compra ('dd/mm/yyyy') |
| 'CL_GENERO' | Gênero do cliente |
| 'CL_SEG' | Segmento do cliente |
| 'CL_EC' | Estado civil (código) |
| 'CL_FHL' | Número de filhos |
|'PR_CAT' | Categoria de produto |
|'PR_NOME' | Nome do produto |