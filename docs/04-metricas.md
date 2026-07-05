# Avaliação e Métricas

## Como o Agente foi avaliado

**Testes estruturados:** Perguntas e respostas esperadas.
---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

---

## Exemplos de Cenários de Teste

Testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Trouxe informaçoes de clima
- **Resultado:** [ ] Correto  [X] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende 20 reais aplicados no rendeMuito ?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resultado:** [X] Correto  [ ] Incorreto

---

## Resultados

Conclusões:

**O que funcionou bem:**
- As consultas relacionadas a gastos, produto e informações inexistente o agente se comportou como esperado.

**O que pode melhorar:**
- Para as perguntas fora do escopo o agente não admite não conhecer e busca na internet as respostas.

---
