# Cenário de Análise de Problema — Interface Humano-Computador
### Projeto: Análise Pupilométrica e o Tempo de Reação em Pilotos Automotivos
**Equipe:** Anna Carolina R. P. Zomer (22.224.017-8) | Humberto de O. Pellegrini (22.224.019-4)  
**Orientador:** Prof. Dr. Victor Perrone de Lima Varela

---

## 1. Ambiente e Contexto

### 🏁 Ambiente Físico
O sistema é utilizado no **Pit Lane (Box) do Autódromo de Interlagos**, um ambiente industrial, hostil e de altíssima pressão temporal.

- **Ruído extremo:** O som dos motores impede comunicação verbal eficiente. Qualquer instrução precisa ser visual ou por gestos.
- **Calor e vibração:** O asfalto irradia calor, e o piloto retorna suado e com adrenalina elevada.
- **Espaço improvisado:** A engenheira opera um notebook apoiado em pilhas de pneus ou agachada ao lado do carro, cercada por ferramentas mecânicas, cabos e combustível.
- **Iluminação variável:** A tela precisa ser legível sob sol direto ou à noite sob holofotes artificiais.
- **Conectividade limitada:** Não há garantia de Wi-Fi estável; os dados precisam ser processados localmente via USB.

### ⏱️ Contexto Temporal
- A equipe tem **apenas ~5 minutos** entre sessões para extrair dados, analisar e ajustar o setup do carro.
- O sistema precisa entregar resultados em **menos de 30 segundos** após a conexão do cabo USB.
- Qualquer atraso significa **perda de tempo de pista**, que é o recurso mais caro no automobilismo.

### 🧠 Contexto Social e Emocional
- Clima de **urgência constante** e cobrança da equipe ("Anna, cadê o dado?").
- O piloto está cheio de adrenalina, impaciente, e quer respostas visuais imediatas.
- A engenheira sente **ansiedade paralisante** se o software travar ou a sincronia falhar.
- Não há espaço para "ler o manual" — a interface precisa ser **autoexplicativa**.

---

## 2. Atores (Personas)

### 👩‍💻 Persona Primária: Anna (Engenheira de Dados)
> 🗣️ *"Eu preciso que o vídeo e a telemetria conversem sozinhos. Meu trabalho é criar estratégia pra ganhar a corrida, não perder 20 minutos sincronizando arquivo na mão."*

| Aspecto | Descrição |
|---|---|
| **Idade** | 23 anos |
| **Perfil** | Estudante de Ciência da Computação, analítica, metódica |
| **Papel** | Operadora do sistema — configura, extrai e analisa os dados |
| **Habilidades** | Expert em lógica e dados, mas precisa de agilidade sob pressão |
| **Tarefas** | Calibrar Eye Tracker, baixar logs, sincronizar vídeo + dados, gerar relatório |
| **Necessidade principal** | Automação da sincronização e exportação rápida (CSV) |
| **Frustração** | Perder tempo precioso fazendo trabalho manual e repetitivo |

### 🏎️ Persona Primária: Humberto (Piloto)
> 🗣️ *"Cara, eu sei que fui lento na curva 3, só me mostra no vídeo ONDE eu olhei errado."*

| Aspecto | Descrição |
|---|---|
| **Idade** | 24 anos |
| **Perfil** | Piloto competitivo, visual, prático e impaciente |
| **Papel** | Consumidor do dado — vê o replay na tela que a Anna mostra |
| **Habilidades** | Pilotagem extrema, mas prefere interfaces visuais diretas |
| **Tarefas** | Dirigir o veículo e assistir ao replay com o "Gaze Point" sobreposto |
| **Necessidade principal** | Interface limpa, botões grandes, feedback visual imediato |
| **Frustração** | Não conseguir ver rapidamente onde errou |

### 🧬 Persona Secundária: Varela (Preparador Físico)
> 🗣️ *"Se a pupila dilatar de cansaço na volta 15, o tempo sobe. Eu treino o cérebro, não só o músculo."*

| Aspecto | Descrição |
|---|---|
| **Idade** | 42 anos |
| **Perfil** | Fisiologista do Esporte, experiente e observador |
| **Papel** | Analista de longo prazo — planejamento fora da pista |
| **Habilidades** | Expert em biometria, dificuldade com software de engenharia |
| **Tarefas** | Analisar gráficos de carga cognitiva nas voltas finais |
| **Necessidade principal** | Relatórios simplificados (PDF) com gráficos de tendência |

---

## 3. Objetivos dos Atores

| Ator | Objetivo Principal | Objetivo Secundário |
|---|---|---|
| **Anna** | Automatizar o cruzamento de dados (eye tracker + telemetria) para gerar insights em <30s | Encontrar correlações científicas ("freou tarde porque olhou tarde") |
| **Humberto** | Baixar o tempo de volta imediatamente | Validar se a percepção dele bate com a realidade dos dados |
| **Varela** | Monitorar fadiga cognitiva ao longo do campeonato | Provar com dados que preparo físico impacta atenção visual |

---

## 4. Esquema de Interação Humano-Computador

### Fluxo Principal de Interação

```
┌─────────────────────────────────────────────────────────────────────┐
│                    ANTES DA SESSÃO (20 min)                        │
│                                                                     │
│  [ANNA] ──► [SISTEMA: Tela de Calibração] ──► [HUMBERTO]          │
│     │         ┌──────────────────────┐           │                  │
│     │         │  👁️ Eye Tracker      │           │                  │
│     │         │  Pupil Core          │◄──────────┘                  │
│     │         │  "Olhe para os       │  (Humberto olha para        │
│     │         │   pontos na tela"    │   os marcadores)            │
│     │         └──────────────────────┘                              │
│     │                                                               │
│     └──► [Feedback Visual: ✅ Calibração OK]                       │
└─────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────���──────────────────┐
│                    DURANTE A SESSÃO (20 min)                       │
│                                                                     │
│  [HUMBERTO pilota] ──► [Hardware coleta dados automaticamente]     │
│                          │                          │               │
│                    ┌─────┴─────┐             ┌──────┴──────┐       │
│                    │ Eye Tracker│             │ Telemetria  │       │
│                    │ (Pupila,  │             │ (Freio,     │       │
│                    │  Gaze)    │             │  Aceleração,│       │
│                    └───────────┘             │  Esterçam.) │       │
│                                              └─────────────┘       │
│  [ANNA] ──► [SISTEMA: Ponto Cego 😰]                              │
│              "Os dados estão sendo gravados corretamente?"          │
└─────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────┐
│               APÓS A SESSÃO — O MOMENTO DA VERDADE (~5 min)       │
│                                                                     │
│  [ANNA conecta USB] ──► [SISTEMA: Ingestão Automática]            │
│                          │                                          │
│                          ▼                                          │
│              ┌───────────────────────┐                              │
│              │  🔄 MERGE AUTOMÁTICO  │  ◄── O GRANDE DIFERENCIAL  │
│              │                       │                              │
│              │  Vídeo (Eye Tracker)  │                              │
│              │  + Telemetria (Carro) │                              │
│              │  + Timestamps         │                              │
│              │                       │                              │
│              │  ████████████ 100%    │  (~30 segundos)             │
│              │  ✅ Sincronizado!     │                              │
│              └───────────┬───────────┘                              │
│                          │                                          │
│                          ▼                                          │
│              ┌───────────────────────┐                              │
│              │  📊 TELA DE ANÁLISE   │                              │
│              │                       │                              │
│              │  ┌─────────────────┐  │                              │
│              │  │ 🎥 Vídeo com    │  │  ◄── Humberto vê aqui      │
│              │  │ Gaze Point (👁️) │  │      "onde olhou errado"   │
│              │  └─────────────────┘  │                              │
│              │  ┌─────────────────┐  │                              │
│              │  │ 📈 Diâmetro da  │  │  ◄── Anna analisa aqui     │
│              │  │ Pupila x Tempo  │  │      carga cognitiva       │
│              │  └─────────────────┘  │                              │
│              │  ┌─────────────────┐  │                              │
│              │  │ 🗺️ Mapa da     │  │  ◄── Traçado + Gaze        │
│              │  │ Pista + Traçado │  │      sobrepostos            │
│              │  └─────────────────┘  │                              │
│              └───────────────────────┘                              │
│                          │                                          │
│              [ANNA] ──► [HUMBERTO]                                  │
│              "Você não olhou pra zebra na curva 3!"                │
│                          │                                          │
│                          ▼                                          │
│              [EXPORTAR] ──► PDF para Varela (relatório de fadiga)  │
└─────────────────────────────────────────────────────────────────────┘
```

### Diagrama de Interação Simplificado (por Ator)

```
    ┌──────────┐         ┌──────────────────┐         ┌───────────┐
    │  ANNA    │         │    SISTEMA       │         │ HUMBERTO  │
    │(Operadora)│         │  (Software de    │         │ (Piloto)  │
    └────┬─────┘         │  Processamento)  │         └─────┬─────┘
         │               └────────┬─────────┘               │
         │                        │                          │
         │──Calibra Eye Tracker──►│                          │
         │                        │◄──Olha para marcadores───│
         │◄──Feedback: "OK" ──────│                          │
         │                        │                          │
         │                        │◄──Pilota (dados brutos)──│
         │                        │   (pupila + telemetria)  │
         │                        │                          │
         │──Conecta USB ────────►│                          │
         │                        │──Merge Automático (30s)  │
         │◄──Dados Sincronizados──│                          │
         │                        │                          │
         │──Seleciona volta ─────►│                          │
         │◄──Replay c/ Gaze ──────│──────────────────────────►│
         │                        │      (Vídeo + bolinha     │
         │                        │       do olhar)           │
         │                        │                          │
         │──Exporta PDF ────────►│                          │
         │◄──Relatório Fadiga ────│                          │
         │                        │                          │
    ┌────┴─────┐                                      ┌─────┴─────┐
    │ Envia    │                                      │ Entende   │
    │ p/ Varela│                                      │ o erro    │
    └──────────┘                                      └───────────┘
```

---

## 5. Narrativa do Cenário de Análise/Problema

### 🎬 "A Corrida Contra o Relógio de Anna"

**Contexto:** Autódromo de Interlagos, São Paulo. Sessão de testes de uma equipe amadora que investe em tecnologia de ponta para análise de desempenho.

---

**Ato 1 — A Preparação (20 min antes)**

São 14h de uma sexta-feira escaldante. Anna chega ao box com seu notebook reforçado debaixo do braço e a maleta com os óculos Pupil Core. O ruído dos motores já é ensurdecedor — ela se comunica com Humberto por gestos e gritando.

Ela precisa calibrar o Eye Tracker no rosto do piloto. Humberto, já com o macacão de corrida, está inquieto. *"Anda logo, Anna, o treino começa em 15!"* — ele grita. Anna posiciona os óculos e abre a tela de calibração no notebook. Humberto precisa fixar o olhar em 5 pontos na tela. Ele se mexe, ela precisa recalibrar. Tempo perdido. A ansiedade começa.

**Dor atual:** Não existe um feedback claro de que a calibração foi bem-sucedida. Anna precisa confiar na intuição.

---

**Ato 2 — O Ponto Cego (20 min de sessão)**

Humberto entra na pista. Anna... espera. Ela fica no box sem saber se os óculos estão coletando dados corretamente. O Eye Tracker pode ter descalibrado com a vibração do carro. A telemetria do veículo (Racelogic) grava em um arquivo separado. São dois sistemas independentes que não se falam.

Anna sente **impotência**. Ela torce para que tudo esteja funcionando, mas não tem como verificar em tempo real.

**Dor atual:** Dois sistemas isolados gravando dados em formatos diferentes, sem validação em tempo real.

---

**Ato 3 — O Clímax: 5 Minutos de Caos**

O carro retorna ao box. Humberto sai visivelmente frustrado: *"Não consigo manter a constância na curva 3! O carro não faz curva!"*

Anna corre para conectar o cabo USB. O chefe de equipe grita no rádio: *"Anna, temos 5 minutos para o setup, cadê o dado?"*

**❌ SEM o sistema proposto (cenário problemático atual):**
- Anna baixa os logs do veículo: arquivo `.csv` com 50 colunas.
- Baixa os dados do Eye Tracker: outro arquivo `.csv` com timestamps diferentes.
- Abre o Excel. Tenta alinhar manualmente os timestamps.
- O notebook trava. Ela perde 2 minutos reiniciando.
- Humberto está impaciente olhando por cima do ombro dela.
- Depois de 8 minutos (3 a mais do que tinha), ela tem uma correlação "mais ou menos" que pode conter erros.
- O treino seguinte é perdido. A equipe paga R$2.000/hora de pista desperdiçada.

**✅ COM o sistema proposto (cenário ideal):**
- Anna conecta o USB. O sistema detecta automaticamente os dois dispositivos.
- Em **30 segundos**, o merge automático sincroniza vídeo + telemetria + dados pupilares.
- A barra de progresso fica verde: ✅ *Sincronizado!*
- Anna seleciona "Volta 5 — Curva 3" e vira o notebook para Humberto.
- Na tela: o vídeo onboard mostra a bolinha do olhar (Gaze Point) de Humberto focada **no retrovisor** ao invés da **zebra de entrada da curva**.
- Anna diz: *"Você olhou pro retrovisor 0.3s tarde demais. Sua pupila dilatou 40% — estava em sobrecarga cognitiva."*
- O dado é **irrefutável**. Humberto entende visualmente. O setup é ajustado em 2 minutos.

---

**Ato 4 — O Pós-Corrida**

No hotel, Anna exporta um relatório PDF para o Varela. O relatório mostra um gráfico de linha com a evolução do diâmetro pupilar ao longo das 20 voltas. Nas últimas 5 voltas, a dilatação média subiu 35% — sinal claro de **fadiga cognitiva**. Varela ajusta o treino físico da semana seguinte para incluir exercícios de resistência mental.

---

## 6. Como a Interface Agrega Valor ao Usuário

### O Problema Central
Hoje, **não existe uma ferramenta única** que cruze dados de rastreamento ocular com telemetria veicular no contexto de corridas. As soluções existentes atendem apenas metade do problema:

| Ferramenta | O que faz bem | O que NÃO faz |
|---|---|---|
| **MoTeC i2** | Análise profunda de telemetria (freio, aceleração, traçado) | Não integra dados de eye tracking nem biometria |
| **Racelogic** | Sincroniza vídeo com dados do carro | Não analisa olhar do piloto nem carga cognitiva |
| **Smart Eye** | Rastreia olhar e mede atenção/sonolência | Não entende de corrida — não correlaciona com tempo de volta |

### O que o nosso sistema resolve

```
┌──────────────────────────────────────────────────────────────┐
│                    VALOR AGREGADO                             │
│                                                              │
│  ┌────────────┐    ┌────────────┐    ┌────────────┐         │
│  │ Eye Tracker│    │ Telemetria │    │   Vídeo    │         │
│  │  (Pupila,  │    │  (Freio,   │    │  Onboard   │         │
│  │   Gaze)    │    │  Aceler.)  │    │            │         │
│  └─────┬──────┘    └─────┬──────┘    └─────┬──────┘         │
│        │                 │                 │                  │
│        └────────────┬────┴─────────────────┘                 │
│                     ▼                                        │
│          ┌──────────────────────┐                            │
│          │  🔄 MERGE AUTOMÁTICO │  ◄── DIFERENCIAL          │
│          │  (sincronização por  │      COMPETITIVO           │
│          │   timestamp em 30s)  │                            │
│          └──────────┬───────────┘                            │
│                     ▼                                        │
│          ┌──────────────────────┐                            │
│          │  📊 ANÁLISE CRUZADA  │                            │
│          │                      │                            │
│          │  "Freou 0.3s tarde   │                            │
│          │   PORQUE olhou pro   │                            │
│          │   retrovisor"        │                            │
│          │                      │                            │
│          │  "Pupila dilatou 40% │                            │
│          │   = sobrecarga       │                            │
│          │   cognitiva"         │                            │
│          └──────────────────────┘                            │
│                                                              │
│  RESULTADO: Dado ACIONÁVEL em 30 segundos                   │
│  (vs. 20+ minutos de trabalho manual com risco de erro)     │
└──────────────────────────────────────────────────────────────┘
```

### Benefícios Concretos por Ator

| Ator | Benefício | Métrica de Valor |
|---|---|---|
| **Anna** | Elimina trabalho manual de sincronização | De 20 min → 30 segundos |
| **Humberto** | Vê visualmente onde errou no vídeo | Feedback imediato entre sessões |
| **Varela** | Recebe relatório de fadiga cognitiva automatizado | Dados longitudinais para treino |
| **Equipe** | Não perde tempo de pista esperando dados | Economia de ~R$2.000/hora |

---

## 7. Mapa de Empatia (Persona: Anna)

| Quadrante | Resposta |
|---|---|
| **O que VÊ?** | O Humberto suado e a equipe impaciente esperando respostas, enquanto a tela mostra arquivos CSV desconexos que não se alinham. |
| **O que OUVE?** | O som ensurdecedor dos motores e o rádio do chefe: *"Anna, temos 5 minutos, cadê o dado?"* |
| **O que PENSA e SENTE?** | Ansiedade paralisante: *"Se o software travar agora, vamos perder o treino e a culpa será minha."* |
| **O que FALA e FAZ?** | Grita *"Humberto, pare de mexer a cabeça!"* enquanto digita freneticamente alternando janelas. |
| **DORES** | Perder tempo fazendo trabalho manual repetitivo sob pressão extrema, com risco de erro humano. |
| **NECESSIDADES** | Ferramenta que faça ingestão automática dos dados assim que o cabo for conectado, entregando análise pronta em segundos. |

---

## 8. Conclusão — Por que este projeto é necessário?

O automobilismo moderno já gera dados de telemetria em abundância, mas **ninguém está olhando para o piloto**. As ferramentas existentes tratam o carro como máquina e ignoram que o piloto é um sistema biológico com limitações cognitivas.

Nosso sistema preenche essa lacuna ao:
1. **Unificar dados silados** (olhar + carro + vídeo) em uma única plataforma
2. **Automatizar a sincronização** eliminando o gargalo humano
3. **Traduzir dados complexos em feedback visual** acessível ao piloto
4. **Quantificar o invisível** — a carga cognitiva — transformando "achismo" em ciência

> *"O dado de telemetria te diz O QUE o carro fez. O nosso sistema te diz POR QUE o piloto fez o carro fazer isso."*