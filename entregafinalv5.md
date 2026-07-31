# Desafios técnicos e Cases — Nosso Plano de Resposta

Como vamos ajudar essa fábrica a enxergar seus dados de forma integrada.

Nosso plano de resposta, explicado sem jargão técnico — para toda a equipe entender o raciocínio antes de
entrarmos em qualquer detalhe de implementação.

---

## Nossa visão

**Por que ainda não estamos falando de ferramenta nenhuma**

A fábrica pediu "visão integrada, tempo real, mais eficiência" — um pedido legítimo, mas ainda vago demais
para virar projeto. Antes de escolher qualquer tecnologia, nosso trabalho é entender de verdade o que está
acontecendo: quem usa qual sistema, o que realmente precisa ser rápido e o que pode esperar, e quais
perguntas importantes ainda não foram feitas a ninguém.

Resumindo em uma frase: **um bom projeto de dados começa com perguntas certas, não com uma plataforma
escolhida às pressas.** Escolher ferramenta antes de entender o problema é como comprar uma solução para um
problema que a gente ainda não sabe qual é.

## O que já descobrimos

Por trás do pedido "queremos usar nossos dados melhor" existem quatro questões reais e separadas:

| Questão | O que significa |
|---|---|
| **Sistemas que não se falam** | Cada área (produção, qualidade, manutenção) tem seu próprio jeito de identificar as coisas — um mesmo lote pode ter "nomes" diferentes em cada sistema. Sem resolver isso, qualquer painel bonito vai misturar dados que na verdade não combinam. |
| **"Tempo real" ainda não foi definido** | Todo mundo pede "tempo real", mas ninguém disse ainda o que isso significa na prática. Às vezes "tempo real" só precisa ser "algumas vezes por hora" — construir algo instantâneo quando ninguém precisa disso custa caro à toa. |
| **Não sabemos a qualidade dos dados hoje** | Existem planilhas paralelas e controles manuais em algumas áreas — sinal de que os sistemas oficiais não dão conta sozinhos. Precisamos entender isso antes de prometer confiabilidade. |
| **Uma fronteira de segurança que ninguém tinha perguntado** | A rede que conecta os sensores de fábrica à rede corporativa pode ou não estar devidamente isolada — essa pergunta muda completamente como vamos coletar dado de sensor, e ainda não tinha sido feita. |

## Quem precisa estar na conversa

Além dos times óbvios, duas pessoas que costumam ficar de fora — e não podem, neste caso:

Produção · Planejamento · Qualidade · Manutenção · TI · Estoque/Logística · **Segurança da Informação (rede
industrial)** · **Jurídico / Proteção de Dados**

Os dois últimos normalmente entram "depois", quando já é tarde. Segurança da Informação decide se dá para
conectar sensores com segurança. Jurídico decide se um log que identifica qual operador estava no turno pode
ser guardado do jeito que está guardado hoje. As duas coisas podem mudar a arquitetura inteira — por isso
entram desde o início.

## O maior risco que encontramos

> **Não é volume de dado. Não é escolha de ferramenta.**
>
> É a possibilidade de existir, hoje, um jeito não controlado de um computador acessar tanto a rede da
> fábrica quanto a rede corporativa ao mesmo tempo. Se isso existir, qualquer coisa que a gente construir
> para captar dado de sensor herda esse risco sem que ninguém tenha decidido isso conscientemente. É a
> primeira pergunta que precisa ser respondida, antes de qualquer sensor ser conectado a qualquer coisa nova.

## Como vamos trabalhar

Nosso processo, em quatro etapas simples:

1. **Fazer as perguntas certas, para cada área** — já temos um roteiro pronto de quem entrevistar e o que
   perguntar, construído especificamente para esse tipo de fábrica, mas reaproveitável em qualquer cliente
   parecido no futuro.
2. **Confirmar com mais de uma pessoa antes de aceitar como pronto** — qualquer levantamento passa por uma
   segunda checagem independente antes de virarmos página; já aprendemos, fazendo esse mesmo case duas vezes
   de formas diferentes, que a primeira resposta quase sempre deixa passar algo importante.
3. **Só desenhar arquitetura depois de ter respostas reais** — nada de Databricks, Kafka, Fabric ou qualquer
   ferramenta antes disso. Quando o levantamento estiver completo, cada resposta já vai apontar exatamente
   qual decisão técnica ela ajuda a tomar.
4. **Aprender com cada cliente, para o próximo ficar mais rápido** — toda descoberta nova vira parte do nosso
   processo padrão; o próximo projeto, em qualquer setor, começa já sabendo o que este nos ensinou.

## Próximos passos

1. **Marcar as entrevistas reais** — seguindo o roteiro já preparado; o documento não substitui a conversa
   com o cliente, só organiza o que perguntar.
2. **Trazer Segurança e Jurídico já na primeira rodada** — são os dois pontos que mais mudam o rumo do
   projeto se a resposta vier diferente do esperado.
3. **Segurar qualquer decisão de ferramenta** — só decidimos tecnologia depois de ter respostas reais na mão,
   nunca antes.
4. **Desenhar a arquitetura com base nas respostas coletadas** — cada resposta já indica qual parte da
   arquitetura ela define; não começamos do zero nessa hora.
5. **Registrar qualquer surpresa nova** — se as entrevistas revelarem algo que não previmos, isso vira
   aprendizado para o próximo projeto também.

---

**Resumo em uma frase:** não vamos construir nada até entender de verdade o problema — e já temos o caminho
pronto para chegar lá rápido, sem pular etapa.

---

Roberto Nascimento — [github.com/Roberton003](https://github.com/Roberton003)
