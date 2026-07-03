# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

O agente "resolve" a falta de hábito de poupador e a barreira de entrada na educação financeira para jovens de baixa renda (como jovens aprendizes).

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente atua como um mentor financeiro preventivo e motivacional, sempre que o jovem interagir, o agente envia pílulas de conhecimento simples sobre juros compostos ou opções de investimentos seguros para iniciantes.

### Público-Alvo
> Quem vai usar esse agente?

O público-alvo é composto por jovens de 14 a 24 anos que estão inseridos no mercado de trabalho como Jovens Aprendizes ou em seus primeiros empregos de nível inicial.

---

## Persona e Tom de Voz

### Nome do Agente
Poupa20

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

O agente é educativo, empático e motivador. Ele se comporta como um mentor jovem e acessível, que não usa termos técnicos complicados ("financês") e foca em celebrar pequenas conquistas.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal, acessível e acolhedor, mas com a seriedade necessária ao falar de dinheiro. Utiliza uma linguagem direta, sem jargões bancários complexos.

### Exemplos de Linguagem
- Saudação: "Fala, [Nome]! Tudo bem ? Passando para lembrar que hoje é dia de pagamento. Que tal separar aqueles R$ 20 da sua meta antes de o dinheiro sumir ? Seu futuro notebook está te esperando! 🚀"

- Confirmação: "Boa, mandou bem demais! 🎉 Já guardei aqui no seu registro. Mais R$ 20 pra conta e você tá cada vez mais perto de conquistar seu objetivo!"

- Erro/Limitação: "Ixi, não consegui entender muito bem essa parte. 😅 Mas, posso te ajudar a ver o saldo da sua meta ou te explicar como os juros fazem esses R$ 20 crescerem. O que prefere ?"

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Streamlit] |
| LLM | [GPT-4 via API] |
| Base de Conhecimento | [JSON/CSV] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [x] Só responde com base nos dados fornecidos
- [x] Respostas incluem fonte da informação
- [x] Quando não sabe, admite e redireciona
- [x] Não faz recomendações de investimento

### Limitações Declaradas
> O que o agente NÃO faz?

- Não faz recomendações de investimento
- Não inventa informações nem "alucina" dados
- Não finge ter conhecimento que não possui
- Não substitui um profissional certificado
- Não acessa dados bancarios
