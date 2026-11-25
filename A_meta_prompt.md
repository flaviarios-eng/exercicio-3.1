## Contexto

Sou aluna do mestrado em Ciência de Dados e IA, na disciplina de Transformação Digital do Governo. No exercício anterior, mapeei os atores da jornada do serviço público **Atendimento ao Seguro-Desemprego pela URA (Unidade de Resposta Audível) da Caixa Econômica Federal**: o canal telefônico automatizado de menus de voz que o trabalhador formal usa para consultar a situação de parcelas e pagamentos do benefício. A política é do Ministério do Trabalho e Emprego (MTE), e a CAIXA é o agente pagador e operadora do canal. Agora preciso produzir um **Service Blueprint AS-IS** desse serviço, segundo a metodologia de G. Lynn Shostack: o retrato fiel de como o serviço funciona hoje, com seus pontos de falha à mostra.

Contexto que já tenho (do meu mapa de atores):
- O Contrato MTE–CAIXA nº 11/2021 remunerava a CAIXA por atendimento na URA, para informações sobre parcelas e pagamentos. O contrato atual (nº 07/2026) não tem item de URA separado.
- O MTE opera a Central Alô Trabalho 158, executada pelo INSS por meio de um Termo de Execução Descentralizada.
- O sistema do Seguro-Desemprego é operado pela Dataprev. O Sine (estadual e municipal) e as SRTE atendem presencialmente.
- O TCU (Acórdão 1.621/2026) apontou peregrinação entre canais, duplicidade Empregador Web/eSocial e dificuldades no atendimento.
- Não identifiquei nenhum ator responsável por coordenar o episódio completo de resolução da demanda do cidadão.

## Objetivo

Não quero a pesquisa agora. Quero que você **ELABORE UM PROMPT** para um assistente de deep research investigar **como esse serviço opera hoje**. A pesquisa resultante será a matéria-prima de uma entrevista posterior, na qual eu decidirei as etapas, as camadas e os fail points do blueprint. Por isso, ela precisa ser rica em evidências sobre a operação real, e não genérica.

## O que o prompt deve pedir

O prompt deve pedir uma pesquisa estruturada que sustente um Service Blueprint AS-IS, cobrindo:
1. **Etapas da jornada na ótica do cidadão:** começando antes da ligação (onde o trabalhador está, o que o leva a ligar, como descobre o número) e indo até a resolução, o encaminhamento ou a desistência. A pesquisa deve evitar a "miopia corporativa" de mapear do balcão para dentro.
2. **Evidências físicas de cada etapa:** número discado, mensagens e menus de voz, tempo de espera, protocolo, SMS, extrato, comprovantes, telas do CAIXA Tem e da CTPS Digital.
3. **Frontstage:** o que o cidadão vê e ouve (URA, atendente humano, atendente do 158, agência, Sine).
4. **Backstage e processos de suporte:** quem faz o quê fora da vista do cidadão (roteamento da URA, consulta a bases de dados, arquivo de retorno de pagamento CAIXA–MTE, Portal de Demandas, reprocessamento na Dataprev, medição e fiscalização contratual, telefonia, autenticação gov.br).
5. **Linhas do blueprint:** onde passam a linha de interação, a linha de visibilidade e a linha de interação interna.
6. **Normativos aplicáveis:** Lei 7.998/1990, Resoluções do CODEFAT, contratos MTE–CAIXA, Lei 13.460/2017 e regras de acessibilidade.
7. **Fail points conhecidos:** filas, quedas de ligação, menus confusos, falta de transbordo para humano, divergência entre parcela "paga" e crédito efetivo, encaminhamentos sem resolução, barreiras para pessoas surdas e para quem vive em área rural. Deve indicar, sempre que possível, dados quantitativos (tempo de espera, abandono, recontato).
8. **Rastreabilidade:** fontes verificáveis (sites oficiais, normas, contratos, acórdãos, relatórios de ouvidoria, notícias), com separação explícita entre fato documentado, inferência e lacuna.

## Forma de trabalho

Antes de escrever o prompt, faça perguntas se faltar alguma informação importante. Depois, entregue o prompt pronto para eu colar no assistente de deep research.
