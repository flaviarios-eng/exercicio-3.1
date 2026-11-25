# Dossiê de evidências v2 para o Service Blueprint AS-IS do atendimento ao Seguro-Desemprego pela URA da CAIXA

## Escopo, método e síntese executiva

Esta v2 revisa integralmente o dossiê anterior à luz das onze falhas apontadas na auditoria. Os dois arquivos fornecidos — o relatório v1 e a auditoria — estavam acessíveis e foram confrontados entre si e com fontes primárias atuais. O recorte metodológico original foi preservado: a unidade de análise continua sendo **o episódio completo de atendimento relacionado à consulta de parcelas e pagamentos do Seguro-Desemprego pelo canal telefônico da CAIXA**, e não apenas a ligação; não se elabora aqui o blueprint definitivo, não se propõe TO-BE e não se priorizam antecipadamente fail points.

Permanece válido o protocolo de classificação: **F — fato documentado; I — inferência sustentada; H — hipótese a validar; L — lacuna; D — divergência**. Obrigações normativas ou contratuais são tratadas como evidência de obrigação, não automaticamente como prova de execução. Ausência de documentação pública não é tratada como prova de inexistência.

A conclusão operacional central da v1 permanece válida: a CAIXA continua divulgando o **0800 726 0207 — Atendimento CAIXA Cidadão**, inclusive para benefícios sociais; o atendimento eletrônico do canal é divulgado como disponível 24 horas por dia, sete dias por semana, e o humano, de segunda a sexta-feira das 8h às 21h e aos sábados das 10h às 16h. A FAQ atual de Seguro-Desemprego inclui o 0800 726 0207 entre os canais para **acompanhar a situação da parcela**. Não foi localizada fonte pública oficial que exponha a árvore vigente da URA do Seguro-Desemprego, seus menus, opções numéricas, mensagens gravadas, autenticação, critérios de transbordo, dados solicitados ou protocolo específico. Esses elementos permanecem **L**. Fontes: CAIXA Atendimento, <https://www.caixa.gov.br/atendimento/Paginas/default.aspx>; CAIXA FAQ Seguro-Desemprego, <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx>.

A revisão altera, porém, substancialmente o **antes da ligação**. Há um marco temporal objetivo que pode desencadear a procura por informação: para o trabalhador formal, a primeira parcela deve ser disponibilizada 30 dias após o requerimento e as seguintes em intervalos de 30 dias a partir da emissão da anterior. O requerimento pode ser apresentado do 7º ao 120º dia após a dispensa. A FAQ da CAIXA antecipa expressamente a situação “requerimento há mais de 30 dias e não liberado”. Isso não prova que o 30º dia seja **o gatilho mais frequente**, mas comprova que é um gatilho institucionalmente previsto e suficientemente recorrente para estar na FAQ. Resolução CODEFAT nº 957/2022, arts. 12 e 41, versão consolidada em 2026: <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf>; FAQ CAIXA: <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx>.

A auditoria também identificou corretamente a importância do prazo de **67 dias**. O art. 21 da Resolução 957 estabelece que a parcela fica disponível durante 67 dias a partir da disponibilização para saque e, depois, deve ser devolvida pelo agente pagador ao FAT. Há, contudo, uma ressalva importante não explicitada na auditoria: o §2º permite que a parcela devolvida seja **reemitida a pedido do beneficiário ou por decisão judicial em até dois anos da emissão**. Portanto, “perder a parcela” seria formulação excessiva; o fail point documentado é a perda da disponibilidade imediata, devolução do recurso ao FAT e necessidade potencial de reemissão. Fonte: <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf>, art. 21, caput e §2º.

A arquitetura institucional permanece dividida. A Resolução 957 determina que requisitos sejam aferidos automaticamente pelo sistema Seguro-Desemprego com dados de bases como CNIS e eSocial; a Dataprev declara ser responsável pelo sistema que analisa os requisitos do benefício; a CAIXA é o agente pagador das modalidades do programa. Logo, uma percepção única do cidadão — “minha parcela não caiu” — pode envolver habilitação, emissão da parcela, transferência de dados, processamento bancário ou disponibilização do valor. Fontes: Resolução 957, arts. 4º e 64, <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf>; Dataprev, <https://dataprev.gov.br/solucoes/casos-de-sucesso/seguro-desemprego>.

O Contrato nº 11/2021 remunerava separadamente o item **“Atendimento Canal de Telesserviços – URA”**, a R$ 0,53 por atendimento, e o Projeto Básico determinava que essa URA disponibilizasse informações sobre a situação das parcelas e pagamentos. O Contrato nº 07/2026, vigente no recorte atual, tem apenas a unidade “Pagamento de Parcelas aos Beneficiários do Seguro Desemprego”, a R$ 2,25, estimada em 170.366.759 parcelas e R$ 383.325.207,75 para cinco anos. A ausência de item tarifário separado prova uma alteração na estrutura remuneratória, mas **não prova a extinção da URA**, pois o Termo de Referência admite subcontratação de serviços acessórios como atendimento ao público. Fontes: Contrato 11/2021, cláusula 1.3, item 6, cláusula 3.1(f) e Projeto Básico 7.1.8.20, <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/contratos/pdf/11_2021.pdf>; Contrato 07/2026, cláusulas 1 e 5 e TR 4.6.1.1, <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/pca/072026completo.pdf>.

O Acórdão TCU nº 1.621/2026 documenta baixa clareza das informações, deficiência de notificações, baixa capacidade de resposta e resolução dos canais e encaminhamentos sucessivos. Também registra situação particularmente relevante ao blueprint: o sistema do Seguro-Desemprego recebe retorno da CAIXA marcando a parcela como “paga”, enquanto o crédito efetivo depende de processamento posterior e pode não se concretizar. O TCU determinou integração ao eSocial para evitar entrada duplicada de dados e recomendou medidas de monitoramento do atendimento. A expressão **“síndrome do balcão” não foi localizada no texto integral pesquisável do Acórdão nem na notícia oficial do TCU**; a v2 deixa de atribuí-la ao Tribunal. Fontes: decisão integral, <https://pesquisa.apps.tcu.gov.br/documento/acordao-completo/%2A/NUMACORDAO%253A1621%2520ANOACORDAO%253A2026/DTRELEVANCIA%2520desc%252C%2520NUMACORDAOINT%2520desc%252C%2520COPIACOLEGIADO%2520desc/0>; notícia oficial, <https://portal.tcu.gov.br/imprensa/noticias/tribunal-avalia-servico-digital-de-seguro-desemprego-para-trabalhadores-formais>.

A Central Alô Trabalho 158 continua sendo um canal do MTE para Seguro-Desemprego. O TED 7AAGCV/2026, assinado em 14 de agosto de 2026, descentraliza ao INSS a prestação de serviços de contact center, teleatendimento receptivo e ativo, multimeios e help desk, com vigência de 60 meses. O dado quantitativo contemporâneo acrescentado nesta v2 é que a Central registrou **1.726.914 atendimentos no primeiro semestre de 2025**, dos quais 23% foram classificados como Seguro-Desemprego — aproximadamente 397 mil, se aplicado o percentual ao total. Essa aproximação é **I**, pois a notícia divulga o percentual, não a contagem exata da categoria. Fontes: TEDs MTE, <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/convenios-e-transferencias/termos-de-execucao-descentralizada>; notícia MTE, <https://www.gov.br/trabalho-e-emprego/pt-br/noticias-e-conteudo/2025/agosto/central-201calo-trabalho201d-mais-de-1-7-milhao-de-atendimentos-no-primeiro-semestre-de-2025>.

### Fundamentação metodológica preservada

Shostack propôs em 1982 a representação sistemática do serviço como forma de tornar sua estrutura, evidências e sequência observáveis e gerenciáveis. Referência: G. Lynn Shostack, *How to Design a Service*, *European Journal of Marketing*, 16(1), 49–63, DOI <https://doi.org/10.1108/EUM0000000004799>.

Em 1984, Shostack consolidou o blueprint como instrumento para projetar, controlar e reconhecer vulnerabilidades na prestação de serviços. Referência: G. Lynn Shostack, *Designing Services That Deliver*, *Harvard Business Review*, 62(1), 133–139, <https://hbr.org/1984/01/designing-services-that-deliver>.

Bitner, Ostrom e Morgan sistematizaram posteriormente as camadas de ações do cliente, frontstage, backstage e processos de suporte e as linhas de interação, visibilidade e interação interna, enfatizando a experiência do usuário. Referência: Bitner, Ostrom & Morgan, *Service Blueprinting: A Practical Technique for Service Innovation*, *California Management Review* 50(3), 66–94, DOI <https://doi.org/10.2307/41166446>.

Para este objeto, o mapa de atores responde **quem participa**; a jornada registra o que acontece ao cidadão; o fluxograma descreve lógica processual; e o Service Blueprint conecta ações do cidadão, evidências, frontstage, backstage e suporte. A v2 mantém os acontecimentos em granularidade suficiente para organização posterior e evita antecipar as etapas definitivas do blueprint.

## Dossiê-mestre de evidências e contexto institucional

A numeração E001–E032 da v1 foi preservada. Evidências novas recebem E033 em diante.

| ID | Afirmação sustentada | Classe | Documento / localização | URL direta | Confiança / limitações |
|---|---|---|---|---|---|
| E001 | Shostack propõe visualização e modelagem sistemática de serviços | F | *How to Design a Service*, 1982, pp. 49–63 | <https://doi.org/10.1108/EUM0000000004799> | Alta |
| E002 | Blueprint permite projeto e controle sistemáticos e identificação de vulnerabilidades | F | *Designing Services That Deliver*, 1984 | <https://hbr.org/1984/01/designing-services-that-deliver> | Alta |
| E003 | Bitner et al. estruturam blueprint em ações do cliente, frontstage, backstage e suporte | F | CMR 50(3), 2008 | <https://doi.org/10.2307/41166446> | Alta |
| E004 | CAIXA Cidadão: 0800 726 0207; eletrônico 24x7; humano em horários divulgados | F | CAIXA, “Atendimento CAIXA Cidadão” | <https://www.caixa.gov.br/atendimento/Paginas/default.aspx> | Alta; horário é do canal geral |
| E005 | CAIXA indica 0800 726 0207 para acompanhar situação de parcela | F | FAQ Seguro-Desemprego, seção de acompanhamento | <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx> | Alta |
| E006 | Contrato 11/2021 remunerava URA a R$0,53/atendimento; projeção 48.974.350 | F | cláus. 1.3 item 6; cláus. 3.1(f); PB 7.1.8.20 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/contratos/pdf/11_2021.pdf> | Alta; histórico |
| E007 | Contrato 07/2026 remunera “parcela paga” a R$2,25; 170.366.759 parcelas estimadas | F | cláus. 1.1 e 5.1 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/pca/072026completo.pdf> | Alta |
| E008 | Contrato/TR 07/2026 não individualiza “URA”/“telesserviços” como unidade remunerada | F | pesquisa integral do documento | mesmo URL de E007 | Alta quanto ao documento; não prova extinção |
| E009 | Serviços acessórios, inclusive atendimento ao público, podem ser subcontratados | F | TR 4.6.1.1 | mesmo URL de E007 | Alta |
| E010 | O novo contrato contém obrigação de continuidade na transição técnica | F | TR, requisitos de continuidade/transição | mesmo URL de E007 | Alta; não identifica especificamente a URA |
| E011 | Portal de Demandas/SIRCA é interface formal MTE–CAIXA com perfis Técnico/Gestor | F | TR 5.3.22.1–5.3.22.5 | mesmo URL de E007 | Alta; não é portal do cidadão |
| E012 | Existem arquivos de pagamentos, retornos, rejeições, atualização de base e baixa | F | TR 5.3.8.17–19 e 5.3.20–21 | mesmo URL de E007 | Alta |
| E013 | Parcela enviada para crédito em outra instituição é considerada efetivamente paga contratualmente | F | TR 5.3.8.9 | mesmo URL de E007 | Alta; conceito contratual não equivale necessariamente à percepção do crédito |
| E014 | CAIXA é agente pagador das modalidades do Seguro-Desemprego | F | Res. 957, art. 64 §1º | <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf> | Alta |
| E015 | Habilitação é aferida automaticamente com dados de CNIS, FGTS/GFIP, eSocial etc.; inconsistência admite revisão | F | Res. 957, art. 4º §§1º–2º | mesmo URL de E014 | Alta |
| E016 | Dataprev é responsável pelo sistema que analisa requisitos do benefício | F | página institucional Seguro-Desemprego | <https://dataprev.gov.br/solucoes/casos-de-sucesso/seguro-desemprego> | Alta |
| E017 | 158 atende Seguro-Desemprego; funcionamento divulgado seg.–sáb. 7h–22h | F | MTE, Central Alô Trabalho | <https://www.gov.br/trabalho-e-emprego/pt-br/noticias-e-conteudo/2023/marco/central-alo-trabalho-158> | Alta |
| E018 | TED 7AAGCV/2026: contact center MTE executado pelo INSS, 60 meses | F | página de TEDs, instrumento assinado em 14/08/2026 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/convenios-e-transferencias/termos-de-execucao-descentralizada> | Alta |
| E019 | TCU encontrou problemas de clareza, responsividade, resolutividade e encaminhamento entre canais | F | Acórdão 1621/2026, achados 2.1.x e notícia oficial | <https://pesquisa.apps.tcu.gov.br/documento/acordao-completo/%2A/NUMACORDAO%253A1621%2520ANOACORDAO%253A2026/DTRELEVANCIA%2520desc%252C%2520NUMACORDAOINT%2520desc%252C%2520COPIACOLEGIADO%2520desc/0> | Alta; auditoria focou serviço digital, não só URA CAIXA |
| E020 | TCU determinou integração do Seguro-Desemprego ao eSocial para eliminar entrada duplicada | F | Acórdão, item 9.1 | mesmo URL de E019 | Alta |
| E021 | TCU registrou que “paga” pode constar antes de o crédito se concretizar | F | Acórdão, achado sobre notificações/integração CAIXA, §114 na versão pesquisável | mesmo URL de E019 | Alta |
| E022 | TCU recomendou/mandou monitorar indicadores de atendimento, incluindo espera e abandono | F | Acórdão, itens 9.2.6/9.2.8 | mesmo URL de E019 | Alta |
| E023 | MTE mantém canais digital, 158 e presencial para o serviço | F | Carta de Serviços, atualizada em 25/09/2026 | <https://www.gov.br/pt-br/servicos/solicitar-o-seguro-desemprego> | Alta |
| E024 | CAIXA oferece canal para pessoas surdas/deficiência auditiva e Libras | F | CAIXA Acessibilidade/Libras | <https://www.caixa.gov.br/atendimento/libras/Paginas/default.aspx> | Alta; equivalência integral com URA Seguro-Desemprego não demonstrada |
| E025 | Lei 13.460 rege direitos do usuário, Carta de Serviços, qualidade e avaliação | F | Lei 13.460/2017 | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/lei/l13460.htm> | Alta |
| E026 | Lei de Governo Digital estabelece princípios de serviços digitais, interoperabilidade e simplificação | F | Lei 14.129/2021 | <https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2021/lei/l14129.htm> | Alta |
| E027 | LGPD aplica-se ao tratamento de dados; contrato 07/2026 contém cláusula correspondente | F | Lei 13.709; TR 5.3.24 | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm>; <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/pca/072026completo.pdf> | Alta |
| E028 | TED 01/2020 registra indicadores históricos do 158, inclusive URA, humano e abandono | F | Tabela 02, dados 2017–2019 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/convenios-e-transferencias/termos-de-execucao-descentralizada/termo_de_execucao_descentralizada___ted_no_01_2020.pdf> | Alta, mas histórica |
| E029 | Árvore vigente da URA de Seguro-Desemprego não foi localizada publicamente | L | pesquisa em páginas CAIXA, FAQ, contrato e documentos MTE | E004, E005, E006, E007 | Média-alta; ausência pública ≠ inexistência |
| E030 | Protocolo compartilhado CAIXA–MTE–158–Sine acessível ao cidadão não foi localizado | L | contratos, TCU e Cartas de Serviço | E011, E019, E023 | Média |
| E031 | Retirada do item tarifário URA em 2026 representa mudança de estrutura remuneratória, não prova extinção | I | comparação E006–E010 | URLs de E006/E007 | Alta para a inferência |
| E032 | Um episódio pode atravessar habilitação e pagamento sem que a fronteira institucional seja clara ao cidadão | I | E014–E016, E019–E021 | URLs respectivas | Alta |
| E033 | Primeira parcela do trabalhador formal: 30 dias do requerimento; seguintes, intervalos de 30 dias | F | Res. 957, art. 12 | <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf> | Alta |
| E034 | Trabalhador formal pode requerer do 7º ao 120º dia após a dispensa | F | Res. 957, art. 41 | mesmo URL de E033 | Alta |
| E035 | Parcela fica disponível 67 dias, depois retorna ao FAT; reemissão possível em até dois anos | F | Res. 957, art. 21 caput e §2º | mesmo URL de E033 | Alta |
| E036 | Documento do Requerimento, recebido do empregador, e CPF são elementos documentais da solicitação | F | Carta de Serviços, etapa “Solicitar” | <https://www.gov.br/pt-br/servicos/solicitar-o-seguro-desemprego> | Alta |
| E037 | Cartão do Cidadão dá acesso a benefícios quando não há recebimento em conta; Senha Cidadão habilita saque | F | CAIXA, Cartão do Cidadão | <https://www.caixa.gov.br/servicos/cartao-cidadao/Paginas/default.aspx> | Alta |
| E038 | Contrato 07/2026 prevê pagamento em canais por cartão e senha, biometria, documentos, plataformas digitais ou saque sem cartão | F | TR 5.3.8.12–14 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/pca/072026completo.pdf> | Alta |
| E039 | CAIXA divulga SAC 0800 726 0101 e Ouvidoria 0800 725 7474; Ouvidoria é para reclamações não solucionadas | F | página Telefones/Atendimento | <https://www.caixa.gov.br/atendimento/telefones-app/Paginas/default.aspx> | Alta |
| E040 | CPF é suficiente/substitutivo para identificação no Executivo federal; Lei 14.534 reforça CPF como número único/suficiente | F | Decreto 9.094/2017, art. 5º-A; Lei 14.534/2023, arts. 1º, 5º e 9º | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/decreto/d9094.htm>; <https://www.planalto.gov.br/ccivil_03/_ato2023-2026/2023/lei/l14534.htm> | Alta; incidência concreta sobre autenticação da URA precisa ser testada |
| E041 | 158 fez 1.726.914 atendimentos no 1º semestre de 2025; 23% sobre Seguro-Desemprego | F | notícia MTE de 05/08/2025 | <https://www.gov.br/trabalho-e-emprego/pt-br/noticias-e-conteudo/2025/agosto/central-201calo-trabalho201d-mais-de-1-7-milhao-de-atendimentos-no-primeiro-semestre-de-2025> | Alta; não mede URA CAIXA |
| E042 | FAQ atual da CAIXA lista 0800 726 0207 para **acompanhar** parcela, não no bloco “Onde requerer?” | F | FAQ vigente em 25/11/2026 | <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx> | Alta; contraria premissa da Falha 5 |
| E043 | Resolução vigente e Carta MTE apontam requerimento digital ou presencial; 0800 CAIXA não está previsto como meio de requerimento | F/D | Res. 957 art. 5º; Carta de Serviços | <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf>; <https://www.gov.br/pt-br/servicos/solicitar-o-seguro-desemprego> | Alta |
| E044 | Página atual do Cartão Cidadão remete emissão de segunda via e criação de senha ao atendimento 111, não comprova essas funções no 0800 726 0207 | F | CAIXA, Cartão Cidadão/Senha | <https://www.caixa.gov.br/servicos/cartao-cidadao/Paginas/default.aspx> | Alta; funções específicas do 0800 permanecem L |
| E045 | Expressão “síndrome do balcão” não foi localizada no Acórdão integral pesquisável nem na notícia oficial | L/correção de atribuição | busca textual no Acórdão e notícia | E019 | Média-alta; não prova que expressão nunca tenha sido usada pelo TCU em outro documento |
| E046 | TCU descreve trabalhadores encaminhados de um lugar a outro sem resolver pendências | F | notícia oficial sobre Acórdão 1621/2026 | <https://portal.tcu.gov.br/imprensa/noticias/tribunal-avalia-servico-digital-de-seguro-desemprego-para-trabalhadores-formais> | Alta |
| E047 | Contrato atual prevê bloqueio preventivo de cartões/senhas e atendimento ao beneficiário bloqueado | F | TR 5.3.23.1–5.3.23.5 | <https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/licitacoes-e-contratos/pca/072026completo.pdf> | Alta; não demonstra que desbloqueio ocorra pela URA |
| E048 | CAIXA divulga formas de recebimento: conta, Caixa Tem, cartão/senha, biometria e agência | F | FAQ Seguro-Desemprego | <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx> | Alta |
| E049 | Lei Brasileira de Inclusão exige acessibilidade e igualdade de acesso | F | Lei 13.146/2015 | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2015/lei/l13146.htm> | Alta |

## Operação AS-IS nos onze eixos

### Jornada na perspectiva do cidadão

O “antes da ligação” pode agora ser descrito com evidência mais precisa, sem transformar essa sequência em jornada única obrigatória. Para o trabalhador formal, existe uma linha temporal documental possível: **dispensa sem justa causa → recebimento do documento de Requerimento → janela de requerimento entre o 7º e o 120º dia → requerimento → expectativa regulatória de primeira parcela em 30 dias → acompanhamento em canal digital ou telefônico → eventual procura da CAIXA quando a parcela não aparece ou quando há dúvida sobre pagamento** [E033–E036]. A FAQ da CAIXA possui uma pergunta específica sobre requerimento feito há mais de 30 dias sem liberação, confirmando que esse cenário é previsto pelo prestador [E005, E033].

Outros gatilhos documentados permanecem: dúvida sobre calendário; parcela indicada como paga sem crédito percebido; dificuldade relacionada à concessão; inconsistência cadastral; pagamento rejeitado; impossibilidade de uso de conta informada; bloqueio; dúvida sobre canal de saque; ou informação insuficiente nos canais digitais [E019–E021, E047–E048]. Não há base para afirmar qual desses gatilhos é estatisticamente predominante na URA CAIXA.

Durante a ligação, o cidadão disca 0800 726 0207 e entra em um canal com atendimento eletrônico e humano divulgados [E004]. A existência de atendimento eletrônico é F, mas a sequência de menus, opções, autenticação, repetição, retorno ao menu, transbordo e geração de protocolo específicos do Seguro-Desemprego permanecem L [E029]. A pesquisa não atribui números de menu nem scripts.

Depois da ligação, quatro encerramentos continuam metodologicamente distintos: **resolução informacional**, quando o cidadão apenas precisava saber uma data ou status; **resolução operacional**, quando o problema que impedia o pagamento é efetivamente corrigido; **encaminhamento**, quando o cidadão é orientado a procurar MTE, 158, canal digital, agência, SAC, Ouvidoria ou atendimento presencial; e **encerramento sem resolução**, inclusive recontato ou desistência. O TCU fornece evidência de encaminhamentos sucessivos e baixa resolutividade no ecossistema do serviço [E019, E046].

Há ainda um relógio operacional após a disponibilização: se a parcela permanecer disponível para saque por 67 dias, o agente pagador deve devolver o recurso ao FAT; eventual reemissão passa a depender de solicitação do beneficiário ou decisão judicial, dentro do prazo normativo [E035]. Esse prazo deve permanecer visível na futura discussão do blueprint, sem ser automaticamente classificado como falha em todos os casos.

### Evidências físicas e digitais

Além do número de telefone, áudios e aplicativos já inventariados na v1, a v2 incorpora três elementos omitidos: o **Documento do Requerimento**, o **CPF** e, em episódios de saque por canais físicos, o **Cartão do Cidadão/Senha Cidadão** [E036–E038]. O cartão não é necessário para todos os beneficiários: a própria CAIXA informa que ele se destina principalmente a quem possui benefício social ou trabalhista e não o recebe diretamente em conta [E037].

A existência do Cartão e da Senha altera a análise de exceções: o contrato atual admite pagamento mediante cartão e senha e também documenta bloqueios preventivos desses meios por indícios de irregularidade [E038, E047]. Contudo, a auditoria sugeriu que solicitação, desbloqueio e orientação de senha ocorreriam no próprio 0800 726 0207. A fonte primária atual localizada não sustenta essa afirmação: a página oficial do Cartão do Cidadão indica **111** para segunda via e para procedimento de criação de Senha em lotérica [E044]. Portanto, esses subprocessos não são atribuídos à URA investigada.

### Frontstage

O frontstage confirmado compreende o atendimento eletrônico e humano do CAIXA Cidadão, interfaces digitais CAIXA e MTE, atendimento 158, agências, Sine/SRTE e canais acessíveis. A v2 acrescenta **SAC CAIXA** e **Ouvidoria CAIXA** como frontstages possíveis do episódio [E039]. O SAC recebe reclamações, sugestões, elogios, cancelamentos e informações; a Ouvidoria é divulgada para reclamações não solucionadas. Não há evidência de que a URA transfira automaticamente a chamada, o histórico ou o protocolo a esses canais; por isso, são caminhos potenciais de escalonamento do episódio, não “transbordos” comprovados.

A Falha 5 da auditoria não foi confirmada. Na FAQ CAIXA vigente em 25 de novembro de 2026, o bloco **“Onde requerer?”** lista Portal Gov.br, CTPS Digital e atendimento presencial nas Superintendências após agendamento pelo 158. O 0800 726 0207 aparece posteriormente no bloco de **acompanhamento da situação da parcela** [E042]. A Resolução 957 e a Carta do MTE também não estabelecem a URA CAIXA como canal de requerimento [E043]. Assim, o recorte da v1 — URA como canal de consulta/acompanhamento de parcelas e pagamentos — é preservado.

### Backstage

Permanece documentado o seguinte backstage de pagamento, sem inferir integração direta com a URA:

MTE/Dataprev processam elegibilidade e status a partir de bases oficiais [E015–E016]; parcelas aptas entram nos processos de pagamento; o contrato define prioridade entre conta indicada, contas CAIXA, Poupança Social Digital e canais físicos [E007, E012, E038]; a CAIXA envia diariamente à Dataprev/órgão contratante arquivos de movimento liquidado e recebe relatórios de processamento e registros rejeitados [E012]; os retornos alimentam atualização da base e baixa [E012]; o Portal de Demandas/SIRCA suporta comunicação institucional [E011].

A v2 acrescenta explicitamente o processo de **devolução ao FAT após 67 dias** [E035] e os processos de **bloqueio preventivo de cartão/senha e atendimento a beneficiários bloqueados** [E047]. Nenhuma dessas evidências demonstra, porém, qual dado aparece para a URA ou para o atendente humano.

O ponto mais importante para o blueprint continua sendo a separação entre eventos internos e percepção externa. O contrato pode considerar a parcela “efetivamente paga” quando enviada para crédito em outra instituição [E013], enquanto o TCU registrou que o sistema do Seguro-Desemprego pode apresentar “paga” mesmo antes de o crédito se concretizar [E021]. Assim, “paga” não deve ser usada no futuro blueprint como sinônimo automático de “dinheiro disponível e percebido pelo trabalhador”.

### Processos de suporte

São processos de suporte confirmados: infraestrutura de atendimento telefônico da CAIXA, gestão contratual MTE–CAIXA, mecanismos de proteção de dados, Portal de Demandas, contact center MTE–INSS, gestão de acessibilidade e mecanismos de fiscalização contratual [E004, E007, E011, E018, E024, E027].

A tecnologia, fornecedor, arquitetura de URA, dimensionamento, treinamento, qualidade, roteamento, filas, scripts e monitoramento específico do Seguro-Desemprego na CAIXA não foram localizados publicamente. Continuam sendo lacunas, não inferências.

### Linhas e interfaces

A futura **linha de interação** passará por eventos como discagem, navegação da URA, conversa com humano, uso de aplicativo, contato com 158, SAC/Ouvidoria ou comparecimento presencial. A **linha de visibilidade** deverá separar o que o cidadão ouve ou vê dos processos de habilitação, processamento de arquivos, retorno, rejeição, baixa, SIRCA e devolução ao FAT. A **linha de interação interna** deverá representar dependências entre atendimento, bases, pagamento, administração contratual e interfaces MTE–CAIXA.

Fronteiras organizacionais não equivalem automaticamente a essas linhas. Uma passagem CAIXA→MTE pode ser simultaneamente mudança institucional e novo frontstage, enquanto um arquivo CAIXA→Dataprev é um fluxo backstage sem interação do cidadão.

### Fluxos de informação, decisão e responsabilidade

O fluxo de **dados** inclui requisitos de habilitação, arquivos de parcelas, retorno de pagamentos e registros rejeitados. O fluxo de **decisão** inclui habilitação, recurso, bloqueios e correções. O fluxo **financeiro** envolve FAT, CAIXA, conta indicada, outras instituições e canais de saque. O fluxo de **comunicação ao cidadão** ocorre por plataformas MTE, CAIXA, URA, atendimento humano, 158 e presencial.

A evidência não demonstra que todos esses fluxos compartilhem um identificador de caso ou histórico. O SIRCA prova que existe uma interface formal MTE–CAIXA [E011], mas seus perfis são Técnico e Gestor e o documento não o configura como protocolo acessível ao beneficiário.

Não foi localizado um ator formalmente designado para **gerenciar o episódio completo do cidadão de ponta a ponta** atravessando CAIXA, MTE, Dataprev, 158 e Sine. A classificação permanece **L**, e não “F — não existe”.

## Inventários e matrizes operacionais

### Inventário de acontecimentos da jornada

A correção da Falha 11 preserva o ID J11, mas muda seu conteúdo para um acontecimento perceptível pelo cidadão. O processamento financeiro continua representado em AO05–AO08.

| ID | Acontecimento ou atividade observada | Evento desencadeador | Ação do cidadão | Ator/sistema | Canal | Resultado possível | Evidência | Classe |
|---|---|---|---|---|---|---|---|---|
| J00A | Recebe documento de Requerimento após dispensa | dispensa sem justa causa | guarda/consulta documento | empregador/cidadão | físico/digital | insumo para requerer | E036 | F |
| J00B | Entra na janela de requerimento | 7º–120º dia pós-dispensa | requer benefício | MTE/gov.br/Sine/SRTE | digital/presencial | requerimento registrado | E034, E043 | F |
| J00C | Aguarda marco da primeira parcela | requerimento | acompanha situação | cidadão/MTE | digital | expectativa de 30 dias | E033 | F |
| J01 | Percebe necessidade de consultar parcela | prazo, dúvida, status ou crédito | procura canal | cidadão | multicanal | busca de informação | E005, E021, E033 | F/H |
| J02 | Localiza CAIXA Cidadão | busca de canal CAIXA | obtém 0800 | CAIXA | web | número identificado | E004–E005 | F |
| J03 | Inicia ligação | decisão de usar telefone | disca 0800 726 0207 | CAIXA | telefone | entrada no canal | E004 | F |
| J04 | Interage com atendimento eletrônico | chamada conectada | responde/seleciona opções | URA | telefone | consulta automatizada | E004 | F; detalhes L |
| J05 | Eventualmente chega a humano CAIXA | critério não público | conversa com atendente | CAIXA | telefone | orientação/atendimento | E004 | F/H |
| J06 | Recebe informação sobre parcela | consulta | escuta resposta | CAIXA | telefone | resolução informacional possível | E005 | F/I |
| J07 | Demanda é reconhecida como concessão/valor | causa fora do pagamento | procura MTE | MTE/158/digital | múltiplo | novo contato | E005, E017 | F |
| J08 | Consulta status digital | busca complementar | abre CTPS/portal | MTE/Dataprev | digital | visualiza status | E015–E016, E023 | F |
| J09 | Divergência persiste | informação não resolve | recontata/outro canal | vários | múltiplo | retrabalho/encaminhamento sucessivo | E019–E021, E046 | F |
| J10 | Busca atendimento presencial | necessidade não resolvida | agenda/comparece | Sine/SRTE/MTE/CAIXA | presencial | análise/orientação | E023, E048 | F |
| J11 | **Aguarda e verifica se o crédito/saque se tornou efetivamente disponível** | parcela prevista/processada | consulta app/extrato ou tenta receber | cidadão + instituição financeira | digital/financeiro/físico | crédito percebido ou divergência | E013, E021, E048 | F/I |
| J12 | Episódio se encerra | solução, encaminhamento, desistência ou ausência de nova ação observável | deixa de contatar ou conclui | vários | vários | resolvido ou não | E019, E030 | I/H |
| J13 | Tenta receber por canal físico, quando aplicável | parcela disponível sem crédito em conta | usa cartão/senha, biometria ou documento | CAIXA/Lotérica/Correspondente | físico | saque ou dificuldade | E037–E038, E048 | F |
| J14 | Escalona reclamação à CAIXA | problema não resolvido | contata SAC e, se não solucionado, pode procurar Ouvidoria | CAIXA | telefone | reclamação/novo atendimento | E039 | F |
| J15 | Parcela excede prazo de 67 dias sem saque | disponibilidade expira | pode solicitar reemissão | CAIXA/MTE | administrativo | devolução ao FAT e possível reemissão | E035 | F |

### Inventário de evidências físicas e digitais

| ID | Evidência | Emissor | Canal/momento | Conteúdo/finalidade | Fonte | Limitação |
|---|---|---|---|---|---|---|
| ED01 | 0800 726 0207 | CAIXA | pré/durante | acesso CAIXA Cidadão | E004–E005 | não revela árvore |
| ED02 | áudio/menu da URA | CAIXA | durante | navegação | E004 | conteúdo específico L |
| ED03 | página/FAQ Seguro-Desemprego | CAIXA | antes/depois | canais, prazos, pagamento | E005, E033, E035 | divulgação ≠ execução |
| ED04 | App Benefícios Sociais | CAIXA | antes/depois | situação/calendário | E005 | telas específicas não inventariadas |
| ED05 | CAIXA Tem | CAIXA | depois | consulta/crédito em conta digital | E048 | aplicável conforme modalidade de pagamento |
| ED06 | CTPS Digital | MTE | antes/depois | requerimento/status | E023 | não é canal CAIXA |
| ED07 | Portal gov.br/Emprega Brasil | MTE | antes/depois | requerimento/status/recurso | E023 | não é canal CAIXA |
| ED08 | extrato/saldo bancário | instituição financeira | depois | evidência percebida de crédito | E013, E021 | formato varia |
| ED09 | Central 158 | MTE/INSS | encaminhamento | orientação/suporte | E017–E018 | ligação distinta |
| ED10 | Facilita/agendamento | MTE | depois | acesso remoto/presencial | E023 | depende da situação/localidade |
| ED11 | Portal de Demandas/SIRCA | CAIXA/MTE | backstage | comunicação institucional | E011 | **não é evidência visível ao cidadão** |
| ED12 | Documento do Requerimento | empregador/MTE | pré-requerimento | identifica requerimento do benefício | E036 | formato/processo pode ser digital |
| ED13 | CPF | Estado/cidadão | identificação | identificador oficial | E036, E040 | autenticação real da URA L |
| ED14 | Cartão do Cidadão | CAIXA | recebimento físico | meio de acesso a benefício quando aplicável | E037–E038 | não é necessário em todos os episódios |
| ED15 | Senha Cidadão | CAIXA | recebimento físico | habilita uso do cartão | E037 | procedimento não pertence comprovadamente à URA 0800 |
| ED16 | SAC 0800 726 0101 | CAIXA | escalonamento | reclamação/informação | E039 | transferência automática de contexto L |
| ED17 | Ouvidoria 0800 725 7474 | CAIXA | pós-reclamação não resolvida | escalonamento | E039 | integração com URA L |

### Inventário de atividades operacionais

| ID | Atividade | Executor | Sistema | Visibilidade | Entrada → processamento → saída | Dependências | Evidência |
|---|---|---|---|---|---|---|---|
| AO01 | Receber chamada | CAIXA | telefonia | frontstage | chamada → conexão | infraestrutura | E004 |
| AO02 | Atendimento eletrônico | CAIXA | URA tecnicamente não identificada | frontstage | seleção/dados → resposta | integração L | E004, E029 |
| AO03 | Atendimento humano | CAIXA | não identificado | frontstage | relato → consulta/orientação | sistemas L | E004 |
| AO04 | Analisar habilitação | MTE/Dataprev | Sistema Seguro-Desemprego | backstage | bases → regras → status | CNIS/eSocial etc. | E015–E016 |
| AO05 | Gerar/receber arquivos de pagamento | MTE/CAIXA | layouts contratuais | backstage | lotes → processamento | sistemas institucionais | E012 |
| AO06 | Efetuar pagamento | CAIXA | infraestrutura bancária | backstage; resultado visível | parcela → crédito/saque | rede financeira | E013–E014, E038 |
| AO07 | Enviar movimento liquidado | CAIXA | arquivos | backstage | pagamentos → retorno diário | Dataprev/MTE | E012 |
| AO08 | Tratar rejeição | MTE/CAIXA | arquivos | backstage | rejeição → ajuste | origem do erro | E012 |
| AO09 | Registrar demanda institucional | MTE/CAIXA | SIRCA | backstage/suporte | demanda → tramitação | perfis autorizados | E011 |
| AO10 | Prestar orientação 158 | INSS no arranjo MTE | contact center | frontstage | pergunta → orientação | bases/material | E017–E018 |
| AO11 | Fiscalizar contrato | MTE | gestão contratual | suporte | execução → ateste/correção | documentação | E007 |
| AO12 | Prover acessibilidade | CAIXA | Libras/central acessível | frontstage/suporte | necessidade → atendimento acessível | canal alternativo | E024, E049 |
| AO13 | Devolver parcela não sacada ao FAT após prazo | CAIXA/agente pagador | financeiro | backstage | 67 dias → devolução | regra CODEFAT | E035 |
| AO14 | Viabilizar pagamento com cartão/senha ou alternativas | CAIXA | canais de pagamento | frontstage/backstage | parcela → autenticação → saque | cartão/senha/biometria/documento | E037–E038 |
| AO15 | Tratar bloqueios de cartões/senhas vinculados às parcelas | CAIXA/MTE | mecanismos internos | backstage + atendimento visível | indício → bloqueio/comunicação/atendimento | regras contratuais | E047 |
| AO16 | Receber reclamação/escalonamento | SAC/Ouvidoria CAIXA | contact center | frontstage | reclamação → tratamento | histórico compartilhado L | E039 |

### Matriz de interfaces e transferências

| ID | Origem → destino | Desencadeador | Tipo | Informação/demanda | Responsabilidade | Confirmação | Evidência |
|---|---|---|---|---|---|---|---|
| IT01 | cidadão → URA CAIXA | consulta | interação | identificação/demanda | CAIXA responde dentro do escopo | resposta de voz | E004–E005 |
| IT02 | URA → humano CAIXA | critério desconhecido | possível transbordo | contexto | L | L | E004, E029 |
| IT03 | CAIXA → cidadão → MTE | dúvida de concessão/valor | orientação para outro canal | cidadão transporta demanda | cidadão atua como ponte | preservação de contexto não demonstrada | E005 |
| IT04 | cidadão → 158 | procura MTE | nova interação | dúvida Seguro-Desemprego | 158 assume atendimento | chamada | E017 |
| IT05 | MTE/Dataprev → CAIXA | parcela apta/arquivo | dados | registros | execução do pagamento | mecanismos contratuais | E012 |
| IT06 | CAIXA → MTE/Dataprev | pagamento/rejeição | dados | movimento/retorno | atualização/controle | arquivo retorno | E012 |
| IT07 | MTE ↔ CAIXA | demanda administrativa | institucional | documentos/demandas | conforme natureza | SIRCA/ofício | E011 |
| IT08 | digital → presencial | caso não solucionado remotamente | encaminhamento | contexto | unidade presencial | histórico compartilhado L | E023, E030 |
| IT09 | vários canais ↔ cidadão | orientação insuficiente | recontato | informação repetida | fragmentada | variável | E019, E046 |
| IT10 | cidadão → SAC CAIXA | reclamação/informação | nova interação | problema relatado | SAC trata demanda | registro interno provável; formato L | E039 |
| IT11 | cidadão → Ouvidoria CAIXA | reclamação não solucionada | escalonamento | demanda anterior | Ouvidoria assume tratamento | compartilhamento com URA L | E039 |
| IT12 | CAIXA → FAT | parcela não sacada por 67 dias | fluxo financeiro | valor não sacado | recurso retorna ao Fundo | obrigação normativa | E035 |
| IT13 | cidadão → canal físico CAIXA | necessidade de saque | interação | cartão/senha/biometria/documento | canal realiza autenticação/pagamento | transação | E038 |

O ponto metodológico da v1 continua válido: **fluxo de dados entre instituições não é o mesmo que transferência de atendimento**. Uma orientação para que o cidadão telefone ao 158 ou procure uma SRTE também não é transferência de chamada nem continuidade de caso.

## Falhas, marco normativo, indicadores e exceções

### Inventário de possíveis pontos de falha

| ID | Atividade afetada | Falha/dificuldade | Manifestação ao cidadão | Causa documentada ou hipótese | Consequência | Tratamento conhecido | Frequência | Evidência / classe |
|---|---|---|---|---|---|---|---|---|
| PF01 | escolha de canal | atribuições CAIXA/MTE pouco transparentes | procura canal sem competência para corrigir causa | fragmentação institucional; I | recontato | orientação entre canais | não quantificada | E019, E032 / I |
| PF02 | atendimento eletrônico | árvore/menu não documentados publicamente | dificuldade não mensurável | L | blueprint incompleto | teste/manual autorizado | desconhecida | E029 / L |
| PF03 | canais de suporte | baixa responsividade | espera/chamada sem atendimento | capacidade/demanda | repetição/abandono | medidas TCU | TCU documenta problema no ecossistema; taxa URA CAIXA L | E019, E022 / F |
| PF04 | orientação | informação insuficiente/genérica | cidadão não sabe como resolver | falta de clareza/base uniforme | múltiplos contatos | recomendações TCU | recorrência qualitativa | E019, E046 / F |
| PF05 | habilitação | dados inconsistentes | parcela impedida | inconsistência de bases | revisão/recurso | recurso | não quantificada | E015 / F |
| PF06 | dados do empregador | duplicidade eSocial/Empregador Web | erro/atraso/retrabalho | integração incompleta | atraso/processamento | determinação TCU | não quantificada | E020 / F |
| PF07 | status | “paga” sem crédito percebido | trabalhador não encontra valor | retorno CAIXA precede processamento final | novo contato | investigação/contestação | ocorrência documentada; frequência L | E021 / F |
| PF08 | encaminhamento | cidadão carrega contexto entre canais | repete explicações/dados | protocolo compartilhado não comprovado | retrabalho | mecanismo público não localizado | não quantificada | E019, E030 / F+L |
| PF09 | resolução | chamada pode terminar sem solucionar causa | novo contato | atendimento ≠ resolução do episódio | peregrinação | L para URA | L | E019 / I |
| PF10 | acessibilidade | equivalência funcional do canal acessível não demonstrada | possível barreira para executar mesma consulta | documentação específica insuficiente | uso de alternativa | Libras/central acessível | L | E024 / L/H |
| PF11 | pagamento interbancário | “efetivamente paga” contratualmente antes de percepção do crédito | status e saldo não coincidem | conceito contratual + processamento de outra IF | recontato | retorno/processamento | L | E013, E021 / I |
| PF12 | recurso/atendimento | informação fragmentada e sucessivos encaminhamentos | alternância de canais | falta de integração/base uniforme | prolongamento do episódio | ações TCU | documentado qualitativamente | E019, E046 / F |
| PF13 | prazo de saque | parcela permanece sem saque até 67 dias | valor deixa de ficar disponível imediatamente | prazo normativo | devolução ao FAT; necessidade de reemissão | reemissão até dois anos, se cabível | frequência L | E035 / F |
| PF14 | meio de saque | cartão/senha indisponível, bloqueado ou inadequado ao episódio | impossibilidade/dificuldade de sacar por esse meio | bloqueio ou problema operacional; parte H | uso de outro meio/atendimento | contrato prevê alternativas e atendimento a bloqueados | frequência L | E037, E038, E047 / F+H |
| PF15 | identificação entre canais | exigência eventual de identificador adicional/repetição | cidadão repete dados | lógica da URA L | atrito/retrabalho | CPF é referência normativa | L | E040 + L02 / H |
| PF16 | escalonamento | reclamação não preserva contexto da URA | cidadão reexplica caso | integração de histórico não localizada | retrabalho | SAC/Ouvidoria disponíveis | L | E039, E030 / H/L |

PF13 não deve ser redigido como “perda definitiva da parcela”. A norma prevê devolução ao FAT e possibilidade de reemissão [E035].

PF14 também não deve ser generalizado: Cartão do Cidadão e Senha são relevantes apenas para episódios em que o recebimento utilize esse meio.

### Matriz normativa e contratual

| Instrumento | Dispositivo | Obrigação/regra | Responsável | Relação com o serviço | Evidência de execução | Divergência/lacuna | Fonte |
|---|---|---|---|---|---|---|---|
| Lei 7.998/1990 | estrutura do Programa | disciplina benefício/FAT | União/CODEFAT | base legal | Resolução e contratos | — | <https://www.planalto.gov.br/ccivil_03/leis/l7998compilado.htm> |
| Res. 957/2022 | art. 4º | aferição automática por bases oficiais; revisão de inconsistência | MTE/sistema | habilitação | Dataprev opera sistema | integração criticada pelo TCU | E015–E016 |
| Res. 957/2022 | art. 5º | requerimento digital; presencial se impossível | MTE/Sine/SRTE | antes da URA | Carta de Serviço | não contempla URA CAIXA como meio de requerimento | E043 |
| Res. 957/2022 | art. 12 | primeira parcela em 30 dias; seguintes a cada 30 dias | MTE/sistema | gatilho temporal | FAQ CAIXA reflete prazo | frequência do gatilho L | E033 |
| Res. 957/2022 | art. 20 | pagamento em conta e alternativas | agente pagador | pagamento | contrato 07/2026 | — | E038 |
| Res. 957/2022 | art. 21 | 67 dias; devolução ao FAT; reemissão até 2 anos | agente pagador/MTE | prazo crítico | FAQ CAIXA confirma 67 dias | frequência de devoluções L | E035 |
| Res. 957/2022 | art. 41 | requerimento do 7º ao 120º dia | trabalhador/MTE | pré-atendimento | Carta/FAQ | — | E034 |
| Res. 957/2022 | art. 64 §1º | CAIXA agente pagador | CAIXA | papel institucional | contrato 07/2026 | — | E014 |
| Contrato 11/2021 | item 6; PB 7.1.8.20 | URA remunerada e destinada a informar parcelas/pagamentos | CAIXA | histórico do canal | obrigação contratual | execução granular histórica não auditada | E006 |
| Contrato 07/2026 | cláus. 1/5 | remuneração por parcela paga | CAIXA | modelo atual | contrato vigente | URA não individualizada | E007–E008 |
| Contrato 07/2026 | TR 4.6.1.1 | atendimento ao público pode ser serviço acessório subcontratado | CAIXA | suporte | permissão contratual | fornecedor concreto L | E009 |
| Contrato 07/2026 | TR 5.3.8 | ordem e meios de pagamento | CAIXA | backstage/recebimento | obrigação atual | relação com URA L | E013, E038 |
| Contrato 07/2026 | TR 5.3.22 | Portal de Demandas | MTE/CAIXA | interface interna | mecanismo previsto | não acessível ao cidadão | E011 |
| Contrato 07/2026 | TR 5.3.23 | bloqueios e atendimento de beneficiários afetados | CAIXA/MTE | exceção de pagamento | obrigação | canal usado para resolver L | E047 |
| Lei 13.460/2017 | arts. 5º, 7º, 10-A, 23 | direitos do usuário, Carta, identificação e avaliação | Administração/prestadores | experiência | canais e Carta existem | TCU aponta problemas de qualidade | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/lei/l13460.htm> |
| Decreto 9.094/2017 | art. 5º-A | CPF suficiente/substitutivo para diversos identificadores no Executivo federal | órgãos/entidades federais | identificação | CPF usado na Carta | autenticação URA não conhecida | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2017/decreto/d9094.htm> |
| Lei 14.534/2023 | arts. 1º, 5º, 9º | CPF como número único/suficiente; adequação e interoperabilidade | serviços públicos | identificação/once-only | — | eventual exigência adicional na URA precisa ser observada | <https://www.planalto.gov.br/ccivil_03/_ato2023-2026/2023/lei/l14534.htm> |
| Lei 14.129/2021 | princípios e dispositivos de governo digital | simplificação/interoperabilidade/acesso | Administração | serviço multicanal | plataformas digitais | fragmentação observada pelo TCU | <https://www.planalto.gov.br/ccivil_03/_ato2019-2022/2021/lei/l14129.htm> |
| LGPD 13.709/2018 | princípios/deveres | proteção e finalidade dos dados | controlador/operador | autenticação e consultas | contrato incorpora LGPD | dados da URA L | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm> |
| LBI 13.146/2015 | acessibilidade | igualdade de acesso | prestadores | atendimento acessível | CAIXA oferece Libras | equivalência funcional SD L | <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2015/lei/l13146.htm> |
| TED 7AAGCV/2026 | objeto | contact center MTE executado pelo INSS | MTE/INSS | 158 | vigente | indicadores SD detalhados L | E018 |

O Decreto 9.094 e a Lei 14.534 são **régua normativa**, não prova de que a URA esteja em desconformidade. Como os dados de autenticação da URA são desconhecidos, eventual exigência de PIS/NIS além do CPF deve permanecer H/L até observação autorizada ou documentação da CAIXA.

### Inventário de indicadores

| Indicador | Definição/valor | Período | Abrangência | Meta/resultado | Fonte | Limitação |
|---|---|---|---|---|---|---|
| Tarifa URA 11/2021 | R$0,53 por atendimento; 48.974.350 projetados; R$25,956 mi | 60 meses projetados | URA contratada | projeção, não realizado | E006 | histórico |
| Parcela paga 07/2026 | R$2,25; 170.366.759 projetadas; R$383,325 mi | 2026–2031 | pagamento SD | base remuneratória atual | E007 | não mede atendimento |
| Chamadas 158 históricas | 3.993.068 entregues; 1.202.457 URA; 2.479.111 humano; 311.500 abandonadas | 2019 | 158 agregada | histórico | E028 | não usar como indicador atual nem URA CAIXA |
| TMA histórico | aprox. 5m46s no cenário do TED | período histórico | contact center Trabalho | histórico | E028 | obsoleto para AS-IS 2026 |
| Atendimentos 158 | 1.726.914 | 1º semestre 2025 | Central Alô Trabalho | observado | E041 | não é URA CAIXA |
| Participação Seguro-Desemprego no 158 | 23% dos atendimentos; ≈397 mil por cálculo | 1º semestre 2025 | 158 | observado + cálculo I | E041 | percentual arredondado; número absoluto inferido |
| Espera/abandono atuais URA CAIXA | não localizado | 2025–2026 | URA CAIXA SD | L | E022 | TCU recomenda monitoramento, mas não fornece série da URA |
| FCR/resolução primeiro contato | não localizado | 2025–2026 | URA CAIXA SD | L | E019 | baixa resolutividade qualitativa não é taxa |
| Recontato | não localizado | 2025–2026 | URA CAIXA SD | L | E019 | qualitativo |
| Disponibilidade técnica | não localizada | 2025–2026 | CAIXA SD | L | E004 | 24x7 é horário de oferta, não disponibilidade |
| Satisfação específica | não localizada | 2025–2026 | URA CAIXA SD | L | E022 | não inferir ausência de medição interna |
| Reclamações específicas | série não localizada | 2025–2026 | URA CAIXA SD | L | E019, E039 | existência de SAC/Ouvidoria não fornece série SD |

A atualização de 2025 não elimina a utilidade histórica de E028: a série 2017–2019 continua útil para demonstrar que o 158 já distinguia “atendidas URA”, “atendimento humano” e “abandonadas”. Contudo, não é aceitável usá-la como desempenho de 2025–2026.

### Variações e fluxos de exceção

| Situação | Condição diferenciadora | Atores documentados/prováveis | Resultado possível | Evidência |
|---|---|---|---|---|
| consulta de calendário | benefício sem intercorrência | CAIXA/MTE digital | informação | E005 |
| marco de 30 dias sem liberação | primeira parcela não aparece | cidadão/CAIXA/MTE | consulta/encaminhamento | E033 |
| parcela prevista/liberada | status normal | CAIXA | crédito/saque | E013, E038 |
| “paga” sem crédito percebido | status ≠ experiência | CAIXA/outra IF/MTE | investigação/recontato | E021 |
| pendência de habilitação | requisito/inconsistência | MTE/Dataprev | revisão/recurso | E015–E016 |
| divergência cadastral | base inconsistente | MTE/Dataprev/empregador | correção/reprocessamento | E015, E020 |
| conta indicada inválida | depósito impossível | CAIXA | conta alternativa/canal físico | E038 |
| pagamento a outro banco | conta indicada | CAIXA/outra IF | envio/crédito | E013 |
| saque por cartão/senha | não houve crédito em conta | CAIXA/Lotérica/Correspondente | saque | E037–E038 |
| cartão/senha bloqueados | indício/inconsistência | CAIXA/MTE | atendimento/desbloqueio por mecanismo não totalmente documentado | E047 |
| 67 dias sem saque | parcela expira para saque | CAIXA/FAT/MTE | devolução e eventual reemissão | E035 |
| necessidade MTE | concessão/valor/recurso | cidadão→MTE/158 | orientação/análise | E005, E017 |
| reclamação CAIXA | atendimento não resolve | cidadão→SAC/Ouvidoria | tratamento/escalonamento | E039 |
| atendimento presencial | remoto insuficiente | Sine/SRTE/MTE/CAIXA conforme caso | análise/orientação | E023 |
| necessidade acessível | deficiência auditiva/fala | CAIXA | Libras/central acessível | E024 |
| indisponibilidade técnica | falha de sistema/telefonia | não documentado especificamente | recontato/outro canal | L |
| recurso | decisão contestada | MTE/Dataprev/Sine | análise de recurso | E015, E019 |

## Lacunas, validação dos conhecimentos prévios e revisão adversarial

### Matriz de lacunas e questões de validação

Todos os IDs L01–L18 da v1 foram preservados. A v2 adiciona lacunas específicas decorrentes da auditoria.

| ID | Informação desconhecida | Relevância | Evidências consultadas | Possível fonte | Ator | Impacto |
|---|---|---|---|---|---|---|
| L01 | árvore atual da URA | define ações/esperas | E004–E005, E029 | gravação/teste autorizado/manual | CAIXA | muito alto |
| L02 | dados exigidos/autenticação | interação, CPF, LGPD | E027, E029, E040 | script/manual/teste | CAIXA | alto |
| L03 | sistemas consultados pela URA | backstage real | E011–E016 | arquitetura | CAIXA/MTE | muito alto |
| L04 | transbordo URA→humano e critérios | fronteira frontstage | E004 | operação contact center | CAIXA | alto |
| L05 | preservação de contexto no transbordo | retrabalho | E030 | logs/processos | CAIXA | alto |
| L06 | protocolo gerado na URA | continuidade | E030 | teste/manual | CAIXA | alto |
| L07 | protocolo compartilhado CAIXA–158–Sine | episódio interinstitucional | E019, E030 | acordos/APIs | MTE/CAIXA/INSS | muito alto |
| L08 | capacidade adicional do humano sobre URA | resolutividade | E004 | matriz de acesso | CAIXA | alto |
| L09 | distinção processada/paga/creditada no atendimento | questão central | E013, E021 | regra operacional | CAIXA/MTE | muito alto |
| L10 | uso do SIRCA em caso originado por cidadão | resolução institucional | E011 | procedimento interno | MTE/CAIXA | alto |
| L11 | responsável ponta a ponta | governança | E019, E030 | normativo/processo | MTE/CAIXA | muito alto |
| L12 | indicadores URA SD 2025–2026 | intensidade de falhas | E022, E028, E041 | LAI/relatório operacional | CAIXA/MTE | muito alto |
| L13 | satisfação/FCR/recontato | resolução real | E019 | pesquisas/logs | CAIXA/MTE | alto |
| L14 | equivalência funcional do canal acessível | inclusão | E024 | teste/manual | CAIXA | alto |
| L15 | motivo documental para retirada da tarifa URA em 2026 | evolução contratual | E006–E010 | ETP/proposta/nota técnica | MTE/CAIXA | médio-alto |
| L16 | fornecedor/tecnologia da URA | suporte | E009 | contratos CAIXA | CAIXA | médio |
| L17 | histórico entregue à agência CAIXA | continuidade | E030 | procedimento interno | CAIXA | alto |
| L18 | confirmação ao cidadão após correção interinstitucional | fechamento | E019 | workflow/notificações | MTE/CAIXA | alto |
| L19 | proporção de casos acionados após o marco de 30 dias | representatividade do gatilho | E033 | logs/CRM | CAIXA | médio |
| L20 | quantidade de parcelas devolvidas ao FAT por prazo de 67 dias | intensidade PF13 | E035 | relatórios financeiros/LAI | MTE/CAIXA | alto |
| L21 | uso do Cartão do Cidadão entre beneficiários SD atuais | relevância do fluxo físico | E037–E038 | dados de pagamentos | CAIXA | médio |
| L22 | se problemas de cartão/senha são resolvidos pelo 0800 726 0207 | delimitação da URA | E037, E044, E047 | script/manual | CAIXA | médio |
| L23 | integração de SAC/Ouvidoria com histórico da URA | continuidade | E039 | CRM/procedimento | CAIXA | alto |
| L24 | exigência efetiva de PIS/NIS na autenticação telefônica | conformidade/simplificação | E040 | teste/manual | CAIXA | alto |

As questões de campo mais importantes passam a incluir: qual menu o usuário ouve; quais dados são solicitados; o que significa “paga” na resposta da URA; se existe distinção entre emitida, enviada, liquidada e creditada; se há protocolo; se ele segue para humano, SAC, Ouvidoria ou MTE; como uma parcela devolvida após 67 dias é reemitida na prática; e em quais situações atuais o Cartão do Cidadão é efetivamente necessário.

### Questões críticas transversais

| Questão | Estado da evidência |
|---|---|
| O cidadão distingue habilitação de pagamento? | **I:** não necessariamente; documentos separam competências, TCU registra dificuldade de informação. E019, E032. |
| A URA identifica causa ou apenas status? | **L:** lógica não publicada. |
| Existe transferência URA→humano? | **L:** atendimento humano existe, critério de transbordo não localizado. |
| Humano vê mais informação que a URA? | **L.** |
| CAIXA distingue processada, paga e crédito efetivo? | **F/I:** processos internos distinguem eventos; apresentação ao cidadão pode usar status “paga” antes da percepção do crédito. E012, E013, E021. |
| 158 consegue resolver falha de pagamento CAIXA? | **L:** atende Seguro-Desemprego, mas matriz de competência granular não localizada. |
| Canais compartilham protocolo/histórico? | **L.** |
| SIRCA acompanha problema individual do cidadão? | **L:** é interface institucional, não foi demonstrado como sistema de caso do beneficiário. |
| Cidadão recebe confirmação de resolução? | **L:** TCU identifica deficiência de notificações. |
| Existe coordenador ponta a ponta? | **L:** não localizado. |
| Desempenho é atendimento ou resolução? | **D/L:** contrato antigo remunerava atendimento; atual remunera parcela; FCR específico não localizado. |
| Há alternativa acessível? | **F:** CAIXA possui Libras/canal acessível; **L:** equivalência funcional completa para SD. |
| Quando cidadão atua como intermediário? | **F/I:** quando precisa procurar outro canal sem transferência de contexto comprovada. |
| O 0800 CAIXA permite requerer o benefício? | **F:** não segundo a FAQ CAIXA vigente, Res. 957 e Carta MTE; é comprovado para acompanhamento. E042–E043. |
| A devolução em 67 dias extingue definitivamente o direito à parcela? | **Não. F:** a norma admite reemissão até dois anos nas condições do art. 21 §2º. E035. |

### Validação dos sete conhecimentos prévios

| Conhecimento prévio | Resultado | Evidências | Correções/complementações | Lacuna |
|---|---|---|---|---|
| Contrato 11/2021 remunerava URA para informações sobre parcelas/pagamentos | **Confirmado** | E006 | R$0,53; projeção 48,97 mi; PB 7.1.8.20 explicita finalidade | execução histórica granular |
| Contrato 07/2026 não apresenta item separado URA | **Confirmado** | E007–E010 | remuneração por parcela a R$2,25; atendimento pode ser acessório | razão específica da mudança |
| 158 é operado pelo INSS via TED | **Confirmado e atualizado** | E017–E018 | TED 7AAGCV/2026, 14/08/2026, 60 meses | indicadores operacionais granulares |
| sistema Seguro-Desemprego é operado pela Dataprev | **Confirmado** | E016 | Dataprev declara responsabilidade pela análise dos requisitos | interface com URA |
| Sine e SRTE participam do presencial | **Confirmado** | E023, E043 | Resolução prevê presencial quando digital impossível | distribuição local dos casos |
| TCU 1621/2026 apontou problemas de encaminhamento, duplicidade e atendimento | **Confirmado com correção terminológica** | E019–E022, E046 | “síndrome do balcão” deixa de ser atribuída ao TCU; fenômeno de encaminhamento sucessivo é comprovado | incidência exclusiva na URA CAIXA |
| não havia ator formal identificado para coordenar episódio integral | **Não verificável como inexistência; lacuna mantida** | E011, E019, E030 | SIRCA coordena comunicação institucional, não prova gestão de caso cidadão | confirmar MTE/CAIXA |

### Revisão adversarial da própria v2

A incorporação da auditoria não significa aceitar automaticamente todas as suas premissas. Duas correções são particularmente importantes.

Na **Falha 5**, a auditoria afirma que a FAQ da CAIXA lista o 0800 726 0207 em “Onde requerer?”. A verificação independente em 25 de novembro de 2026 não confirma isso. Na página oficial atual, “Onde requerer?” lista Gov.br, CTPS Digital e unidades das Superintendências; o 0800 aparece em seguida entre os canais para **acompanhar a situação da parcela**. A Resolução consolidada também estabelece requerimento pelo Gov.br/CTPS ou presencial. A v2, portanto, **defende o escopo original da URA** em vez de introduzir uma etapa de requerimento telefônico não demonstrada. URLs: <https://www.caixa.gov.br/beneficios-trabalhador/seguro-desemprego/perguntas-frequentes/paginas/default.aspx>; <https://portalfat.trabalho.gov.br/wp-content/uploads/2026/09/Resolucao-no-957-de-21-de-setembro-de-2022-Revisao-do-SD.pdf>.

Na **Falha 4**, o auditor corretamente identificou a ausência do Cartão do Cidadão e da Senha como evidências relevantes, mas a hipótese de que solicitação/desbloqueio desses instrumentos passe pelo 0800 726 0207 não foi confirmada em fonte primária atual. A página CAIXA vigente indica o **111** para segunda via e para o procedimento relacionado à criação da Senha em lotérica. O Cartão e a Senha foram incorporados ao episódio de recebimento, mas sua administração não foi atribuída à URA investigada. URL: <https://www.caixa.gov.br/servicos/cartao-cidadao/Paginas/default.aspx>.

Na **Falha 3**, a existência do prazo de 67 dias foi confirmada, mas a consequência foi refinada: não há base para dizer simplesmente que o cidadão “perde a parcela”, porque o art. 21 §2º admite reemissão. O risco operacional relevante é expirar a disponibilidade de saque, devolver o recurso ao FAT e impor uma etapa posterior de reemissão.

Na **Falha 10**, a evidência sustenta o fenômeno que a v1 pretendia descrever, mas não a atribuição textual. O TCU afirma que trabalhadores são encaminhados de um lugar a outro sem resolver suas pendências, porém não foi localizada a expressão “síndrome do balcão”. A v2 elimina as aspas e o suposto crédito autoral ao Tribunal.

## Tratamento da auditoria

| Falha | tratamento (a/b/c) | o que mudou |
|---|---|---|
| **Falha 1 — rastreabilidade** | **(a) corrigir** | Todos os E001–E032 foram mantidos e passaram a apontar para URLs públicas reais; as evidências novas E033–E049 também têm URL e localização normativa/contratual sempre que aplicável. Nenhum marcador interno de ferramenta é usado como referência bibliográfica. |
| **Falha 2 — gatilho antes da ligação** | **(a) corrigir** | O “antes” foi reconstruído: dispensa → Requerimento → janela de 7–120 dias → requerimento → primeira parcela em 30 dias → consulta. O marco do 30º dia é tratado como gatilho documentado, mas não como gatilho estatisticamente predominante. Criados J00A–J00C, E033–E034. |
| **Falha 3 — 67 dias/devolução ao FAT** | **(a) corrigir** | Incluídos E035, J15, AO13, IT12, PF13, matriz normativa e variação específica. Corrigida também a formulação da auditoria: após 67 dias há devolução ao FAT, mas pode haver reemissão em até dois anos; não se afirma perda definitiva. |
| **Falha 4 — Cartão do Cidadão/Senha** | **(a) corrigir** | Incluídos ED14–ED15, AO14–AO15, PF14, J13 e E037–E038/E047. A parte não confirmada da auditoria — gestão do cartão/senha pelo 0800 726 0207 — ficou explicitamente em aberto; a página atual aponta 111 para procedimentos de emissão/senha. |
| **Falha 5 — 0800 também seria canal de requerimento** | **(b) defender** | A verificação independente não confirma a premissa da auditoria. A FAQ atual coloca o 0800 em “acompanhar situação da parcela”, não em “Onde requerer?”. Res. 957 e Carta MTE também não o preveem para requerimento. O escopo da v1 como canal de acompanhamento/consulta é preservado; E042–E043 documentam a defesa. |
| **Falha 6 — SAC e Ouvidoria ausentes** | **(a) corrigir** | Adicionados ED16–ED17, AO16, IT10–IT11, J14, PF16 e E039. A v2 não confunde existência desses canais com transferência automática da URA; preservação de contexto permanece L23. |
| **Falha 7 — Decreto 9.094/2017 e once-only** | **(a) corrigir** | Decreto 9.094/2017 e Lei 14.534/2023 foram incorporados à matriz normativa. PF15 e L24 conectam CPF/repetição à autenticação, mas nenhuma desconformidade da URA é afirmada sem conhecer os dados efetivamente pedidos. |
| **Falha 8 — documento de Requerimento omitido** | **(a) corrigir** | Documento de Requerimento e CPF entram como ED12–ED13; E036 documenta a Carta de Serviços; o recebimento do documento aparece em J00A. |
| **Falha 9 — indicador 158 de 2025** | **(a) corrigir** | Adicionado E041 e atualizado o inventário de indicadores com 1.726.914 atendimentos no 1º semestre de 2025 e 23% sobre Seguro-Desemprego. A série 2019 foi preservada, mas apenas como histórico. |
| **Falha 10 — “síndrome do balcão” atribuída ao TCU** | **(a) corrigir** | A expressão foi retirada como citação/denominação do TCU. Mantém-se apenas o fenômeno comprovado de encaminhamento entre lugares/canais sem resolução, com E045–E046 e URL do Acórdão/notícia oficial. |
| **Falha 11 — jornada mistura cidadão e backstage** | **(a) corrigir** | J11 foi preservado como ID, mas reescrito para a experiência observável: “aguarda e verifica se crédito/saque está efetivamente disponível”. Processamento de pagamento fica exclusivamente em AO05–AO08/AO13 e interfaces backstage. |

A v2, portanto, confirma a maior parte das conclusões estruturais da v1 — existência atual do canal telefônico, mudança de remuneração contratual sem prova de extinção da URA, separação habilitação/pagamento, backstage de arquivos e pagamentos, papel da Dataprev, papel do 158 e ausência de evidência pública de gestão de caso ponta a ponta —, mas melhora substancialmente a rastreabilidade, o início da jornada, o tratamento de prazo, os meios físicos de recebimento, os canais de reclamação, a matriz normativa e a separação entre experiência do cidadão e processamento interno. As lacunas essenciais permanecem deliberadamente abertas onde a documentação pública não autoriza conclusão: árvore da URA, autenticação, integração técnica, transbordo, protocolo, compartilhamento de histórico, indicadores específicos da URA e responsável formal pela resolução interinstitucional.