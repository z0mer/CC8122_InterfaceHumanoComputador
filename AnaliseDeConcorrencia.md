### MoTeC I2
![MoTeC I2](https://github.com/z0mer/CC8122_InterfaceHumanoComputador/blob/main/IMG/MOTEC.jpg)

* **Quem é:** O software de análise de dados mais usado no automobilismo profissional (F1, WEC, Stock Car).
* **Link:** `motec.com.au`
* **Descrição Visual:** Interface escura, super densa, cheia de gráficos de linha (Line Charts) coloridos empilhados. Parece um monitor de ações da bolsa, só que de carro.
* **Funcionalidades:**
* Canais matemáticos (você programa fórmulas, ex: `WheelSpin = Speed - GPS_Speed`).
* Workspaces customizáveis (monta a tela como quiser).
* Histogramas de suspensão e Scatter Plots.

### Racelogic
![Racelogic](https://github.com/z0mer/CC8122_InterfaceHumanoComputador/blob/main/IMG/racelogic.jpg)

* **Quem é:** Focado em pilotos e track days. O forte deles é o hardware VBOX.
* **Link:** `vboxmotorsport.co.uk`
* **Descrição Visual:** Tela dividida. Metade é vídeo (câmera onboard), metade é gráfico/mapa da pista. Interface mais limpa e botões grandes.
* **Funcionalidades:**
* **Sincronia automática de Vídeo + Dados** (o grande trunfo).
* "Delta-T": Mostra em tempo real onde você perdeu tempo comparado à melhor volta.
* Análise de traçado sobreposta no mapa.

### Smart Eye
![SmartEye](https://github.com/z0mer/CC8122_InterfaceHumanoComputador/blob/main/IMG/smart%20eye.jpg)

* **Link:** smarteye.se
* **Descrição:** Líder mundial em IA para monitoramento de motoristas (DMS). Usado por montadoras (BMW, Geely) para desenvolver sistemas de segurança e HMI (Interação Humano-Máquina).
* **Características e Funcionalidades:**
* **Rastreamento Robusto:** Funciona com óculos escuros, à noite, e com o rosto parcialmente coberto.
* **Métricas de Atenção:** Mede nível de sonolência, distração cognitiva e direção do olhar (Gaze direction).
* **Integração:** Feito para ser embutido no painel do carro (não intrusivo).

---

### Experiência do Usuário (UX) & Opiniões

| Concorrente | O que a galera fala (UX) |
| --- | --- |
| **MoTeC i2** | 🤯 **Hardcore.** "É uma ferramenta para engenheiros, não para humanos normais". A curva de aprendizado é um paredão, mas quem domina, não troca por nada. |
| **Racelogic** | 😎 **Amigável.** "A melhor forma de aprender uma pista rápido". A UX é desenhada pro piloto ver o erro visualmente sem precisar fazer conta. |
| **Smart Eye** | 🤖 **Industrial.** "Extremamente preciso, mas focado em validação". A interface é feita para pesquisadores e desenvolvedores de carro, não para pilotos de corrida. O feedback não é pensado em "tempo de volta", mas em "estatística de comportamento". |

---

### Padrões e Tendências de Mercado

1. **Segurança vs. Performance:** O mercado automotivo (Smart Eye) tá obcecado com **Segurança** (evitar acidentes). O mercado de Racing (MoTeC) tá obcecado com **Performance** (ganhar tempo). Existe um buraco no meio disso.
2. **Sensor Fusion:** A tendência é juntar dados de fontes diferentes. O Smart Eye tá começando a cruzar dados faciais com sinais vitais, mas ainda engatinha na parte de telemetria esportiva.
3. **Non-Intrusive:** Ninguém mais quer usar óculos de Eye Tracking (tipo Tobii Glasses) dentro de um capacete apertado. A tendência é câmera remota no painel (que é o forte do Smart Eye e o desafio de vocês).

---

### Relatório Final

#### 🟢 Pontos Positivos da Concorrência

* **Smart Eye:** Tecnologia de ponta que não falha com vibração ou luz ruim (coisa crítica em carro de corrida).
* **MoTeC:** Flexibilidade infinita para tratar dados.
* **Racelogic:** Simplicidade visual que reduz a carga cognitiva do piloto.

#### 🔴 Pontos Negativos

* **Contexto Errado:** O *Smart Eye* te diz que o motorista olhou pra esquerda, mas não te diz se isso fez ele perder 0.1s na volta. Ele não "entende" de corrida.
* **Dados Silados:** Hoje, uma equipe precisaria comprar o MoTeC E o Smart Eye, e tentar fazer uma "gambiarra" pra cruzar os dados no Excel. Não existe uma ferramenta única.

