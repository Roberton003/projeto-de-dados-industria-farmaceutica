# ConsolidadePerguntas — Desafios técnicos e Cases

**O que é este documento:** todas as perguntas que planejamos fazer, reunidas num lugar só, com o motivo de
cada uma e o que fazemos com a resposta. Consolidamos aqui tudo que amadurecemos ao longo de três versões do
nosso levantamento — não é uma lista nova, é a versão limpa e organizada da que já temos.

**Como ler:** cada pergunta vem em três partes — o que perguntamos, por que essa pergunta importa, e o que a
resposta muda no nosso trabalho. Se uma pergunta não tiver a terceira parte clara, é sinal de que ainda não
sabemos por que estamos perguntando — e isso também é bom de saber.

---

## Antes de tudo: o que a diretoria pediu, traduzido em pergunta

A diretoria não usou termos técnicos — usou termos de negócio. Cada um deles vira uma pergunta real que
vamos levar pra alguém que possa responder de verdade.

| O que foi dito | O que vamos perguntar | O que fazemos com a resposta |
|---|---|---|
| "Acompanhar a produção quase em tempo real" | Quando você diz tempo real, qual decisão muda com isso? Em quanto tempo essa decisão precisa ser tomada? | Define se o dado precisa chegar em segundos, minutos ou pode esperar até o próximo turno — isso muda completamente o quanto o projeto custa |
| "Comparar planejado x realizado" | Onde esses dois números vivem hoje, e por que às vezes eles não batem? | Mostra se o problema é falta de dado ou falta de um lugar único que junte os dois |
| "Identificar desvios de produção rapidamente" | O que conta como desvio hoje, e quem decide isso? | Evita construir um alerta que dispara para coisa errada, ou que nunca dispara |
| "Entender quais equipamentos causam mais interrupção" | Toda parada é anotada, ou só as grandes? | Sem isso, qualquer ranking de "equipamento problemático" pode estar simplesmente errado |
| "Prever possíveis atrasos" | O planejamento muda ao longo do dia? Isso fica registrado? | Sem histórico de mudança, não tem como comparar "o que foi planejado" com "o que realmente aconteceu" |
| "Usar Machine Learning no futuro" | Existe hoje histórico suficiente e de qualidade pra treinar algo assim? | Evita prometer inteligência artificial sobre uma base de dados que ainda não existe de forma confiável |

---

## Perguntas por pessoa — organizadas por quem vamos procurar

### Quem patrocina o projeto (Diretor Industrial)

- **Pergunta:** Qual decisão você não consegue tomar hoje por falta de dado integrado?
  **Por quê:** É a pergunta mais importante de todas — sem uma resposta concreta aqui, o projeto inteiro fica
  sem norte.
  **O que fazemos com a resposta:** Vira o primeiro critério de sucesso do projeto — se no final não
  resolvermos essa decisão específica, o projeto não cumpriu o combinado.

- **Pergunta:** Se você tivesse essa visão integrada amanhã, o que mudaria na prática — quem age, e como?
  **Por quê:** Separa "seria legal ter" de "isso realmente muda o meu dia".
  **O que fazemos com a resposta:** Ajuda a priorizar o que construir primeiro entre os seis assuntos
  possíveis.

- **Pergunta:** Existe prazo ou orçamento que já está definido para isso?
  **Por quê:** Muda o tamanho da proposta que vamos apresentar.
  **O que fazemos com a resposta:** Define se propomos algo enxuto pra já mostrar valor rápido, ou algo mais
  completo desde o início.

### Quem toca a produção no dia a dia

- **Pergunta:** Como uma ordem de produção é identificada do começo ao fim — o mesmo código aparece nos
  outros sistemas?
  **Por quê:** Se cada sistema chama a mesma coisa de um jeito diferente, nenhum painel vai conseguir juntar
  os dados direito.
  **O que fazemos com a resposta:** Define se precisamos criar uma "tradução" entre sistemas antes de
  qualquer outra coisa.

- **Pergunta:** O registro de produção é feito na hora, ou depois? Com quanto atraso?
  **Por quê:** Isso mostra a diferença entre o que a gente vê na tela e o que realmente aconteceu na fábrica.
  **O que fazemos com a resposta:** Define o quão "ao vivo" a informação pode realmente ser, com honestidade.

- **Pergunta:** O que conta como "parada" pra vocês? Toda parada é anotada, ou só as grandes?
  **Por quê:** Sem essa definição, qualquer número de "tempo parado" pode estar incompleto sem ninguém saber.
  **O que fazemos com a resposta:** Vira a definição oficial que todo o resto do projeto vai usar — sem
  reinventar essa definição em cada painel.

### Quem faz o planejamento

- **Pergunta:** Como é feita hoje a comparação entre planejado e realizado? Em que sistema, com que
  detalhe?
  **Por quê:** É literalmente um dos pedidos da diretoria — precisamos saber o ponto de partida real.
  **O que fazemos com a resposta:** Mostra se dá pra melhorar o que já existe ou se precisa começar do zero.

- **Pergunta:** O plano muda durante o dia? Essas mudanças ficam guardadas em algum lugar, ou são
  sobrescritas?
  **Por quê:** Sem o histórico de mudança, não dá pra saber se um atraso é culpa da execução ou de o plano
  ter mudado no meio do caminho.
  **O que fazemos com a resposta:** Define se precisamos guardar versões do plano ao longo do tempo, não só
  o plano atual.

### Quem cuida da qualidade

- **Pergunta:** Um desvio de qualidade é ligado a qual informação — o lote, a ordem, a linha, o equipamento?
  **Por quê:** Sem esse vínculo, não dá pra saber se um problema de qualidade tem relação com uma máquina ou
  linha específica.
  **O que fazemos com a resposta:** Define como vamos conseguir cruzar "problema de qualidade" com "o que
  estava acontecendo na produção" naquele momento.

- **Pergunta:** Quanto tempo leva entre o desvio acontecer e ser registrado no sistema?
  **Por quê:** Se o atraso for grande, um alerta "rápido" de qualidade na prática não é tão rápido assim.
  **O que fazemos com a resposta:** Ajusta a expectativa de velocidade que vamos prometer para esse alerta.

- **Pergunta:** Existe alguma exigência legal ou regulatória sobre como esse dado precisa ser guardado?
  **Por quê:** Indústria farmacêutica tem regra própria sobre isso — descobrir isso tarde custa caro.
  **O que fazemos com a resposta:** Define, desde o início, se o dado precisa ficar guardado de um jeito que
  não pode ser alterado depois (para fins de auditoria).

### Quem cuida da manutenção

- **Pergunta:** Toda parada de máquina é registrada, mesmo as pequenas, ou só as formais?
  **Por quê:** Um ranking de "equipamento que mais dá problema" feito só com paradas grandes pode estar
  incompleto.
  **O que fazemos com a resposta:** Define se o dado de manutenção que temos hoje já é confiável o suficiente
  para virar indicador, ou se precisa de ajuste antes.

- **Pergunta:** O identificador do equipamento é o mesmo usado pela Produção e pelos sensores?
  **Por quê:** Mesmo problema de "tradução" entre sistemas, agora para equipamento em vez de lote.
  **O que fazemos com a resposta:** Confirma (ou não) que dá pra cruzar dado de sensor com dado de
  manutenção sem trabalho extra de reconciliação.

### Quem cuida dos sensores e da automação da fábrica

- **Pergunta:** Que tipo de tecnologia os sensores usam para se comunicar? Já existe algo coletando esse
  dado hoje?
  **Por quê:** Isso muda completamente como vamos buscar esse dado — não existe um jeito único de "pegar
  dado de sensor".
  **O que fazemos com a resposta:** Define literalmente como o dado de fábrica vai chegar até nós.

- **Pergunta:** Com que frequência real cada sensor gera dado — e isso já fica guardado em algum lugar hoje?
  **Por quê:** Sensor pode gerar dado a cada segundo; nem sempre isso precisa (ou consegue) ser guardado
  assim.
  **O que fazemos com a resposta:** Ajuda a dimensionar o tamanho real do projeto de coleta desses dados.

- **Pergunta:** Existe algum computador com acesso tanto à rede da fábrica quanto à rede administrativa da
  empresa, mesmo que informalmente?
  **Por quê:** Essa é a pergunta que a gente quase deixou passar em versões anteriores deste levantamento —
  e é uma das mais importantes. Se existir essa ponte sem controle, qualquer projeto novo herda esse risco de
  segurança sem ninguém ter decidido isso.
  **O que fazemos com a resposta:** Decide se dá pra seguir com o projeto de coleta de sensores como está, ou
  se precisa resolver essa brecha de segurança antes de qualquer coisa.

### Quem cuida da infraestrutura de TI

- **Pergunta:** Quais sistemas já têm um jeito automático de puxar dado (API), e quais só dá para tirar
  manualmente?
  **Por quê:** Muda completamente o esforço e o prazo de cada fonte de dado.
  **O que fazemos com a resposta:** Vira a lista de prioridade — o que é mais fácil de conectar primeiro.

- **Pergunta:** Se a gente pedir acesso a um sistema novo, qual é o processo hoje? Quanto tempo demora?
  **Por quê:** Esse tipo de espera burocrática costuma ser subestimada no cronograma.
  **O que fazemos com a resposta:** Ajusta o prazo real do projeto, não o prazo ideal.

### Quem cuida da segurança da informação

- **Pergunta:** Existe uma separação de verdade (com firewall dedicado) entre a rede da fábrica e a rede
  administrativa, ou a separação é só "no papel"?
  **Por quê:** É a versão formal da pergunta que fizemos ao time de automação — agora com quem tem
  autoridade pra confirmar ou desmentir.
  **O que fazemos com a resposta:** Decide se o projeto de sensores pode seguir direto ou se precisa passar
  por uma etapa de reforço de segurança antes.

- **Pergunta:** Qual é hoje o processo para autorizar um novo ponto de coleta de dado da fábrica?
  **Por quê:** Sem saber isso, corremos o risco de simplesmente conectar algo sem passar pela aprovação
  certa.
  **O que fazemos com a resposta:** Vira uma etapa formal do nosso cronograma, não um detalhe.

### Quem cuida de assuntos legais e de regulação

- **Pergunta:** Existe exigência de conseguir rastrear um lote do início ao fim, de forma que não possa ser
  alterada depois?
  **Por quê:** Indústria farmacêutica costuma ter essa exigência — e ela muda como o dado precisa ser
  guardado.
  **O que fazemos com a resposta:** Define se algumas partes do sistema precisam ser "só de leitura" depois
  de escritas.

- **Pergunta:** Os registros de produção ou dos sensores identificam qual pessoa (operador, turno) estava
  envolvida?
  **Por quê:** Se sim, isso é dado pessoal e tem regra própria sobre quanto tempo pode ficar guardado e por
  quê.
  **O que fazemos com a resposta:** Decide se precisamos "disfarçar" essa informação antes de guardar, e por
  quanto tempo podemos mantê-la.

### Perguntas de robustez — pra sistema não quebrar quando alguma coisa der errado

Essas quatro entraram depois de revisarmos o que faltava pra proposta ser realmente robusta, não só completa.
Todas dentro do nosso papel (como os dados são coletados, guardados, processados) — nenhuma delas é sobre
indicador de negócio ou sobre viabilidade de Inteligência Artificial, que são investigações de outra
natureza.

- **Pergunta:** Se esse sistema parar de funcionar por um tempo, quanto tempo de dado dá pra perder sem
  prejuízo grande? E em quanto tempo ele precisa voltar a funcionar?
  **Por quê:** Sem essa resposta, o jeito de guardar backup e recuperar o sistema é escolhido no chute.
  **O que fazemos com a resposta:** Define o quão protegido o sistema precisa ser, desde o desenho — não
  depois que algo já quebrou.

- **Pergunta:** Esse tipo de dado se comporta sempre igual, ou tem época de pico (fim de mês, campanha,
  troca de turno)?
  **Por quê:** Um alerta simples só funciona bem se o padrão for estável; se varia bastante, precisa de algo
  mais esperto pra não disparar aviso falso o tempo todo.
  **O que fazemos com a resposta:** Decide que tipo de alerta faz sentido construir.

- **Pergunta:** Quantas pessoas ou sistemas vão consultar esse dado, comparado a quantos escrevem nele?
  **Por quê:** Se muita gente só olha e pouca gente escreve, dá pra separar essas duas partes e economizar
  recurso em vez de dimensionar tudo igual.
  **O que fazemos com a resposta:** Evita superdimensionar (ou subdimensionar) a parte errada do sistema.

- **Pergunta:** Os sensores perdem conexão de vez em quando? Quando voltam, recuperam o que ficou perdido
  durante a queda, ou começam do zero? E já existe um padrão de nome para os sensores, ou vamos inventar
  agora?
  **Por quê:** Sem isso, corremos o risco de perder dado sem perceber, ou de criar um padrão de nomenclatura
  que não aguenta crescer para mais sensores no futuro.
  **O que fazemos com a resposta:** Define como a coleta precisa se comportar quando a conexão cai — e evita
  ter que renomear tudo depois.

### Perguntas de continuidade do projeto

Essas quatro não são sobre como o sistema funciona tecnicamente — são sobre o que garante que o trabalho
continue de pé depois que o levantamento terminar.

- **Pergunta:** Ao lidar com dado que identifica uma pessoa (como operador em log de produção), existe um
  acordo formal definindo essa responsabilidade entre as partes?
  **Por quê:** Não é só sobre a postura de privacidade do cliente — é sobre a nossa própria responsabilidade
  ao lidar com esse dado.
  **O que fazemos com a resposta:** Define se precisamos formalizar esse acordo antes de tocar qualquer dado
  pessoal.

- **Pergunta:** Quem vai operar o que for construído depois que este trabalho terminar, e como garantimos
  que essa pessoa/time recebe o conhecimento necessário?
  **Por quê:** Uma solução tecnicamente correta que ninguém sabe operar depois vira um problema novo, não
  uma solução.
  **O que fazemos com a resposta:** Define o plano de transferência de conhecimento, não só a entrega técnica.

- **Pergunta:** O que você (cliente) considera "entregue e aceito"? É a mesma coisa que nosso critério
  técnico de conclusão, ou é diferente?
  **Por quê:** Um projeto pode estar tecnicamente pronto e ainda não ser aceito, se ninguém combinou o
  critério com antecedência.
  **O que fazemos com a resposta:** Alinha nosso critério de conclusão com o do cliente antes de declarar o
  trabalho pronto.

- **Pergunta:** Além de quem abriu o projeto, quem mais precisa "comprar a ideia" para a mudança realmente
  pegar no dia a dia?
  **Por quê:** Resistência de quem usa o sistema é uma das causas mais comuns de projeto tecnicamente pronto
  que não é adotado.
  **O que fazemos com a resposta:** Define quem mais precisa ser envolvido, além do patrocinador inicial,
  para a mudança realmente acontecer.

---

## A pergunta que fazemos pra todo mundo, sempre

**Quando dois sistemas contarem versões diferentes da mesma história, qual deles a gente confia?**

Essa pergunta não é de uma pessoa só — é de todo mundo que tem um sistema que registra algo parecido com o
que outro sistema também registra. Sem uma resposta clara aqui, mesmo juntando todos os dados corretamente, o
projeto ainda vai mostrar números que não batem entre si — e isso destrói a confiança de todo mundo no
trabalho, mesmo que tecnicamente esteja certo.

---

## O que fazemos com todas essas respostas, no fim das contas

Nenhuma dessas perguntas é curiosidade — cada uma existe porque a resposta muda algo concreto no que vamos
construir depois. Depois de reunidas, essas respostas fazem três coisas:

1. **Confirmam (ou corrigem) a nossa leitura do problema** — o que a diretoria pediu, traduzido em termos
   reais da fábrica, não em suposição nossa.
2. **Viram a lista de prioridade** — o que resolvemos primeiro, e o que fica pra depois.
3. **Apontam exatamente qual decisão de construção cada resposta destrava** — quando chegar a hora de
   desenhar a solução de verdade, não vamos começar do zero: cada resposta já vai estar ligada à parte do
   projeto que ela define.

Só depois de ter essas respostas — de verdade, conversando com as pessoas certas, não supondo — é que faz
sentido conversar sobre qual tecnologia usar.

---

Roberto Nascimento — [github.com/Roberton003](https://github.com/Roberton003)
