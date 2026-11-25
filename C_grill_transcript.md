# Transcrição da sessão grill-me — Service Blueprint AS-IS

**Exercício:** 3.1 · **Aluna:** Flavia Rios · **Serviço:** Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal (0800 726 0207; órgãos: CAIXA e MTE)
**Contexto:** `B_relatorio_assistente_v3.md` e a metodologia de Service Blueprint de Shostack (camadas, linhas e fail points).
**Condução:** entrevista no método grill-me (uma pergunta por vez, em tom adversarial), feita no Claude (claude.ai). O computador da aluna usa macOS Catalina, que não roda o Claude Code. As perguntas e as respostas estão transcritas na íntegra.
**Total:** 7 rodadas — R1 Jornada de referência; R2 Etapas na ótica do cidadão; R3 Linha de visibilidade; R4 Fail points; R5 Backstage × processos de suporte; R6 Convenção F/H/L e acessibilidade; R7 Relações do diagrama (Parte D).

---

## Rodada 1 — Jornada de referência

**Entrevistador (Claude, grill-me):**

A v3 lista mais de dez gatilhos possíveis: o 30º dia sem liberação, a parcela "paga" sem crédito, o calendário, o bloqueio de cartão ou senha, a devolução ao FAT após 67 dias, entre outros. Um blueprint AS-IS precisa de **uma jornada de referência**. Se tentar abarcar todos os gatilhos, as etapas viram uma mistura que ninguém consegue ler.

Duas opções fortes:
- **(a) "Passaram 30 dias e a parcela não foi liberada":** o gatilho está documentado na própria FAQ da CAIXA. A causa costuma estar no MTE ou nos dados (habilitação), então a URA da CAIXA tende a apenas encaminhar o cidadão. Mostra bem a fronteira entre a CAIXA e o MTE.
- **(b) "O status diz 'paga', mas o dinheiro não está na conta":** é o achado do TCU, a divergência entre o status do sistema e a experiência do cidadão. A causa costuma estar no pagamento, então a CAIXA é a dona do problema. Mostra bem a linha de visibilidade.

**Pergunta:** qual gatilho será a jornada de referência do seu blueprint, e por quê? O que você deixa de fora como fluxo alternativo?

**Aluna (Flavia Rios):**

Escolho a opção (b): “O status indica parcela paga, mas o dinheiro não está na conta”.
Esse episódio evidencia a divergência entre a informação apresentada ao cidadão e a execução efetiva do serviço, permitindo explorar as linhas de visibilidade, as integrações entre sistemas e as responsabilidades institucionais.
Deixo como fluxos alternativos a não liberação após 30 dias, o bloqueio de cartão ou senha, a consulta ao calendário e a devolução ao FAT. A responsabilidade pela causa da divergência deverá ser investigada, não presumida.

---

## Rodada 2 — Etapas na ótica do cidadão

**Entrevistador (Claude, grill-me):**

Decisão registrada: a jornada de referência é **(b) "paga" sem crédito**. As demais situações ficam como fluxos alternativos, e a causa da divergência será investigada, não presumida.

O blueprint precisa de pelo menos 5 etapas, que são as colunas da tabela, contadas do ponto de vista de quem consome o serviço. Aqui está o ponto delicado: o cidadão **vê o "paga" antes de ligar**, no app ou na CTPS Digital. Então a URA não é a primeira etapa. Ao mesmo tempo, se você começar muito cedo, na dispensa ou no requerimento, o blueprint vira o ciclo inteiro do benefício, que você descartou no 2.1.

Etapas candidatas, todas da v3:
1. Vê o status "paga" no app
2. Confere o extrato ou a conta e não encontra o crédito
3. Liga para o 0800 e navega pela URA
4. Fala com um atendente da CAIXA
5. Recebe uma orientação e é encaminhado
6. Recontata ou recorre ao SAC, à Ouvidoria ou ao 158
7. Recebe o crédito, desiste ou tem a parcela devolvida após 67 dias

**Pergunta:** quais etapas você escolhe (de 5 a 7, podendo juntar ou renomear) e onde o blueprint **começa e termina**? A etapa 4 (atendente humano) entra como coluna própria, mesmo que a v3 diga que o critério de transbordo da URA para o atendente é uma lacuna?

**Aluna (Flavia Rios):**

Escolho sete etapas: (1) consulta o status “paga”; (2) verifica a ausência do crédito; (3) liga e navega pela URA; (4) busca atendimento humano; (5) recebe orientação ou encaminhamento; (6) recontata ou busca outro canal; (7) obtém resolução ou permanece sem solução.
O blueprint começa na identificação da divergência e termina no desfecho do episódio de atendimento.
O atendimento humano terá coluna própria, mas será uma etapa condicional, pois os critérios de transbordo permanecem não comprovados.
A devolução ao FAT será tratada como fluxo alternativo, não como desfecho obrigatório.

---

## Rodada 3 — Linha de visibilidade

**Entrevistador (Claude, grill-me):**

Decisão registrada: **7 etapas**, do momento em que o cidadão identifica a divergência até o desfecho. O atendimento humano é uma **coluna condicional**, e a devolução ao FAT fica como fluxo alternativo.

O tutorial chama essa decisão de "a barreira mais sensível". O seu caso tem uma armadilha. O status **"paga"** que o cidadão vê no app (etapa 1) **não nasce no app**. Segundo a v3, ele vem de um **arquivo de retorno** que a CAIXA envia ao MTE e à Dataprev, e esse arquivo pode marcar "paga" antes de o crédito se concretizar. Ou seja, a falha que gera todo o episódio é **invisível**, mas a consequência dela é **visível**.

Classifique quatro elementos, cada um em uma camada: **evidência física**, **frontstage**, **backstage** ou **processo de suporte**.
- (i) a mensagem "paga" na tela do app ou da CTPS Digital;
- (ii) a URA respondendo sobre a parcela;
- (iii) o arquivo de retorno CAIXA → MTE/Dataprev, que marca a parcela como "paga";
- (iv) o envio do crédito para outro banco, que pelo contrato já conta como "efetivamente paga".

**Pergunta:** em que camada fica cada um? E a URA, por ser uma máquina, fica **acima ou abaixo** da linha de visibilidade?

**Aluna (Flavia Rios):**

* (i) Evidência física/digital: mensagem “paga” exibida na tela do aplicativo.
* (ii) Frontstage: resposta automatizada da URA ao cidadão.
* (iii) Backstage: geração e transmissão do arquivo de retorno CAIXA–MTE/Dataprev.
* (iv) Backstage: processamento e envio do crédito para outro banco.

A URA fica acima da linha de visibilidade, pois interage diretamente com o cidadão. O critério é a percepção do usuário, independentemente de o atendimento ser humano ou automatizado.

---

## Rodada 4 — Fail points

**Entrevistador (Claude, grill-me):**

Decisão registrada:
- (i) a mensagem "paga" é **evidência física/digital**;
- (ii) a URA é **frontstage**;
- (iii) o arquivo de retorno é **backstage**;
- (iv) o envio do crédito a outro banco é **backstage**.

O critério é a **percepção do usuário**, independentemente de quem atende ser uma máquina ou uma pessoa.

A v3 lista 17 pontos de falha possíveis. Um blueprint com 17 alertas não aponta nada. Há também uma escolha de método: o "paga sem crédito" se **manifesta** nas etapas 1 e 2 (visíveis), mas se **origina** no backstage (o arquivo de retorno). Se você marcar só a manifestação, o blueprint esconde a causa. Se marcar só a origem, esconde o sofrimento do cidadão.

Candidatos ligados às suas 7 etapas:
- **PF07** — status "paga" sem crédito (origem no backstage, etapas 1 e 2);
- **L09 / PF02** — a URA pode repetir "paga" sem distinguir "enviada" de "creditada" (etapa 3);
- **L04** — transbordo para o atendente sem critério conhecido (etapa 4);
- **PF08** — encaminhamento em que o cidadão carrega o contexto sozinho, sem protocolo compartilhado (etapas 5 e 6);
- **PF09 e PF12** — a ligação termina sem resolver, e o cidadão recontata e alterna canais (etapas 6 e 7).

**Pergunta:** quais fail points você marca (sugiro de 3 a 5), em qual etapa cada um fica e se o PF07 aparece **na origem**, **na manifestação** ou **nos dois lugares**, ligados entre si?

**Aluna (Flavia Rios):**

Seleciono quatro pontos de falha, diretamente relacionados à jornada de referência:

* PF07 — Etapas 1 e 2: marcar a possível origem no backstage e a manifestação visível ao cidadão, conectando-as por uma seta.
* PF02/L09 — Etapa 3: possível reprodução da informação divergente pela URA.
* PF08 — Etapas 5 e 6: encaminhamento sem continuidade do contexto do atendimento.
* PF09/PF12 — Etapas 6 e 7: ausência de resolução, recontatos e peregrinação entre canais.

A L04 permanece como lacuna de conhecimento, não como falha operacional comprovada.

---

## Rodada 5 — Backstage × processos de suporte

**Entrevistador (Claude, grill-me):**

Decisão registrada: **4 fail points**.
- **PF07:** marcado **na origem e na manifestação**, ligados por uma seta;
- **PF02/L09:** na etapa 3;
- **PF08:** nas etapas 5 e 6;
- **PF09/PF12:** nas etapas 6 e 7.

O L04 fica como **lacuna de conhecimento**, e não como falha comprovada. Essa distinção é boa.

Na tradição de Bitner, o **backstage** são as ações *do próprio prestador* que o cidadão não vê, como o atendente consultando o sistema ou a CAIXA processando o crédito. Os **processos de suporte** são os sistemas, as outras unidades e os terceiros de que o backstage depende. Aqui está a sua tensão: no seu serviço, o "prestador" são duas instituições (CAIXA e MTE), e várias peças ficam na fronteira entre as camadas.

Classifique como **backstage**, **suporte** ou **fora do blueprint**:
- (a) o Sistema do Seguro-Desemprego, operado pela Dataprev;
- (b) o banco recebedor, quando o crédito vai para outra instituição;
- (c) o Portal de Demandas/SIRCA, o canal interno CAIXA–MTE;
- (d) a fiscalização contratual do MTE, que hoje remunera a CAIXA **por parcela paga** (Contrato 07/2026), e não por ligação.

**Pergunta:** em que camada fica cada um? Sobre o item (d): remunerar "por parcela paga" pode criar um incentivo para marcar como "paga" o mais cedo possível. Você representa essa hipótese no blueprint ou deixa de fora por falta de evidência?

**Aluna (Flavia Rios):**

* (a) Suporte: Sistema do Seguro-Desemprego, operado pela Dataprev.
* (b) Suporte: banco recebedor, responsável pela etapa externa de disponibilização do crédito.
* (c) Suporte: Portal de Demandas/SIRCA; sua utilização pelos operadores constitui uma atividade de backstage.
* (d) Fora do blueprint: fiscalização contratual, por pertencer à camada de governança institucional.

A hipótese de incentivo à antecipação do status “paga” ficará fora do blueprint AS-IS, sendo registrada como hipótese de investigação, sem evidência suficiente de relação causal.

---

## Rodada 6 — Convenção F/H/L e acessibilidade

**Entrevistador (Claude, grill-me):**

Decisão registrada:
- **(a), (b) e (c) são suporte.** O *uso* do SIRCA pelos operadores é uma atividade de backstage.
- **(d) fica fora do blueprint,** como governança.
- **A hipótese de incentivo** fica registrada para investigação, mas não entra no AS-IS.

A v3 é honesta: a **árvore da URA**, os **dados que ela pede**, o **protocolo** e o **critério de transbordo** são lacunas (L01, L02, L04, L06). Só que um blueprint é uma tabela, e as células de evidência física e de frontstage das etapas 3 e 4 ficariam quase vazias. Há três jeitos de lidar com isso:
- **(a)** Deixar a célula com a marca **"L"** e o código da lacuna, como "áudio do menu (conteúdo L01)". É honesto, mas visualmente pobre.
- **(b)** Preencher com as **hipóteses** das fontes secundárias, como a opção "Cartão Social", marcadas como **H**. É mais rico, mas há risco de parecer fato.
- **(c)** Preencher **só com o que é F** e mover as lacunas para uma linha final "Lacunas a validar", abaixo dos fail points.

E outra questão: a jornada de pessoas **surdas** (Libras, sem equivalência comprovada com a URA) aparece no blueprint, ou fica fora como fluxo alternativo?

**Pergunta:** qual convenção você adota para F, H e L nas células, e o que faz com a acessibilidade?

**Aluna (Flavia Rios):**

Adoto a opção (a), com identificação explícita do grau de evidência nas próprias células:

* F — Fato: informação comprovada por fonte documental.
* H — Hipótese: somente quando diretamente relevante à jornada escolhida, sem apresentá-la como fato.
* L — Lacuna: informação desconhecida, acompanhada do respectivo código (L01, L02, L04, L06).

A acessibilidade será representada como fluxo alternativo, destacando a ausência de equivalência comprovada entre o atendimento em Libras e a URA, sem presumir que essa alternativa garanta a resolução do episódio.

---

## Rodada 7 — Relações do diagrama (Parte D)

**Entrevistador (Claude, grill-me):**

Decisão registrada: a convenção é **(a)**, com **F, H e L marcados nas próprias células**. A H só entra quando for diretamente relevante, e a L sempre vem com o seu código. A **acessibilidade** fica como fluxo alternativo, sem presumir que o atendimento em Libras seja equivalente à URA.

A rubrica da Parte D exige **relações explícitas**: setas, e não uma lista de caixas. Ela também exige que os nós reflitam o que foi decidido aqui. O diagrama não precisa repetir o blueprint. Ele deve mostrar o que a tabela não mostra bem: **o fluxo e os desvios**. Faltam três decisões:

1. **O laço do recontato:** a etapa 6 ("recontata ou busca outro canal") volta para a etapa 3 (URA) e/ou abre caminhos para o SAC, a Ouvidoria e o 158? Você desenha isso como um **ciclo explícito**, que é a imagem da peregrinação?
2. **A ligação do PF07:** a seta que liga a origem (arquivo de retorno, no backstage) à manifestação (o "paga" no app) aparece no diagrama, cruzando a linha de visibilidade?
3. **Os desfechos:** a etapa 7 termina em quantos finais distintos? Por exemplo: crédito recebido, desistência, devolução ao FAT (fluxo alternativo).

**Pergunta:** decida esses três pontos. Depois desta rodada, eu monto o `C_blueprint_asis.md`, o `D_diagrama_asis.md` e a transcrição.

**Aluna (Flavia Rios):**

1. Laço de recontato: representar um ciclo explícito da etapa 6 para a etapa 3 (URA), com ramificações para SAC, Ouvidoria e 158, sem presumir transferências automáticas.
2. PF07: representar a ligação entre a possível origem no backstage e a manifestação no aplicativo, cruzando a linha de visibilidade. Utilizar seta tracejada para indicar causalidade não integralmente comprovada.
3. Desfechos: representar quatro finais distintos: crédito recebido, desistência, permanência sem resolução e devolução ao FAT após 67 dias, sendo este último um fluxo alternativo condicionado à aplicabilidade da regra.

O diagrama deverá evidenciar a peregrinação do cidadão sem transformar hipóteses em fatos comprovados.

---
