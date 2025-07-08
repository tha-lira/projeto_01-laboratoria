# 📊 Projeto de Análise de Dados – O Mercado

**Segmentação de Clientes e Otimização de Estratégias de Marketing – O Mercado**

## 🎯 Objetivo
Esta análise visa orientar “O Mercado” na adaptação e reconhecimento do perfil de seus clientes, otimizando estratégias de retenção e crescimento. Para isso, será aplicada a metodologia RFM (Recência, Frequência e Valor Monetário), permitindo segmentar os clientes com base em seu comportamento de compra.A segmentação permitirá: Melhor compreensão do perfil dos clientes e Identificação de oportunidades de ações mais eficientes e personalizadas

## 👥 Equipe
Projeto desenvolvido **individualmente**.

## 🛠️ Ferramentas e Tecnologias Utilizadas
- Google Sheets 
- Google Slides
- Google Docs

## 🔧 Processamento e Análises
- **Conectar/importar dados**
Para iniciar o processo de análise, foi utilizada a função **IMPORTRANGE** em conjunto com **QUERY** para importar os dados brutos diretamente das planilhas fornecidas pela Laboratória. Esses dados foram organizados em abas nomeadas como **db_clientes**, **db_transacoes** e **db_resumo_compras**.

Com o objetivo de permitir manipulações sem comprometer os dados originais, os conteúdos dessas abas foram copiados e colados como valores em novas planilhas: **clientes**, **transacoes** e **resumo_compras**. Essa estrutura modular permite a limpeza, transformação e enriquecimento de dados de forma segura, mantendo a integridade da base bruta.

- **Limpeza de dados**
Para iniciar a análise da qualidade dos dados, foi realizada uma verificação individual das colunas de cada tabela. Essa etapa teve como objetivo identificar possíveis inconsistências, como valores ausentes.

A abordagem adotada incluiu:
- Contagem do total de células preenchidas:
 Utilizou-se a função **=COUNTA()** para contabilizar o número de células não vazias em cada coluna.
- Identificação de células vazias (valores nulos):
 Em seguida, foi aplicada a função **=COUNTBLANK()** para determinar a quantidade de células sem preenchimento.

Esse processo permitiu identificar colunas com presença de dados ausentes ou inconsistências, possibilitando o registro detalhado dos valores nulos e contribuindo para a definição de estratégias de tratamento posteriores.

- **Identificar e tratar valores duplicados**
Como parte do processo de validação da integridade dos dados, foi realizada uma verificação de linhas duplicadas nas tabelas. A estratégia aplicada consistiu em:
- Criação de uma coluna auxiliar chamada **status**:
Essa coluna foi adicionada às tabelas com o objetivo de classificar cada linha como "Duplicado" ou "Único", com base na comparação dos valores de todas as colunas relevantes de cada tabela.

- **Identificar dados fora do escopo da análise**
Durante análise exploratória das planilhas **clientes**, **transacoes** e **resumo_compras** com objetivo de identificar valores que estivessem fora do padrão esperado, foram encontradas inconsistências nas colunas **ano_nascimento** e **salario_anual_dolar**, que são críticos para a segmentação e compreensão do comportamento do consumidor.
- Durante a validação da planilha clientes foi encontrada uma inconsistência na variável ano_nascimento, foram encontrados 3 registros com idade superior a 100 anos. Este valor é estatisticamente raro e pode indicar erro de digitação no campo.
- Durante a análise exploratória da variável salario_anual_dolar, foi identificado um valor atípico extremamente alto: 666.666,00, que está muito acima da média (52.247,25) e da mediana (51.381,50) da base salarial. Esse valor destoante poderia distorcer as análises estatísticas, como médias e distribuições por faixa etária e nível de educação.

- **Unir tabelas**
Criação de planilha base_tratada, com finalidade de junção de dados necessários para análise, importados das tabelas clientes, transacoes e resumo_compras. Durante o processo de unificação das bases de dados, utilizei a combinação das funções ARRAYFORMULA e VLOOKUP no Google Sheets com o objetivo de automatizar a busca de informações entre abas, e a fim de trazer colunas específicas das abas optando por importar os dados separadamente por coluna. Essa abordagem visa facilitar futuras manutenções ou atualizações no conjunto de dados garantindo escalabilidade e facilitando a manutenção da planilha.

## Lógica de Classificação dos Segmentos
Após o cálculo dos decis para cada métrica, foram atribuídos os códigos RFM no formato R_score, F_score, M_score. A seguir, os clientes foram agrupados em segmentos estratégicos a partir da combinação dessas três dimensões, com a seguinte lógica condicional:

  =IF(AND(R>=4;F>=3;M>=3);"Campeões";
  IF(AND(R>=3;F>=3;M>=2);"Clientes Fiéis";
  IF(AND(R>=3;F>=2;M>=3);"Fiéis em Potencial";
  IF(AND(R>=4;F<=2;M<=2);"Novos Clientes";
  IF(AND(R>=3;F<=2;M<=2);"Promessas";
  IF(AND(R=2;F>=3;M>=3);"Quase Inativos";
  IF(AND(R<=2;F<=2;M<=2);"Quase Dormentes";
  IF(AND(R<=2;F>=3;M>=3);"Em Risco";
  IF(AND(R<=2;F>=4;M>=4);"Não Pode Perder";
  IF(AND(R=1;F=1;M<=2);"Hibernando";
  "Perdidos"))))))))))

Essa lógica permitiu classificar os clientes em 11 grupos estratégicos de comportamento, refletindo diferentes estágios da jornada do consumidor e oferecendo base sólida para a definição de ações de retenção, reativação e fidelização.

Essa segmentação refinada garante que a empresa consiga adaptar suas estratégias de marketing, relacionamento e ofertas conforme o valor e o engajamento de cada grupo de clientes, otimizando o uso de recursos e maximizando o retorno sobre investimento.

Conclusão Geral
A combinação entre segmentação precisa e marketing personalizado permitirá aumentar a receita média por cliente e construir relações duradouras, focadas em confiança e valor percebido, potencializando o crescimento sustentável da empresa.
Limitações:

Dados Incompletos: Algumas variáveis relevantes, como salário anual, detalhes sobre a origem dos clientes, apresentaram valores ausentes ou inconsistências. Isso pode limitar a profundidade de algumas análises demográficas e comportamentais.

Recorte Temporal Restrito: A análise foi baseada em dados do período de 30/07/2020 a 31/12/2022. Portanto, não reflete alterações no comportamento dos clientes ocorridas após esse intervalo, o que pode impactar a atualidade dos insights e recomendações.
Links de interesse:

📄 Documentação Completa: https://docs.google.com/document/d/1WSEmTa1qtLzqHCw4EE9G6aqNPbTl5uvFEZx7cJpRxyE/edit?usp=sharing

📊 Spreadsheet: https://docs.google.com/spreadsheets/d/1W6B5wigxthb2hUK6FoGI3GWvKPRjbuuOvvu5cT-M08g/edit?usp=sharing




