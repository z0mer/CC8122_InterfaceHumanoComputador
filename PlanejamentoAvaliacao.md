# 1. Planejamento da Avaliação de Usabilidade (Método DECIDE)

Este documento apresenta o planejamento detalhado da avaliação de IHC para o Sistema de Análise Integrada (Telemetria Veicular + Eye Tracking), estruturado através do framework DECIDE.

### D - Determinar os Objetivos Gerais da Avaliação
O objetivo principal desta avaliação é medir a **usabilidade** (eficácia, eficiência e satisfação) e a **qualidade da experiência do usuário (UX)** na interface de três telas desenvolvida. Especificamente, busca-se validar se o sistema automatizado mitiga a carga cognitiva e o estresse da engenheira de dados durante o processo crítico de sincronização de logs brutos sob restrição de tempo, além de verificar se o feedback visual gerado facilita a tomada de decisão da equipe técnica.

### E - Explorar as Perguntas a Serem Respondidas
Para guiar o processo de avaliação, foram estabelecidas as seguintes perguntas de pesquisa baseadas no contexto de uso:
1. **Eficácia:** A engenheira de dados (Anna) consegue concluir o upload, calibração e envio dos logs na Tela 1 sem cometer erros críticos de compatibilidade de arquivos?
2. **Eficiência:** Qual é o tempo médio (*time-on-task*) gasto para o sistema realizar o *merge* automatizado e plotar os dados comparativos na Tela 2? O processo ocorre em menos de 2 minutos?
3. **Prevenção de Erros:** Os filtros de restrição de extensão implementados na interface impedem que o usuário insira arquivos inválidos antes do processamento?
4. **Carga Cognitiva:** O piloto (Humberto) consegue identificar de forma autônoma em qual ponto da pista (focando na Volta 0, a saída do grid) ocorreu o desvio de atenção visual, utilizando apenas os elementos simplificados da Tela 2?
5. **Liberdade do Usuário:** Em caso de interrupções externas simuladas, os botões de "Cancelar" e "Voltar" oferecem saídas de emergência eficientes sem gerar travamentos ou perda de dados locais?

### C - Escolher os Métodos de Avaliação
A abordagem metodológica será mista, combinando métodos analíticos e empíricos para garantir a validade dos dados:
* **Método de Inspeção (Avaliação Heurística):** Executado previamente por especialistas para mapear possíveis violações das 10 Heurísticas de Nielsen nas três telas do sistema, focando em severidades catastróficas.
* **Método Empírico (Teste de Usabilidade por Observação Direta):** Realizado em ambiente simulado para capturar o comportamento real do usuário interagindo com o sistema sob cenários de tarefas predefinidos.

### I - Identificar as Questões Práticas
O planejamento operacional para a execução dos testes empíricos segue os parâmetros abaixo:
* **Perfil dos Participantes:** Serão selecionados 6 participantes no total, divididos em dois perfis específicos: 3 Engenheiros/Coaches de pista (usuários operacionais - Perfil Anna) e 3 Pilotos de competição (usuários consumidores dos gráficos - Perfil Humberto).
* **Ambiente de Teste:** As sessões serão conduzidas na infraestrutura de simuladores da **Pilotech**, configurando o brilho dos monitores no nível máximo para mimetizar a iluminação agressiva (reflexo solar) do box de um autódromo.
* **Equipamentos e Materiais:** Computador portátil de alta performance rodando o software e conjunto de dados brutos pré-coletados de treinos reais (.ld do MoTeC e .mp4 do Eye Tracker).

### D - Decidir como Lidar com as Questões Éticas
Devido à natureza dos dados manipulados pelo sistema, os seguintes protocolos éticos serão adotados rigidamente:
* **Consentimento:** Todos assinarão o Termo de Consentimento Livre e Esclarecido (TCLE), confirmando que a participação é voluntária e pode ser interrompida a qualquer momento.
* **Privacidade e LGPD:** Os dados do Eye Tracker envolvem biometria e mapeamento pupilar, classificados como **dados sensíveis**. O sistema garantirá o anonimato completo desses registros.
* **Sigilo Desportivo:** Os logs veiculares revelam os segredos de setup do carro. Os arquivos serão tratados sob estrito sigilo de confidencialidade.

### E - Avaliar, Analisar e Apresentar os Dados
A consolidação dos resultados será dividida em duas frentes analíticas:
* **Análise Quantitativa:** Tabulação dos tempos de execução comparados com a meta estipulada (< 2 minutos), cálculo da taxa de sucesso sem ajuda e contagem de erros críticos por tela.
* **Análise Qualitativa:** Agrupamento das observações e aplicação da métrica SUS (System Usability Scale) para gerar uma lista de recomendações priorizadas visando o refinamento contínuo da UI/UX.

---

### Lista de Instrumentos e Materiais de Apoio
Para garantir o rigor da avaliação empírica, foi estruturado o seguinte conjunto de instrumentos complementares à execução do método:
1. **Termo de Consentimento Livre e Esclarecido (TCLE):** Documento impresso e assinado antes da sessão.
2. **Questionário de Perfil do Usuário (Pré-teste):** Formulário digital rápido para mapear a experiência prévia do participante com análise de telemetria.
3. **Roteiro de Cenários e Tarefas:** Documento entregue ao participante contendo apenas o objetivo da análise, sem fornecer dicas de uso da interface.
4. **Planilha de Observação do Avaliador:** Utilizada exclusivamente pelo facilitador para registrar métricas quantitativas e qualitativas.
5. **Questionário Pós-teste (Escala SUS):** Formulário aplicado ao final da tarefa para medir a satisfação.
