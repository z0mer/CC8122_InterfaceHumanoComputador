# Ciclo de Vida de Engenharia de Usabilidade

### 1\. Características da Plataforma

| Característica | Descrição |
| :---- | :---- |
| Descrição do Software | Aplicação *desktop* voltada para a análise de dados de alta performance, focada na sincronização e cruzamento automático de registos de telemetria veicular (ficheiros `.ld` / `.csv`) com dados biométricos e de vídeo (ficheiros `.mp4` / `.csv` do Eye Tracker). |
| Descrição do Hardware | Computador portátil robusto e de alto desempenho operado pela engenheira de dados, aliado a sensores/óculos de captação ocular (Eye Tracker) utilizados pelo piloto durante a condução. |
| LISTA DE Capacidades da Plataforma (com explicação) | **Processamento Local (Offline):** Não depende de ligação à internet, vital em autódromos onde a rede é instável.<br>**Sincronização Automatizada:** Capacidade de alinhar as *timestamps* do automóvel com as do sensor ocular instantaneamente.<br>**Renderização Visual:** Capacidade de sobrepor mapas de calor (*heatmaps*) e o ponto do olhar (*gaze point*) em vídeos com gráficos matemáticos. |
| LISTA DE Restrições da Plataforma (com explicação) | **Luminosidade e Reflexos:** O ecrã do portátil está sujeito à luz solar direta no *pit lane*, exigindo uma interface de altíssimo contraste.<br>**Restrição Sonora:** O ruído ambiental ultrapassa frequentemente os 100dB (motores a trabalhar), o que inutiliza qualquer *feedback* sonoro. Toda a comunicação do sistema tem de ser estritamente visual. |

-----

### 2\. Princípios Gerais do Projeto

| Nome | Descrição | Link |
| :---- | :---- | :---- |
| Descrição do Contexto | Ambiente de *pit lane* (boxes) num autódromo. Cenário industrial, hostil, com pressão de tempo extrema (intervalos de 10 a 15 minutos entre treinos), ruído ensurdecedor e stresse elevado. A interação com o sistema ocorre em "surtos" de extrema urgência. | *Não aplicável* |
| Lei Geral de Proteção de Dados (LGPD) - Lei n.º 13.709/2018 | A LGPD é a legislação brasileira que regulamenta o tratamento de dados pessoais no Brasil. É importante para o projeto porque estabelece regras sobre como os dados dos usuários devem ser coletados, armazenados, processados e protegidos, garantindo sua privacidade e segurança. | [https://www.planalto.gov.br/ccivil\_03/\_ato2015-2018/2018/lei/l13709.htm](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm) |
| Lei n.º 10.098/2000 - Lei da Acessibilidade | Esta lei brasileira estabelece normas gerais e critérios básicos para a promoção da acessibilidade das pessoas com deficiência ou com mobilidade reduzida. É importante para o projeto porque define diretrizes para tornar produtos e serviços, incluindo interfaces de usuário, acessíveis a todos os usuários, independentemente de suas habilidades físicas ou cognitivas. | [https://www.planalto.gov.br/ccivil\_03/leis/l10098.htm](https://www.planalto.gov.br/ccivil_03/leis/l10098.htm) |
| ABNT NBR ISO 9241 Ergonomia da interação humano-sistema | Esta série de normas brasileiras, baseadas nas normas ISO 9241, fornece diretrizes e orientações para o design centrado no usuário de sistemas interativos, incluindo a concepção de interfaces de usuário. A parte 210 aborda o processo de design centrado no humano, enquanto a parte 11 fornece orientações específicas sobre usabilidade. Essas normas são importantes para o projeto porque estabelecem princípios e métodos para garantir que a interface do usuário atenda às necessidades e expectativas dos usuários. | [https://www.inf.ufsc.br/\~edla.ramos/ine5624/\_Walter/Normas/Parte%2011/iso9241-11F2.pdf](https://www.inf.ufsc.br/~edla.ramos/ine5624/_Walter/Normas/Parte%2011/iso9241-11F2.pdf) |
| **10 Heurísticas de Usabilidade de Jakob Nielsen** | Princípios fundamentais de *design* de interação. Essenciais para o projeto, garantindo saídas de emergência (botões para cancelar e voltar à configuração inicial) e prevenção de erros, evitando que o tempo precioso de pista seja perdido com falhas na introdução de dados. | [https://www.nngroup.com/articles/ten-usability-heuristics/](https://www.nngroup.com/articles/ten-usability-heuristics/) |

-----

### 3\. Metas de Usabilidade

**1. Qualitativo**

  * Eliminar o trabalho braçal e de tentativa e erro na sincronização de ficheiros, reduzindo drasticamente a carga cognitiva, a ansiedade e o stresse da engenheira durante o intervalo.
  * Fornecer *feedback* visual claro e imediato, permitindo que a falha de desempenho (ex: olhar para o local errado antes da travagem) seja compreendida instantaneamente, sem necessidade de interpretação matemática avançada.

**2. Quantitativo**

| Metas | Porcentagem | Justificativa |
| ----- | :---- | :---- |
| Facilidade de Aprendizagem (*Learnability*) | 15% | A equipa técnica e os pilotos precisam de dominar a ferramenta e interpretar a interface rapidamente, sem ler manuais extensos sob pressão. |
| Eficiência (Tempo de Tarefa) | 40% | O tempo é o recurso mais escasso entre os treinos. O "merge" automático tem de ser célere, poupando os minutos vitais gastos atualmente na sincronização manual. |
| Eficácia (Precisão / Taxa de Acerto) | 24% | O cruzamento da biometria pupilar com a dinâmica do automóvel tem de ser exato para gerar análises corretas de *performance*. |
| Taxa de Erros Críticos (Prevenção) | 1% | Falhas na ingestão de ficheiros ou bloqueios no sistema ("*crashes*") não podem ocorrer durante a janela curta da análise; a tolerância ao erro é praticamente nula. |
| Facilidade de Memorização (*Memorability*) | 20% | Como a utilização do sistema ocorre em picos de stresse apenas durante os fins de semana de corrida, a interface tem de ser intuitiva o suficiente para ser recordada facilmente entre os eventos. |
| **Total** | **100%** | |
