# Auditoria da v1 — Operação AS-IS do Atendimento ao Seguro-Desemprego pela URA da CAIXA

**Assistente auditor:** Claude (Anthropic). **Pesquisa auditada:** `B_relatorio_assistente_v1.md`, produzida pelo ChatGPT (OpenAI).

**Critério:** só entram falhas de conteúdo que afetam o futuro Service Blueprint AS-IS: erros factuais, etapas de bastidor omitidas, evidências físicas e normativos ausentes, fail points não identificados, inferências mal-suportadas e fontes fracas. Questões de formatação e estilo foram desconsideradas.

## Avaliação geral

A v1 é metodologicamente cuidadosa. Ela distingue ligação de episódio e status de crédito, e trata como lacuna, sem inventar, a árvore de menus da URA. Os contratos de 2021 e 2026 foram bem lidos.

Mas a pesquisa tem três problemas graves para um blueprint:
1. **Nenhuma fonte é verificável.** Todas as citações aparecem como marcadores internos do assistente, sem URL.
2. **A pesquisa deixa de fora evidências públicas da própria CAIXA**, sobre prazos, cartão e senha e usos do 0800, que mudam as etapas, as evidências físicas e os fail points.
3. **O "antes da ligação" ficou mais fraco do que a evidência permite.** Isso contraria o pedido de começar pela ótica do cidadão.

---

## Falha 1 — Rastreabilidade inexistente: nenhuma das citações é verificável

**Tipo:** fontes fracas ou ausentes.

**Trechos:** "citeturn987017search0turn987017search1", "fileciteturn0file0", e a coluna "URL/fonte" do dossiê-mestre (E001 a E032), preenchida com marcadores como "citeturn832799search3".

**Justificativa:** esses marcadores são referências internas da sessão do assistente, que não podem ser resolvidas por um leitor externo. **Não há uma única URL no documento.** O protocolo F/I/H/L/D e a coluna "Confiança" dão aparência de rigor, mas nenhum "F" (fato documentado) pode ser conferido por terceiros. Isso compromete todo o dossiê, porque o blueprint precisará cruzar cada etapa e cada fail point com a sua fonte. A v2 deve substituir cada marcador pela URL e pela localização no documento (página, cláusula, item ou parágrafo).

---

## Falha 2 — O gatilho "antes da ligação" está documentado, e a v1 diz que não está

**Tipo:** inferência mal-suportada e etapa da jornada omitida.

**Trecho da v1:** "Antes da ligação, a evidência pública não permite afirmar um único gatilho representativo."

**Justificativa:** a própria página de Perguntas Frequentes da CAIXA sobre o Seguro-Desemprego (fonte que a v1 usa como E005) informa que **a liberação da parcela ocorre sempre 30 dias após a requisição ou o saque da parcela anterior**. Ela também traz a pergunta "Fiz o requerimento do meu Seguro-Desemprego há mais de 30 dias e não foi liberado. O que devo fazer?". A Resolução CODEFAT nº 957/2022, art. 12, fixa o mesmo prazo: 30 dias contados do requerimento para o trabalhador formal.

Isso documenta um gatilho temporal concreto e recorrente: **a expectativa do 30º dia frustrada**. É exatamente o momento em que nasce a ligação "minha parcela não caiu". Também documenta que a CAIXA **antecipa essa demanda** na sua FAQ, o que é um indício de demanda de falha previsível. A v1 deveria reconstruir a linha do tempo antes da ligação: dispensa → requerimento (de 7 a 120 dias após a dispensa) → espera de 30 dias → consulta ou ligação.

---

## Falha 3 — Fail point crítico omitido: parcela não sacada é devolvida ao FAT após 67 dias

**Tipo:** fail point não identificado e normativo omitido.

**Justificativa:** segundo a FAQ da CAIXA e o art. 21 da Resolução CODEFAT nº 957/2022, **a parcela fica disponível por 67 dias**. Depois disso, o agente pagador devolve o recurso ao FAT. Esse é um ponto de falha de alto impacto, e a v1 não o menciona em nenhum dos inventários (fail points, variações, matriz normativa). Um cidadão que recebe na URA uma informação incompleta, ou que demora a sacar por estar preso na "peregrinação" que o TCU documentou, pode **perder a parcela**. Para o blueprint AS-IS, isso define um prazo crítico no backstage (a devolução ao FAT) com consequência visível ao cidadão.

---

## Falha 4 — Cartão do Cidadão e Senha Cidadão: evidências físicas, etapas de bastidor e fail points omitidos

**Tipo:** evidência física omitida, etapa de bastidor omitida e fail point não identificado.

**Trecho da v1:** no inventário de evidências físicas (ED01 a ED11), não aparece o **Cartão do Cidadão** nem a **Senha Cidadão**.

**Justificativa:** a CAIXA mantém uma página institucional de serviço para o Cartão do Cidadão e a Senha Cidadão. Fontes secundárias amplamente difundidas descrevem que o cartão serve para sacar as parcelas do Seguro-Desemprego por quem não tem conta, e que a **solicitação, o desbloqueio e a orientação para cadastrar a senha passam pelo menu eletrônico do próprio 0800 726 0207**. Se isso for confirmado em fonte primária, há quatro consequências:
- **Evidência física:** o cartão de plástico e a senha são objetos concretos da jornada.
- **Backstage e suporte:** emissão, envio pelos Correios, desbloqueio e cadastro de senha em lotérica ou terminal.
- **Fail points:** cartão não recebido, bloqueado ou perdido; senha esquecida ou bloqueada, exigindo ida presencial.
- **Usos da URA:** a URA serve também para gerir o meio de saque, e não apenas para consultar a parcela.

A v1 deve verificar essas funções nas páginas oficiais da CAIXA e incorporá-las ou descartá-las com justificativa.

---

## Falha 5 — O 0800 726 0207 também é canal de requerimento, segundo a CAIXA

**Tipo:** erro de escopo e etapa omitida.

**Trecho da v1:** o 0800 é tratado ao longo de todo o texto apenas como canal de "consulta de liberação de parcelas".

**Justificativa:** a FAQ da CAIXA, no item "Onde requerer?", lista o **Serviço de Atendimento ao Cidadão, pelo 0800 726 0207**, entre os canais para requerer o Seguro-Desemprego, ao lado do gov.br, da CTPS Digital, do Emprega Brasil, do Portal Cidadão e do CAIXA Tem. A v1 não registra isso, nem como fato nem como divergência em relação à Carta de Serviços do MTE. Para o blueprint, isso muda as etapas possíveis do frontstage telefônico (requerer, além de consultar) e as fronteiras de responsabilidade CAIXA–MTE na ligação.

---

## Falha 6 — SAC e Ouvidoria da CAIXA ausentes como caminhos do episódio

**Tipo:** etapa e canal omitidos.

**Justificativa:** a CAIXA divulga canais telefônicos distintos para **SAC (0800 726 0101)** e **Ouvidoria (0800 725 7474)**, além do 0800 726 0207. Quando a URA ou o atendente não resolvem, esses são os caminhos formais de reclamação do cidadão na própria CAIXA. A v1 só menciona ouvidoria de forma genérica, citando o TCU, e não inclui esses canais no frontstage, nas interfaces (IT01 a IT09) nem nas variações. Sem eles, o blueprint perde a etapa de escalonamento dentro da CAIXA. O próprio mapa de atores do exercício anterior tinha "CAIXA — SAC e Ouvidoria" como ator do mapa principal.

---

## Falha 7 — Normativo de simplificação e "once-only" omitido

**Tipo:** normativo relevante omitido.

**Trecho da v1:** a matriz normativa inclui a Lei 13.460/2017, a Lei 14.129/2021, a LGPD e a LBI, mas não o Decreto nº 9.094/2017.

**Justificativa:** o Decreto nº 9.094/2017, que regulamenta a Lei 13.460, obriga os órgãos federais a obter diretamente das bases oficiais os documentos e dados que já constem delas, sem exigi-los do usuário. Com a redação dada pelo Decreto 9.723/2019, ele também estabelece o **CPF como número suficiente** para identificar o cidadão. Para o blueprint AS-IS, essa é a régua normativa para avaliar dois fail points que a própria v1 aponta: a **repetição de informações entre canais** (PF08) e a **autenticação na URA** (L02). Se a URA exigir NIS/PIS em vez do CPF, ou se o cidadão precisar reapresentar dados em cada canal, há tensão com essa norma, e isso deveria ser registrado como hipótese a validar.

---

## Falha 8 — Evidência física pré-ligação omitida: o documento de requerimento

**Tipo:** evidência física omitida.

**Justificativa:** a Carta de Serviços "Solicitar o Seguro-Desemprego" informa que o trabalhador precisa ter o **documento do Requerimento do Seguro-Desemprego, que recebe do empregador no momento da dispensa sem justa causa**, além do CPF. Esse é o primeiro objeto físico ou digital da jornada, e é também onde se originam os erros de dados do empregador (PF06). O inventário de evidências físicas da v1 começa no número do 0800 e pula esse elemento.

---

## Falha 9 — Indicador mais recente do 158 ignorado em favor de dados de 2019

**Tipo:** fonte desatualizada e lacuna de evidência.

**Trecho da v1:** "Chamadas 158 | 3.993.068 entregues em 2019 [...]" e "Espera/abandono atuais | valor não localizado".

**Justificativa:** o MTE divulgou que a Central Alô Trabalho realizou **1.726.914 atendimentos no primeiro semestre de 2025**, dos quais 23% foram sobre Seguro-Desemprego (cerca de 397 mil) e 48% sobre Abono Salarial. É um dado de 2025, oficial e específico do tema, mais pertinente para o AS-IS do que a série de 2017–2019, que a própria v1 classifica como "obsoleta". Ele não mede a URA da CAIXA, mas dimensiona o canal paralelo para onde o cidadão é encaminhado.

---

## Falha 10 — Atribuição ao TCU sem trecho verificável ("síndrome do balcão")

**Tipo:** inferência mal-suportada e fonte fraca.

**Trecho da v1:** "O Tribunal denominou esse fenômeno, no contexto auditado, de 'síndrome do balcão'."

**Justificativa:** a expressão vem entre aspas e é atribuída ao TCU, mas a única referência é um marcador interno não verificável (Falha 1) e o "§195" no dossiê-mestre. No exercício anterior, essa mesma expressão não foi encontrada nas comunicações públicas do TCU sobre o Acórdão 1.621/2026. A v2 deve transcrever o trecho exato, com o parágrafo e o link do acórdão. Se não conseguir, deve apresentar a expressão como rótulo analítico próprio, e não como palavra do Tribunal.

---

## Falha 11 — Inventário da jornada mistura ações do cidadão com processos de bastidor

**Tipo:** inferência e estrutura incompatível com a ótica do cidadão.

**Trecho da v1:** "J11 | Pagamento é processado | parcela apta | aguarda crédito | CAIXA/bancos | financeiro".

**Justificativa:** o pedido era reconstruir a jornada **na ótica do cidadão**. J11 é um evento de backstage (o processamento do pagamento), que aparece como acontecimento da jornada. O que o cidadão vive nesse momento é **esperar e verificar o extrato ou o app**. Misturar as duas coisas prejudica justamente a decisão central do blueprint: onde passa a linha de visibilidade. A v2 deve separar o que o cidadão faz e percebe do que acontece por trás.

---

## Síntese das correções esperadas na v2

1. Substituir todos os marcadores internos por URLs e localização exata (Falha 1).
2. Reconstruir a linha do tempo antes da ligação, com os prazos de 7 a 120 dias para requerer e de 30 dias para a liberação, usando a FAQ da CAIXA e o art. 12 da Res. 957 (Falha 2).
3. Incluir o prazo de 67 dias e a devolução ao FAT como fail point e como norma (Falha 3).
4. Verificar e incorporar o Cartão do Cidadão e a Senha Cidadão e as funções do 0800 além da consulta (Falhas 4 e 5).
5. Incluir o SAC e a Ouvidoria da CAIXA como canais do episódio (Falha 6).
6. Incluir o Decreto 9.094/2017 (CPF suficiente e "once-only") na matriz normativa e relacioná-lo aos fail points de autenticação e repetição (Falha 7).
7. Incluir o documento de requerimento como evidência física inicial (Falha 8).
8. Atualizar os indicadores do 158 com os dados de 2025 (Falha 9).
9. Comprovar ou reclassificar a "síndrome do balcão" (Falha 10).
10. Separar as ações do cidadão dos eventos de backstage no inventário da jornada (Falha 11).

## Fontes consultadas pela auditoria

- CAIXA — Perguntas Frequentes sobre o Seguro-Desemprego (liberação em 30 dias, disponibilidade por 67 dias, canais de requerimento incluindo o 0800 726 0207): https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/Paginas/default.aspx
- CAIXA — página de serviço Cartão do Cidadão / Senha Cidadão: https://www.caixa.gov.br/servicos/cartao-cidadao/Paginas/default.aspx
- Serasa — descrição do uso do 0800 726 0207 para solicitar e desbloquear o Cartão do Cidadão (fonte secundária, a confirmar em fonte primária): https://www.serasa.com.br/blog/cartao-cidadao-o-que-e-como-fazer-e-como-desbloquear/
- CAIXA — telefones divulgados (SAC 0800 726 0101; Ouvidoria 0800 725 7474): https://www.caixa.gov.br/fundos-investimento/renda-fixa/longo-prazo/Paginas/default.aspx
- Resolução CODEFAT nº 957/2022 (art. 12, prazos da primeira parcela; art. 21, disponibilidade por 67 dias): https://www.normaslegais.com.br/legislacao/resolucao-codefat-957-2022.htm
- Decreto nº 9.094/2017 (obtenção direta de dados nas bases oficiais; CPF como identificador suficiente): https://planalto.gov.br/ccivil_03/_ato2015-2018/2017/decreto/d9094.htm
- Carta de Serviços "Solicitar o Seguro-Desemprego" (documento de requerimento entregue pelo empregador): https://www.gov.br/pt-br/servicos/solicitar-o-seguro-desemprego
- Central Alô Trabalho: 1.726.914 atendimentos no 1º semestre de 2025: https://www.contabeis.com.br/noticias/72162/alo-trabalho-bate-1-7-mi-de-atendimentos/
