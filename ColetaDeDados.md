# Coleta de Dados

### 1. Identificação de Necessidades dos Usuários e Requisitos de IHC

**Que dados coletar?**
* **Dados de Contexto e Ambiente:** Nível de ruído, condições de iluminação no *pit lane*, hardware utilizado (tamanho da tela do notebook, uso de mouse ou *touchpad*).
* **Dados de Tarefa e Eficiência:** Tempo médio gasto atualmente para sincronizar vídeos com dados de telemetria, taxa de erros na ingestão de arquivos, softwares mais utilizados (MoTeC, Racelogic).
* **Dados Cognitivos e Biométricos:** Principais indicadores de fadiga visual que os preparadores buscam (ex: dilatação da pupila, fixação do olhar), dificuldades de interpretação gráfica sob pressão.
* **Dados de UX (Experiência):** Maiores frustrações da equipe técnica durante o intervalo curto entre os treinos, nível de estresse com as interfaces atuais.

**De quem coletar?**
* **Engenheiros de Dados / Mecatrônicos:** (A Persona Primária). Eles que vão operar o software no limite do tempo.
* **Pilotos de Competição:** (A Persona Secundária). Eles que vão consumir o feedback visual e gerar os dados com o Eye Tracker.
* **Preparadores Físicos / Fisiologistas:** (Persona Terciária). Eles que usam os dados de carga cognitiva para planejar os treinos fora das pistas.

---

### 2. Aspectos Éticos

**Seu projeto deverá considerar aspectos éticos? Justifique usando os conceitos da aula.**

**Sim, de forma rigorosa.** O projeto lida com a captura e processamento de dados gerados por um Eye Tracker, que mapeia a direção do olhar e a dilatação da pupila do piloto. Segundo a LGPD (Lei Geral de Proteção de Dados), essas informações são classificadas como **dados sensíveis (biométricos)**, pois estão intimamente ligadas ao estado fisiológico e cognitivo do indivíduo. 

Além disso, há a questão do segredo industrial/desportivo: a telemetria do carro revela a estratégia de *setup* e o desempenho do piloto, informações sigilosas para as equipes concorrentes. Portanto, é obrigatório garantir o anonimato na divulgação científica, o armazenamento seguro desses logs e, principalmente, aplicar um **Termo de Consentimento Livre e Esclarecido (TCLE)** antes de colocar o equipamento em qualquer piloto, garantindo que ele sabe como sua biometria será usada e quem terá acesso a ela.

---

### 3. Ferramentas de Coleta de Dados (Três técnicas diferentes)

Para não ficar só no achismo, vamos usar três frentes de ataque para descobrir o que a equipe realmente precisa:

#### Técnica 1: Questionário Online (Pesquisa Quantitativa)
* **Objetivo de aplicação:** Alcançar um volume maior de pilotos e engenheiros de diversas categorias (Kart, Fórmula Vee, Porsche Cup) para mapear o tempo perdido com softwares atuais e validar se a dor da sincronização é generalizada.
* **Como aplicar:** O link será distribuído via WhatsApp e grupos de automobilismo. O ideal é que seja responsivo (para responderem no celular pelo box) e leve no máximo 3 minutos. As perguntas devem ser, em sua maioria, fechadas (escala Likert ou múltipla escolha) para facilitar a tabulação matemática.
* **Instrumento:** Formulário via *Google Forms*.
  * *Exemplo de questões:* 1) "Qual software você utiliza para telemetria?"
    2) "Em uma escala de 1 a 5, quão frustrante é sincronizar vídeo e dados manualmente?"
    3) "Quanto tempo você tem disponível entre as baterias para analisar os dados do carro?"

#### Técnica 2: Entrevista Semiestruturada (Pesquisa Qualitativa)
* **Objetivo de aplicação:** Aprofundar na "dor" da Engenheira de Dados. Entender o caos emocional, o fluxo de pensamento dela no momento do stresse e como ela gostaria que o cruzamento do olhar com o freio acontecesse.
* **Como aplicar:** Sessões de 30 a 40 minutos via Teams/Google Meet, gravadas (com consentimento). O entrevistador terá um roteiro de tópicos em mãos, mas deixará a conversa fluir livremente, fazendo perguntas abertas ("Me conte mais sobre o dia que você perdeu os dados...").
* **Instrumento:** Roteiro de Entrevista.
  * *Tópicos:* 1) Rotina de extração de dados no *pit lane*.
    2) Maiores erros cometidos pela interface do MoTeC.
    3) Expectativas sobre a correlação "Atenção Visual vs. Dinâmica do Carro".

#### Técnica 3: Observação Direta In Situ (Shadowing)
* **Objetivo de aplicação:** Descobrir os problemas que o usuário não sabe que tem ou esquece de mencionar na entrevista. Ver a interação no "habitat natural" sob pressão real.
* **Como aplicar:** O pesquisador vai até o autódromo em um dia de treino (Track Day). Ele ficará posicionado atrás do engenheiro no box ("sendo a sombra" dele), em silêncio absoluto. Anotará em uma prancheta o barulho, as interrupções que o engenheiro sofre, as vezes que ele erra o clique devido à pressa ou reflexo do sol na tela.
* **Instrumento:** Planilha de Observação Heurística.
  * *Campos da planilha:* 1) Ação observada.
    2) Tempo gasto.
    3) Interrupções/Gargalos físicos (sol, barulho, sujeira).
    4) Dificuldades de navegação nas janelas dos softwares atuais.
