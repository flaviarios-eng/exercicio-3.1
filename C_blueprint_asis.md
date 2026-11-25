# Service Blueprint AS-IS — Atendimento ao Seguro-Desemprego pela URA da CAIXA

**Aluna:** Flavia Rios · **Exercício 3.1** · IDP-TD 2026
**Serviço:** Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal (0800 726 0207; órgãos: CAIXA e Ministério do Trabalho e Emprego)
**Jornada de referência (Rodada 1):** **"O status indica parcela paga, mas o dinheiro não está na conta"** (trabalhador formal).
**Base:** decisões da sessão grill-me (`C_grill_transcript.md`) e evidências de `B_relatorio_assistente_v3.md`. Os códigos E##, PF## e L## remetem à v3.

---

## 1. Regras adotadas (decididas na entrevista)

- **Fronteira (Rodada 2):** o blueprint começa quando o cidadão **identifica a divergência** e termina no **desfecho do episódio de atendimento**. A dispensa, o requerimento e a habilitação ficam fora.
- **Etapas (Rodada 2):** são 7, na ótica do cidadão. A etapa 4 (atendimento humano) é **condicional**, porque o critério de transbordo da URA é desconhecido (L04).
- **Linha de visibilidade (Rodada 3):** o critério é a **percepção do usuário**. A URA fica **acima** da linha, por interagir com o cidadão, mesmo sendo automatizada.
- **Backstage × suporte (Rodada 5):** o backstage reúne as ações da CAIXA e dos operadores que o cidadão não vê. O suporte reúne os sistemas e terceiros (Sistema do Seguro-Desemprego/Dataprev, banco recebedor e Portal de Demandas/SIRCA). A fiscalização contratual fica **fora do blueprint**, como governança.
- **Convenção de evidência (Rodada 6):** cada célula traz **F** (fato documentado), **H** (hipótese, só quando diretamente relevante) ou **L** (lacuna, com o seu código).
- **Fail points (Rodada 4):** são quatro. O PF07 está marcado **na origem (backstage) e na manifestação (etapas 1 e 2)**, ligados entre si. O L04 é uma lacuna, e não uma falha.

---

## 2. Blueprint

| Camada \ Etapa | 1. Consulta o status "paga" | 2. Verifica a ausência do crédito | 3. Liga e navega pela URA | 4. Busca atendimento humano *(condicional)* | 5. Recebe orientação ou encaminhamento | 6. Recontata ou busca outro canal | 7. Obtém resolução ou permanece sem solução |
|---|---|---|---|---|---|---|---|
| **Evidências físicas** | Mensagem **"paga"** na tela do app ou da CTPS Digital — F (E021) | Extrato ou saldo **sem o valor**, na conta ou no CAIXA Tem — F (ED08) | Número **0800 726 0207** — F (E004, E005); áudio do menu — conteúdo L01 | Voz do atendente; número de protocolo — L06 | Orientação verbal para procurar outro canal; protocolo — L06 | Números do **SAC 0800 726 0101**, da **Ouvidoria 0800 725 7474** e do **158** — F (E039, E017) | Crédito no extrato, ou ausência dele — F; confirmação de resolução ao cidadão — L18 |
| **Ações do cidadão** | Abre o app ou a CTPS e vê a parcela como "paga" — F | Confere a conta e não encontra o dinheiro — F | Disca o 0800, escolhe opções e informa dados (dados exigidos: L02) — F/L | Tenta falar com um atendente e relata o caso — F/L04 | Recebe a orientação e anota para onde ir — F | Liga de novo para a URA, ou procura o SAC, a Ouvidoria ou o 158, e **repete o caso** — F (E019, E046) | Recebe o crédito, desiste ou continua sem solução — I |
| — *Linha de interação* — | | | | | | | |
| **Frontstage** (visível) | Interface digital do app ou da CTPS Digital (autosserviço) — F (E023) | App bancário, CAIXA Tem ou extrato — F (E048) | **URA da CAIXA** respondendo sobre a parcela — F (E004); distinção entre "paga" e "creditada" na resposta — L09 | **Atendente CAIXA Cidadão** (seg.–sex. 8h–21h; sáb. 10h–16h) — F (E004); critério de transbordo — L04 | URA ou atendente informando e encaminhando — F | URA de novo; SAC e Ouvidoria da CAIXA; operadores do Contact Center 158 — F (E039, E018) | Canal que concluiu o atendimento, se houver — I |
| — *Linha de visibilidade* — | | | | | | | |
| **Backstage** (invisível) | **CAIXA gera e transmite o arquivo de retorno** ao MTE/Dataprev, que marca a parcela como "paga" — F (E012, E021) ⚠ origem do PF07 | **Processamento e envio do crédito** pela CAIXA; o envio a outro banco já conta como "efetivamente paga" no contrato — F (E013) | Consulta da URA às bases (quais sistemas: L03) | Atendente consulta sistemas internos (o que ele vê a mais que a URA: L08) | **Operador registra a demanda no Portal de Demandas/SIRCA** — uso para casos individuais: L10 | Tratamento da reclamação pelo SAC e pela Ouvidoria (histórico da URA compartilhado? L23) — F/L | Regularização do crédito ou tratamento da rejeição — F (E012); devolução ao FAT após 67 dias *(fluxo alternativo)* — F (E035) |
| — *Linha de interação interna* — | | | | | | | |
| **Processos de suporte** | **Sistema do Seguro-Desemprego (Dataprev)** atualiza o status a partir do retorno — F (E016, E012) | **Banco recebedor**, quando o crédito vai para outra instituição — F (E013) | Plataforma telefônica da CAIXA — F (E004); tecnologia e fornecedor da URA — L16 | Sistemas e CRM do atendimento CAIXA — L | **Portal de Demandas/SIRCA** (perfis Técnico e Gestor) — F (E011) | Contact center do 158 (TED MTE–INSS) — F (E018); Sistema do Seguro-Desemprego — F | Banco recebedor; Sistema do Seguro-Desemprego — F |
| **⚠ Fail points** | **PF07 (manifestação):** status "paga" sem crédito | **PF07 (manifestação):** o cidadão não encontra o dinheiro | **PF02/L09:** a URA pode repetir a informação divergente | — *(L04 é lacuna, não falha)* | **PF08:** encaminhamento sem continuidade do contexto | **PF08** e **PF09/PF12:** recontatos e peregrinação entre canais | **PF09/PF12:** episódio termina sem resolução |
| **Lacunas a validar** | — | — | L01 menu, L02 dados exigidos, L03 sistemas consultados, L09 | L04 transbordo, L06 protocolo, L08 | L06, L10 | L07 protocolo compartilhado, L23 | L11 responsável ponta a ponta, L18 confirmação |

**Ligação do PF07 (Rodadas 4 e 7):** a falha **se origina** no backstage da etapa 1 (arquivo de retorno que marca "paga") e **se manifesta** nas etapas 1 e 2. A ligação cruza a linha de visibilidade e está desenhada como **seta tracejada** no `D_diagrama_asis.md`, porque a causalidade não está integralmente comprovada.

---

## 3. Fluxos alternativos (fora da jornada de referência — Rodadas 1, 2 e 6)

- **30 dias sem liberação da primeira parcela** — causa provável na habilitação (MTE/Dataprev); gatilho documentado na FAQ da CAIXA (E033).
- **Bloqueio de cartão ou senha** — tratamento previsto em contrato (E047); a relação entre o 111 e o 0800 está em aberto (L22).
- **Consulta ao calendário** — informação simples, sem intercorrência.
- **Devolução ao FAT após 67 dias sem saque** — com possibilidade de reemissão em até 2 anos (E035); o canal da reemissão é desconhecido (L25).
- **Acessibilidade (pessoas surdas):** atendimento em Libras disponível na CAIXA (E024), **sem equivalência comprovada** com a URA e sem garantia de resolução do episódio (Rodada 6).

## 4. Fora do blueprint AS-IS (Rodada 5)

- **Fiscalização contratual do MTE** (camada de governança).
- **Hipótese de incentivo:** a remuneração "por parcela paga" (Contrato 07/2026) poderia estimular a marcação antecipada do status "paga". Fica registrada **apenas como hipótese de investigação**, sem evidência de relação causal.

## 5. Síntese do diagnóstico

O episódio nasce de uma **divergência invisível** (backstage) que se torna **visível** ao cidadão (status "paga" sem dinheiro). Os canais de frontstage (URA, atendente, SAC, Ouvidoria e 158) **informam e encaminham**, mas não há evidência de que algum deles compartilhe o contexto do caso ou tenha a responsabilidade pelo episódio completo (L07, L11). O resultado é um **ciclo de recontato** (etapa 6 → etapa 3) em que o próprio cidadão carrega o caso entre os canais.
