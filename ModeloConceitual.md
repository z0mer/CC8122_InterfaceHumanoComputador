# Modelo Conceitual

### 1) Cenários de Interação

> **_NOTE:_** O texto em **negrito** destaca a mudança de paradigma: sai o processo manual, entra a solução do sistema desenvolvido no TCC.

**Nome do Cenário: A Sincronização Ágil no Pit Lane**

No intervalo apertado de 15 minutos de um treino de sábado [2], Anna, a engenheira de dados da equipe [1], precisa desesperadamente cruzar as informações do carro para entender a perda de tempo. O ambiente é caótico: o barulho ensurdecedor gera estresse, e o sol bate direto na tela do computador [5]. 

Para iniciar sua Jornada, Anna **abre o novo Sistema de Análise Integrada** e tira o cartão SD do Eye Tracker [3]. Seu objetivo é cruzar o gráfico de frenagem com o vídeo de dilatação da pupila [4]. **Acessando o Menu Principal, Anna clica em "Iniciar Nova Análise" e insere os arquivos do MoTeC e do Eye Tracker na mesma tela.** Sua ação **agora se resume a clicar no botão "Processar e Enviar" [7].** **O sistema realiza a sincronia dos dados de forma automática em 30 segundos, exibindo a Tela de Comparação com o vídeo onboard perfeitamente alinhado aos gráficos de telemetria [8].** Suando frio, **mas com 14 minutos sobrando**, ela chama Humberto, que depende daquela informação para voltar à pista [9]. Anna mostra a tela **com o Gaze Point (ponto do olhar) sincronizado no vídeo**: "Você freou tarde porque olhou pro painel, não pra zebra". Humberto entende o erro instantaneamente. Anna sente um alívio imediato, sabendo que a falha foi identificada e a meta atingida **sem desgaste mental e trabalho manual [10].**

---

### 2) Design Centrado na Comunicação

**Nome do Cenário: Sincronizar e Analisar Dados de Performance**

| tópico > subtópico (diálogo) | falas e signos |
| :---- | :---- |
| Configurar Análise > Inserir Logs | U: Preciso iniciar uma nova análise de desempenho. |
| | D: Aqui está o formulário de Configuração. Por favor, insira os arquivos e valores de calibração. |
| > | U: Quero processar os arquivos inseridos (.ld e .mp4). |
| | D: Dados processados com sucesso. Aqui está a tela de Comparação. |
| Comparar Telemetrias > Visualizar | U: Preciso ver a telemetria veicular alinhada com o olhar do piloto. |
| | D: Aqui estão os gráficos alinhados na mesma linha do tempo do vídeo. Use a barra de controle para ajustar. |
| Visualizar Resultados > Gráficos Avançados | U: Quero ver os dados complexos (Carga Cognitiva e Mapa de Calor). |
| | D: Aqui estão os gráficos de dispersão e dilatação pupilar. |
| Exportar > Salvar Relatório | U: Quero exportar este relatório para o preparador físico. |
| | D: Aqui está o local para salvar o PDF. Relatório salvo com sucesso! |

---

### 3) Mapa de Objetivos

> **_NOTE:_** Diagrama de consolidação hierárquica dos objetivos do usuário dentro do sistema.

1. **Gerenciar Análise (Meta Principal)**
   * 1.1 Iniciar Nova Análise
      * 1.1.1 Inserir arquivos de telemetria (MoTeC) e vídeo (Eye Tracker)
      * 1.1.2 Definir valores de calibração (offset)
   * 1.2 Consultar Histórico
      * 1.2.1 Selecionar e carregar sessão anterior salva
   * 1.3 Analisar Dados Sincronizados
      * 1.3.1 Comparar vídeo do *Gaze Point* com telemetria básica
      * 1.3.2 Analisar gráficos avançados (Carga Cognitiva, *Scatter Plot*)
   * 1.4 Exportar Resultados
      * 1.4.1 Gerar relatório em PDF
      * 1.4.2 Salvar localmente no computador

---

### 4) Esquema Conceitual de Signos

> **_NOTE:_** Junção das três tabelas referentes aos dados inseridos na tela de **Configurar Análise (C)** - Os artefatos que a Anna preenche para o sistema funcionar.

| Configuração de Análise (C) - Dados para cruzamento das telemetrias | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **signo** | **origem** | **observações** | **Tipo de conteúdo** | **restrição sobre conteúdo** | **valor default** | **prevenção (PP)** | **recuperação (RA)** |
| Log MoTeC | domínio | Ficheiro do carro | arquivo (.ld, .csv) | obrigatório, não pode ser nulo | — | PP: Filtro aceita apenas extensões de telemetria veicular | RA: Mensagem de erro "[SR] Arquivo veicular inválido" |
| Log Eye Tracker | domínio | Ficheiro do óculos | arquivo (.mp4, .csv) | obrigatório, não pode ser nulo | — | PP: Filtro aceita apenas vídeo/telemetria visual | RA: Mensagem de erro "[SR] Arquivo visual inválido" |
| Offset de Sincronia | IHC | Ajuste fino de tempo | numérico | numérico, permite valores negativos | 0 | PP: Campo numérico, impede texto | RA: Alerta visual se o valor exceder o tempo do vídeo |
| Nome da Sessão | IHC | Para salvar no histórico | texto | opcional, máximo 50 caracteres | "Sessão [Data]" | PP: Bloqueio de limite de caracteres | RA: Destaque em vermelho caso use caracteres especiais não permitidos |

-Com esse consolidado, o Plínio vai ver que tu pegou as metodologias de Design Centrado na Comunicação (MoLIC) e aplicou diretinho no caso de uso da Anna! Se precisar de mais alguma coisa pra matar essa entrega, só chamar! 🚀🏁
