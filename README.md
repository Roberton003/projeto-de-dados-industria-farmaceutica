# Projeto de Dados — Indústria Farmacêutica

Discovery de arquitetura e engenharia de dados para uma indústria farmacêutica com operação contínua
(24h, múltiplas linhas de produção) e dados fragmentados entre ERP, MES, sensores/IoT, sistemas de
qualidade e manutenção.

## O que tem neste repositório

Dois documentos, além do case original:

| Arquivo | O que é |
|---|---|
| [`Case_Comunidados_Industria_Farmaceutica_COMPLETO.pdf`](./Case_Comunidados_Industria_Farmaceutica_COMPLETO.pdf) | O case original, como recebido — não deve ser editado. |
| [`entregafinalv5.md`](./entregafinalv5.md) | Nossa visão do problema e do plano de resposta, em linguagem direta, para qualquer pessoa do time entender sem contexto técnico prévio. |
| [`ConsolidadePerguntas.md`](./ConsolidadePerguntas.md) | Todas as perguntas que vamos fazer a cada área da fábrica — o motivo de cada uma e o que fazemos com a resposta. É o roteiro de investigação em si. |

## Como este projeto funciona

Antes de qualquer arquitetura, tecnologia ou protótipo, o objetivo é reduzir incerteza: entender como os
dados são gerados, quem é dono de cada informação, o que realmente precisa ser rápido e o que pode esperar,
e quais riscos (segurança, regulatórios, de qualidade) precisam ser resolvidos antes de qualquer decisão
técnica. Nenhuma ferramenta é escolhida enquanto essas respostas não existirem de verdade.

## Como contribuir e revisar

Este repositório é o espaço de trabalho colaborativo do time:

1. **Sugestões e correções** entram por Pull Request — comente inline no PR ou proponha a mudança direto no
   arquivo. Isso mantém o histórico de quem sugeriu o quê, e por quê.
2. **Nunca edite `main` diretamente.** Crie uma branch (`ajuste/nome-curto`) para qualquer alteração.
3. **Cada versão significativa vira um commit próprio** — evite reescrever histórico (`--force`) depois que
   outra pessoa já revisou.
4. Se você encontrar algo que os documentos atuais não previram (uma pergunta que falta, um risco novo),
   registre isso explicitamente no PR — é assim que o processo de investigação melhora a cada rodada.

## Licença

Uso interno do time — sem licença pública definida.

---

Roberto Nascimento — [github.com/Roberton003](https://github.com/Roberton003)
