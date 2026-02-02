# Apresentação sobre o TCC

### Membros de Equipe:
- Anna Carolina Ribeiro Pires Zomer - 22.224.017-8
- Humberto de Oliveira Pellegrini - 22.224.019-4

### Título Original do TCC: 
- Análise Pupilométrica e o Tempo de Reação em Pilotos Automotivos

### Nome do orientador:
- Prof. Dr. Victor Perrone de Lima Varela

### Previsto desenvolver Interface?
- Não

### Objetivo do trabalho?
- Validar a pupilometria como uma medida objetiva para quantificar a carga cognitiva e o esforço mental em pilotos durante a condução de alta performance.
- Analisar a relação entre a Resposta Pupilar Evocada pela Tarefa (TEPR) e o tempo de reação, comparando a eficiência neural entre pilotos novatos e profissionais para identificar padrões de expertise.
- Verificar a validade ecológica dos simuladores, comparando se os marcadores fisiológicos (carga cognitiva) obtidos no ambiente virtual se mantêm em condições reais de pista.

### Qual o produto final? 
- Um software de processamento capaz de sincronizar dados de rastreamento ocular e telemetria veicular para extrair, processar e analisar métricas fisiológicas automaticamente.

### Quem é o usuário final deste produto?
- Equipes de corrida automotiva e treinadores de pilotos de alto desempenho.

### O que o usuário recebe de benefício ao usar esse produto?
- Decodificação da Eficiência Cognitiva: Acesso a métricas objetivas que vão além do tempo de volta, permitindo entender como o piloto está processando informações (esforço mental).
- Identificação de Sobrecarga (Overdriving): Capacidade de detectar fisiologicamente quando um piloto excede sua capacidade mental, o que é um preditor crítico de erros na pista .
- Otimização do Treinamento: Dados concretos para personalizar o treinamento, focando na economia de recursos cognitivos e na melhoria da tomada de decisão sob pressão.

### Quais as funcionalidades da ferramenta (visão do usuário)?
- Sincronização de Dados: Integração temporal automática entre vídeo, dados do eye tracker e telemetria do veículo (aceleração, freio, esterçamento).
- Detecção Automática de Eventos: Identificação via software (usando YOLO e algoritmos de sinal) de eventos de interesse, como surgimento de obstáculos ou luzes de freio.
- Extração de Métricas Pupilares: Cálculo automático de marcadores como Tempo de Latência Pupilar (TLP), Pico de Dilatação e Amplitude da TEPR .
- Visualização Gráfica: Geração de gráficos que correlacionam o diâmetro da pupila com os eventos da pista para análise de desempenho .

### Quais tecnologias e ferramentas computacionais que pretendem usar neste projeto (TCC)?
- Linguagem de Programação: Python (Bibliotecas: Pandas, Matplotlib e NumPy para análise de dados).
- Visão Computacional: Modelo YOLO (You Only Look Once) para detecção de objetos em vídeo.
- Hardware de Rastreio: Eye Tracker Pupil Core (óculos de rastreio ocular).
- Ambiente de Simulação: Software Assetto Corsa (simulador) e volante Logitech G27 .

### Qual é o contexto de uso dessa aplicação?
- Ambiente: O sistema é utilizado tanto em ambientes controlados (simuladores de direção) quanto em ambientes de alta fidelidade (pistas de corrida reais).
- Situação: Durante sessões de treinamento ou testes onde o piloto é submetido a situações de alta carga cognitiva e incerteza (ex: ultrapassagens, reações a obstáculos inesperados), exigindo tomadas de decisão em frações de segundo.
