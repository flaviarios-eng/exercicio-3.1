# Diagrama AS-IS — Atendimento ao Seguro-Desemprego pela URA da CAIXA

**Aluna:** Flavia Rios · **Exercício 3.1** · Jornada de referência: **"o status indica parcela paga, mas o dinheiro não está na conta"**.
Os nós correspondem às etapas, camadas e fail points decididos na entrevista (`C_grill_transcript.md`) e registrados em `C_blueprint_asis.md`.

**Convenções (Rodadas 4, 6 e 7):** setas contínuas indicam fluxos documentados (F); setas tracejadas indicam relações hipotéticas ou não integralmente comprovadas (H/L); ⚠ marca um fail point.

```mermaid
flowchart TB
  subgraph ACIMA["Acima da linha de visibilidade — o que o cidadão vê e faz"]
    E1["1. Consulta o status 'paga' no app / CTPS Digital<br/>⚠ PF07 manifestação"]
    E2["2. Verifica a conta: o crédito não está lá<br/>⚠ PF07 manifestação"]
    E3["3. Liga 0800 726 0207 e navega pela URA<br/>⚠ PF02/L09"]
    E4["4. Busca atendente humano (condicional, L04)"]
    E5["5. Recebe orientação ou encaminhamento<br/>⚠ PF08"]
    E6["6. Recontata ou busca outro canal<br/>⚠ PF08 · PF09/PF12"]
    SAC["SAC CAIXA 0800 726 0101"]
    OUV["Ouvidoria CAIXA 0800 725 7474"]
    C158["Central 158 (MTE, operada pelo INSS)"]
    E7{"7. Desfecho do episódio"}
    F1(["Crédito recebido"])
    F2(["Desistência"])
    F3(["Permanece sem resolução<br/>⚠ PF09/PF12"])
    F4(["Devolução ao FAT após 67 dias<br/>(fluxo alternativo)"])
  end

  subgraph ABAIXO["Abaixo da linha de visibilidade — backstage"]
    RET["CAIXA gera arquivo de retorno<br/>marcando a parcela como 'paga'<br/>⚠ PF07 origem"]
    ENV["CAIXA processa e envia o crédito<br/>(a outro banco = 'efetivamente paga' no contrato)"]
    CONS["URA consulta bases (L03)"]
    ATD["Atendente consulta sistemas (L08)"]
    REG["Operador registra demanda no SIRCA (L10)"]
  end

  subgraph SUP["Processos de suporte"]
    SSD[("Sistema do Seguro-Desemprego (Dataprev)")]
    BANCO["Banco recebedor"]
    SIRCA[("Portal de Demandas / SIRCA")]
  end

  %% Jornada de referência
  E1 -->|"vê 'paga'"| E2
  E2 -->|"não encontra o dinheiro"| E3
  E3 -.->|"transbordo sem critério conhecido"| E4
  E3 -->|"URA informa"| E5
  E4 -->|"atendente orienta"| E5
  E5 -->|"caso não resolvido"| E6
  E6 -.->|"ciclo de recontato (peregrinação)"| E3
  E6 -->|"reclama"| SAC
  SAC -->|"não solucionado"| OUV
  E6 -->|"procura o MTE"| C158
  E6 --> E7
  E7 --> F1
  E7 --> F2
  E7 --> F3
  E7 -.->|"se a parcela não for sacada"| F4

  %% Origem do PF07 cruzando a linha de visibilidade
  RET -.->|"⚠ PF07: status 'paga' antes do crédito (causalidade não comprovada)"| E1
  RET -->|"retorno"| SSD
  SSD -->|"atualiza status no app"| E1
  ENV --> BANCO
  BANCO -.->|"crédito não percebido"| E2

  %% Bastidores dos canais
  E3 --> CONS
  CONS -.-> SSD
  E4 --> ATD
  E5 --> REG
  REG --> SIRCA
  SAC -.->|"histórico da URA compartilhado? (L23)"| E3

  classDef fail fill:#fdecea,stroke:#c0392b,stroke-width:2px
  classDef fim fill:#eef6ee,stroke:#2e7d32
  classDef alt stroke-dasharray: 5 5
  class E1,E2,E3,E5,E6,RET,F3 fail
  class F1,F2 fim
  class F4 alt
```

## Leitura do diagrama

- **Fluxo principal:** as etapas 1 a 7 do blueprint, da identificação do "paga" sem crédito até o desfecho.
- **Ciclo de recontato (Rodada 7):** a seta tracejada da etapa 6 de volta à etapa 3 representa a peregrinação. As ramificações para o SAC, a Ouvidoria e o 158 aparecem **sem transferência automática** do caso.
- **PF07 (Rodadas 4 e 7):** a seta tracejada do arquivo de retorno (backstage) até a etapa 1 **cruza a linha de visibilidade**, ligando a origem à manifestação da falha.
- **Quatro desfechos (Rodada 7):** crédito recebido, desistência, permanência sem resolução e devolução ao FAT. A devolução ao FAT é um fluxo alternativo, condicionado à regra dos 67 dias.
- **Lacunas visíveis:** L03, L04, L08, L10 e L23 estão nos rótulos e nos nós. São pontos de validação, e não fatos.
