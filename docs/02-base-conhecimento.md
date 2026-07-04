# Base de Conhecimento

## Dados Utilizados

Foram utilizados o conjunto de dados descritos na tabela abaixo:

| Arquivo | Formato | Utilização |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar o perfil |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Tipos de produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

O arquivo JSON perfil_investidor foi ajustado de forma ficticia para um perfil de um jovem aprendiz em início de carreira. Além disso, foi incluido um segundo perfil, também, de uma pessoa jovem em inicio de carreira.
Os dados do arquivo transacoes.csv foram ajustado com valores ficticios para dar sentido ao contexto de um jovem aprendiz. Nesse arquivo, além da atualização de dados foi incluida um coluna nome para diferenciar a transações dos dois clientes (Lucas e Mariana).

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

A disponibilidade dos dados será feita de duas formas: diretamente via prompt ou carregamento dos arquivos via código. Semelhante ao exemplo abaixo:

import json
import pandas as pd

-  Importação do Arquivo JSON (Perfis)

Carrega o arquivo JSON contendo as informações e metas dos jovens aprendizes
with open("data/perfis_aprendizes.json", "r", encoding="utf-8") as file:
    dados_perfis = json.load(file)

-  Importação do Arquivo CSV (Histórico Financeiro)

Carrega o histórico financeiro unificado usando o Pandas
df_historico = pd.read_csv("data/historico_financeiro.csv", encoding="utf-8")

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados são consultados dinamicamente e eles estão organizados conforme exemplo abaixo:
| Data | Nome | Descrição | Categoria | Valor | Tipo |
| :--- | :--- | :--- | :--- | :---: | :---: |
| 2025-10-01 | Lucas Souza | Salário Jovem Aprendiz | receita | 702.00 | entrada |
| 2025-10-01 | Mariana Costa | Salário Jovem Aprendiz | receita | 750.00 | entrada |

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: Lucas Souza
- Idade: 16 anos
- Profissão: Jovem Aprendiz (Administrativo)
- Renda Mensal: R$ 702,00
- Meta Principal: Poupar R$ 20 por mês para comprar um laptop (Meta final: R$ 2500,00)

Últimas Transações Registradas:
- 2025-10-01: Salário Jovem Aprendiz (+R$ 702,00)
- 2025-10-01: Poupança Meta Notebook (-R$ 20,00)
- 2025-10-02: Lanche na escola (-R$ 15,00)
```
