# Personas 

## Persona Primária: Anna (A Engenheira de Dados)
> 🗣️ Frase de Efeito: "Eu preciso que o vídeo e a telemetria conversem sozinhos. Meu trabalho é criar estratégia pra ganhar a corrida, não perder 20 minutos sincronizando arquivo na mão."

- **Identidade:** Anna, 23 anos, estudante de Ciência da Computação/Engenharia. Analítica, metódica e focada em eficiência.
- **Status:** Operadora do Sistema. É quem configura e extrai os dados. O sucesso da usabilidade depende dela.
- **Objetivos:** Automatizar o cruzamento de dados para gerar insights de performance e encontrar correlações científicas (ex: "ele freou tarde porque olhou tarde").
- **Habilidades:** Expert em lógica e análise de dados, mas precisa de agilidade na operação sob pressão.
- **Tarefas:** Calibrar o Eye Tracker no rosto do piloto, baixar os logs do carro, sincronizar vídeo + dados e gerar o relatório final.
- **Relacionamentos:** Traduz os dados técnicos para o Humberto e envia relatórios de fadiga para o Varela.
- **Requisitos:** Precisão absoluta nos timestamps (tempo), exportação para CSV e ferramentas de correção manual rápida.
- **Expectativas:** Quer eliminar o trabalho braçal de juntar arquivos e focar na inteligência da corrida.

## Persona Primária: Humberto (O Piloto)
> 🗣️ Frase de Efeito: "Cara, eu sei que fui lento na curva 3, só me mostra no vídeo ONDE eu olhei errado. Não tenho cabeça pra decifrar gráfico de engenharia agora."

- **Identidade:** Humberto, 24 anos, Piloto e entusiasta de tecnologia. Competitivo, visual, prático e impaciente.
- **Status:** Consumidor do Dado. Ele não opera o software, ele vê o replay na tela que a Anna mostra.
- **Objetivos:** Baixar o tempo de volta imediatamente e validar se a percepção dele bate com a realidade.
- **Habilidades:** Pilotagem extrema e reflexo rápido, mas prefere interfaces visuais diretas a planilhas complexas.
- **Tarefas:** Dirigir o veículo instrumentado e assistir ao replay da volta com o "Gaze Point" (bolinha do olho) sobreposto.
- **Relacionamentos:** Depende da Anna para traduzir os gráficos e do Varela para ajustar o treino físico.
- **Requisitos:** Interface limpa, botões grandes (para ver de longe/cansado) e feedback visual imediato (vídeo).
- **Expectativas:** Quer um "instrutor digital" que mostre o erro na cara, sem rodeios.

## Persona Secundária: Varela (O Preparador Físico)
> 🗣️ Frase de Efeito: "O braço aguenta a corrida toda, mas se a pupila dilatar de cansaço na volta 15, o tempo sobe. Eu treino o cérebro, não só o músculo."

- **Identidade:** Varela, 42 anos, Especialista em Fisiologia do Esporte e Neurociência. Experiente e observador.
- **Status:** Analista de Longo Prazo. Usa os dados para planejamento fora da pista.
- **Objetivos:** Monitorar a fadiga cognitiva (cansaço mental) do piloto ao longo do campeonato. Quer saber se o tempo de reação piorou porque o piloto cansou fisicamente ou mentalmente.
- **Habilidades:** Entende tudo de corpo humano e biometria, mas tem dificuldade com softwares de engenharia mecânica.
- **Tarefas:** Analisar os gráficos de "Carga Cognitiva" (dilatação de pupila) nas voltas finais da corrida.
- **Relacionamentos:** Cobra disciplina do Humberto e solicita relatórios consolidados para a Anna.
- **Requisitos:** Relatórios simplificados (PDF) com gráficos de tendência (Evolução x Cansaço).
- **Expectativas** Quer provar com dados que o preparo físico impacta diretamente na atenção visual do piloto.

# Mapa de Empatia

| Quadrante | Resposta (Foco na Dor e Contexto) |
| :--- | :--- |
| **O que VÊ?** | Ela vê o Humberto suado e a equipe impaciente esperando uma resposta mágica, enquanto a tela do computador mostra arquivos desconexos que não se alinham. |
| **O que OUVE?** | O som ensurdecedor dos motores no box e o rádio do Chefe de Equipe cobrando: "Anna, temos 5 minutos para o setup, cadê o dado?" |
| **O que PENSA e SENTE?** | Sente uma ansiedade paralisante e pensa: "Se o software travar ou a sincronia falhar agora, vamos perder o treino e a culpa será minha." |
| **O que FALA e FAZ?** | Ela grita "Humberto, pare de mexer a cabeça pra eu calibrar!" enquanto digita freneticamente e alterna janelas no notebook tentando salvar os dados. |
| **Quais são as DORES?** | A frustração de perder tempo precioso de pista realizando trabalho manual e repetitivo de sincronização de vídeo, correndo risco de erro humano. |
| **Quais são as NECESSIDADES?** | Uma ferramenta robusta que faça a "ingestão" automática dos dados assim que o cabo for conectado, entregando a análise pronta em segundos. |

# Contexto de Uso

*Descrição detalhada do ambiente físico, social e ambiental onde a Anna trabalha.*

"O sistema é utilizado no Pit Lane (Box) do Autódromo de Interlagos, um ambiente industrial, hostil e de altíssima pressão.

Do ponto de vista Físico e Ambiental, Anna não trabalha em uma mesa ergonômica; ela opera o notebook robusto muitas vezes apoiada em uma pilha de pneus ou agachada ao lado do carro, cercada por ferramentas e mecânicos correndo. O cheiro é uma mistura intensa de gasolina de alta octanagem e borracha queimada. A iluminação é um desafio crítico: ora o sol reflete diretamente na tela (exigindo interface de alto contraste), ora a garagem é escura. O ruído ultrapassa frequentemente os 100dB, tornando impossível qualquer feedback sonoro do sistema — tudo deve ser estritamente visual.

No aspecto Social, o clima é de urgência constante. Não há espaço para erros ou para 'ler o manual'. Anna opera o software sob o olhar julgador do Humberto (que está cheio de adrenalina) e da equipe técnica. A interação com o sistema acontece em 'surtos': momentos de calmaria quando o carro está na pista, seguidos de momentos de caos absoluto quando o carro para no box e os dados precisam ser extraídos 'para ontem'."

# Jornada do Usuário

*Narrativa fluida cobrindo os objetivos, ações, pensamentos e emoções da Anna.*

**A Corrida Contra o Relógio: A Jornada de Anna**

"A jornada começa 20 minutos antes do motor ligar. O objetivo de Anna é garantir a coleta dos dados biométricos. Ela coloca os óculos de rastreamento no rosto do Humberto e abre a aba de 'Calibração'. Seu pensamento é tenso: 'Por favor, detecte a pupila de primeira, não temos tempo'. Ela sente a pressão do piloto impaciente bufando no pescoço dela. Calibração feita, o carro vai para a pista.

Durante a sessão (20 minutos), Anna vive um 'ponto cego'. Ela não sabe se os dados estão sendo gravados corretamente. Ela sente impotência e ansiedade, torcendo para a tecnologia não falhar enquanto observa o Varela anotando tempos de volta.

O clímax acontece quando o carro retorna ao box. O Humberto sai gritando que o carro 'não faz curva'. A ação de Anna é imediata: ela conecta o cabo USB no carro. É o momento da verdade. No sistema antigo, ela sentiria pânico tentando alinhar gráficos manualmente. Mas com o novo sistema (TCC), ela clica em 'Importar Sessão'.

O sistema realiza o 'merge' automático dos dados de telemetria com o vídeo do Eye Tracker em 30 segundos. Anna vê a barra de progresso verde e sente um alívio profundo, seguido de confiança.

Na fase final, a análise, ela vira o notebook para o Humberto. O vídeo mostra a bolinha do olhar dele focada no lugar errado. Ela diz: 'Você não olhou para a zebra'. O dado é irrefutável. Humberto concorda e o Varela já planeja o próximo treino de reação. Anna encerra a jornada sentindo-se competente e essencial para a vitória da equipe."
