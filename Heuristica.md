# 1) Avaliação de IHC através de inspeção HEURÍSTICA
**[1 solução completa por pessoa da equipe — todas as telas do projeto]**

> **NOTA:** SOMENTE VIOLAÇÕES

---

## Dez Heurísticas de Nielsen

### Descrição da avaliação

Avaliação heurística, definida por Nielsen e Molich (1994), é um método de avaliação de usabilidade onde um avaliador procura problemas de usabilidade numa interface com o usuário através da análise e interpretação de um conjunto de princípios ou heurísticas. Este método de avaliação é baseado no julgamento do avaliador.

**Sistema avaliado:** Análise Pupilométrica — Sistema de integração entre Eye Tracking (Pupil) e Telemetria (MoTeC) para análise de pilotos em ambiente de simulação/corrida.

**Telas avaliadas:**
- Tela 1: Formulário de Cadastro de Dados (FormularioDados)
- Tela 2: Visualização de Traçado e Relatórios (VisualizacaoTracado)
- Menu Principal (MenuPrincipal)

---

## Tabela 1 — Conjunto de heurísticas de Nielsen (1994) [Referência]

| # | Heurística |
|---|-----------|
| 1 | **Visibilidade do status do sistema:** O sistema deve sempre manter os usuários informados sobre o que está acontecendo através de feedback apropriado, em um tempo razoável. |
| 2 | **Compatibilidade entre sistema e mundo real:** O sistema deve utilizar a linguagem do usuário, com palavras, frases e conceitos familiares para ele, ao invés de termos específicos de sistemas. |
| 3 | **Controle e liberdade para o usuário:** Os usuários frequentemente escolhem funções por engano e necessitam de uma "saída de emergência" claramente definida, com suporte a undo e redo. |
| 4 | **Consistência e padrões:** Os usuários não deveriam ter acesso a diferentes situações, palavras ou ações representando a mesma coisa. |
| 5 | **Prevenção de erros:** Os erros são as principais fontes de frustração, ineficiência e ineficácia durante a utilização do sistema. |
| 6 | **Reconhecimento em lugar de lembrança:** Tornar objetos, ações, opções visíveis e coerentes. O usuário não deve ter que lembrar informações de uma parte do diálogo para outra. |
| 7 | **Flexibilidade e eficiência de uso:** O sistema deve ser adequado tanto para usuários inexperientes quanto para usuários experientes. |
| 8 | **Projeto minimalista e estético:** Os diálogos não devem conter informações irrelevantes ou raramente necessárias. |
| 9 | **Auxiliar os usuários a reconhecer, diagnosticar e recuperar erros:** Mensagens de erro devem ser expressas em linguagem natural, indicando precisamente o erro e sugerindo uma solução. |
| 10 | **Ajuda e documentação:** Mesmo que seja melhor que o sistema possa ser usado sem documentação, pode ser necessário fornecer ajuda e documentação. |

---

## Tabela 2 — Grau de severidade dos problemas de usabilidade

| Grau de severidade | Tipo | Descrição |
|---|---|---|
| 0 | Sem importância | Não afeta a operação da interface |
| 1 | Cosmético | Não há necessidade imediata de solução |
| 2 | Simples | Problema de baixa prioridade (pode ser reparado) |
| 3 | Grave | Problema de alta prioridade (deve ser reparado) |
| 4 | Catastrófico | Muito grave, deve ser reparado de qualquer forma |

---

## VIOLAÇÕES ENCONTRADAS

---

### Heurística 1 — Visibilidade do status do sistema

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 1.1 | Formulário de Cadastro | Durante o processamento dos dados (upload de CSVs + análise pelo backend), o sistema exibe apenas um spinner genérico com o texto "Processando dados..." sem indicar progresso parcial, percentual ou etapa atual. Processamentos longos (vários pilotos com arquivos grandes) deixam o usuário sem saber em que estágio a análise se encontra. | **3 — Grave** |
| 1.2 | Formulário de Cadastro | Após o upload do CSV do MoTeC, o sistema exibe "N voltas detectadas" somente dentro do card de upload, mas não comunica ao usuário de forma destacada que os campos MoTeC Inicial e MoTeC Final foram preenchidos automaticamente com os dados daquele arquivo. | **2 — Simples** |
| 1.3 | Menu Principal | O histórico exibido na tela inicial é estático (dados de exemplo fixos no código), não refletindo o histórico real de análises do banco de dados. O usuário não sabe se as informações exibidas são reais ou fictícias. | **3 — Grave** |

> **[Inserir print da tela de Formulário de Cadastro mostrando o estado de carregamento]**

---

### Heurística 2 — Compatibilidade entre sistema e mundo real

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 2.1 | Formulário de Cadastro | Os campos "MoTeC Inicial (s)" e "MoTeC Final (s)" utilizam a unidade "(s)" de segundos sem contexto adicional. Para usuários não técnicos, o conceito de tempo em segundos do MoTeC relativo à telemetria pode ser confuso, pois não é o mesmo que o tempo cronometrado da volta. Não há indicação de que esses valores representam o timestamp interno do sistema de telemetria. | **2 — Simples** |
| 2.2 | Formulário de Cadastro | O campo "Fixações" tem placeholder "Frame do Marco Zero (ex: 1135)" — o termo "Marco Zero" é técnico e específico do domínio do Eye Tracking, mas não há explicação do que ele representa fisicamente para um usuário iniciante. O tooltip diz "Inserir fixação ao passar pela linha de largada", porém o campo é chamado de "Fixações" (plural), criando ambiguidade semântica. | **2 — Simples** |
| 2.3 | Formulário de Cadastro | O rótulo "Volta de Ouro" é um termo interno da equipe. Não há definição ou contexto de o que representa esse conceito para alguém que utiliza o sistema pela primeira vez. | **1 — Cosmético** |

> **[Inserir print dos campos de Fixações e Volta de Ouro no Formulário]**

---

### Heurística 3 — Controle e liberdade para o usuário

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 3.1 | Visualização de Traçado | Após concluir o processamento e avançar para a tela de Visualização de Traçado, o botão "Voltar" retorna ao formulário de cadastro, mas todos os dados inseridos (seleção de sessão, pilotos, CSVs carregados e parâmetros configurados) são perdidos. Não há confirmação de saída nem persistência do estado do formulário. | **3 — Grave** |
| 3.2 | Formulário de Cadastro | Ao escolher "Cancelar" durante a criação de uma nova sessão, o campo de seleção volta para o estado inicial sem manter a sessão que estava selecionada anteriormente (se houver). | **2 — Simples** |
| 3.3 | Formulário de Cadastro | Não há possibilidade de desfazer a remoção de um piloto do formulário após clicar no ícone de lixeira. A ação é imediata e irreversível, sem confirmação. | **3 — Grave** |

> **[Inserir print do botão de remoção de piloto sem confirmação]**

---

### Heurística 4 — Consistência e padrões

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 4.1 | Formulário de Cadastro | O campo "Nome do Piloto" utiliza um `<select>` (dropdown) para pilotos existentes, enquanto a "Sessão" também usa um `<select>`. Porém, ao optar por um novo piloto, o formulário muda para um `<input>` de texto livre com botão de cancelar — padrão diferente do fluxo de nova sessão, que usa os mesmos elementos mas com comportamento visual ligeiramente distinto (layouts inconsistentes entre os dois campos). | **1 — Cosmético** |
| 4.2 | Geral | Alguns botões de ação primária usam `bg-indigo-600` (Formulário) e outros usam `bg-green-600` (Salvar nova sessão) e `bg-emerald-600` (Downloads na tela de Visualização). A cor de ação primária não é padronizada em toda a aplicação. | **2 — Simples** |

> **[Inserir print comparativo dos botões de ação primária nas telas]**

---

### Heurística 5 — Prevenção de erros

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 5.1 | Formulário de Cadastro | O campo "MoTeC Inicial (s)" e "MoTeC Final (s)" aceita qualquer valor textual digitado livremente (quando `dadosIncompletos = true`). Não há validação de formato numérico em tempo real, permitindo ao usuário inserir letras ou valores negativos antes de submeter o formulário. | **3 — Grave** |
| 5.2 | Formulário de Cadastro | Os campos de "Fixação Inicial" e "Fixação Final" (frame do Pupil Player) aceitam qualquer string sem validar se o valor final é maior que o inicial. É possível inserir uma fixação final menor que a inicial sem qualquer aviso, o que geraria erros silenciosos no processamento. | **3 — Grave** |
| 5.3 | Formulário de Cadastro | O botão "Processar e Visualizar" não está desabilitado quando nenhuma sessão foi selecionada ou quando há pilotos com dados obrigatórios ausentes. A validação só ocorre após o clique, exibindo a mensagem de erro após a tentativa. | **2 — Simples** |

> **[Inserir print do formulário com campos sem validação inline]**

---

### Heurística 6 — Reconhecimento em lugar de lembrança

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 6.1 | Formulário de Cadastro | Os campos "Fixação Inicial", "Fixação Final", "MoTeC Inicial" e "MoTeC Final" exigem que o usuário memorize os valores corretos obtidos durante a sessão de análise (frames do Pupil Player e timestamps do MoTeC) sem nenhuma referência visual ao vídeo em execução simultânea. Não há integração entre o player de vídeo e os campos de frame para sugerir ou preencher o valor atual do frame assistido. | **3 — Grave** |
| 6.2 | Visualização de Traçado | Na tela de resultados, os gráficos gerados pelo backend são exibidos como imagens estáticas (PNG) sem legendas interativas, tooltips ou identificação inline dos picos e vales. O usuário precisa lembrar o contexto da pista e da telemetria para interpretar os dados sem ajuda visual contextual. | **2 — Simples** |

> **[Inserir print da tela de formulário com o vídeo e os campos de frame lado a lado]**

---

### Heurística 9 — Auxiliar os usuários a reconhecer, diagnosticar e recuperar erros

| # | Tela | Descrição do Problema | Grau de Severidade |
|---|---|---|---|
| 9.1 | Formulário de Cadastro | Quando o backend retorna um erro de processamento, a mensagem exibida é técnica: `"Erro ao processar: [mensagem da exceção Python]"`. O stacktrace ou o nome da exceção são expostos diretamente ao usuário final, sem tradução para linguagem natural nem sugestão de como resolver o problema. | **3 — Grave** |
| 9.2 | Formulário de Cadastro | Quando pilotos são "pulados" pelo backend (sem CSV salvo no disco), a mensagem de aviso inclui o campo `motivo` vindo diretamente do backend (em inglês técnico ou com termos de sistema), sem adaptação para o contexto do usuário. | **2 — Simples** |

> **[Inserir print da mensagem de erro técnico exibida ao usuário]**

---

## 2) Indicação de Boas Práticas de Heurística — Heurísticas Não Violadas

> **NOTA:** 1 exemplo do sistema onde a heurística foi atendida (fins de aprendizado acadêmico).

---

### Heurística 1 — Visibilidade do status do sistema ✅

**Exemplo:** Durante o upload do CSV do MoTeC, o ícone de upload é substituído por um spinner animado (`Loader2` com `animate-spin`) enquanto o sistema detecta as voltas via API. Assim que a operação é concluída, o ícone retorna ao estado normal e exibe o texto "N voltas detectadas" abaixo do ícone. O usuário recebe feedback visual imediato sobre o progresso da operação de upload e detecção.

> **[Inserir print do card de upload do MoTeC com o spinner de carregamento]**

---

### Heurística 4 — Consistência e padrões ✅

**Exemplo:** Todos os cards de piloto no formulário seguem o mesmo padrão visual: gradiente de fundo `from-indigo-50 to-purple-50`, borda `border-2 border-indigo-200`, cabeçalho com ícone de usuário, número do piloto e chevron de expansão. Independentemente de quantos pilotos são adicionados, a estrutura visual de cada card permanece idêntica, proporcionando consistência e previsibilidade na navegação.

> **[Inserir print de dois ou mais cards de piloto lado a lado no formulário]**

---

### Heurística 5 — Prevenção de erros ✅

**Exemplo:** Ao selecionar um piloto já existente no banco de dados, o sistema realiza automaticamente uma busca com debounce de 500ms e preenche todos os campos (fixações, tempos de MoTeC, número da volta) com os dados já persistidos. Isso previne erros de redigitação e inconsistências entre dados novos e históricos, além de exibir um aviso amarelo informando que "os dados foram preenchidos automaticamente com o último registro".

> **[Inserir print do aviso de piloto já cadastrado com dados preenchidos automaticamente]**

---

### Heurística 7 — Flexibilidade e eficiência de uso ✅

**Exemplo:** Pilotos já processados com CSVs salvos no banco de dados podem ser reprocessados sem necessidade de novo upload dos arquivos. O sistema detecta automaticamente via campo `temCsvsSalvos` se os arquivos estão persistidos no disco do servidor, permitindo que usuários experientes apenas selecionem o piloto e cliquem em "Visualizar resultados existentes" — sem precisar reupar megabytes de dados a cada análise.

> **[Inserir print do botão "Visualizar resultados existentes" para piloto já processado]**

---

### Heurística 8 — Projeto minimalista e estético ✅

**Exemplo:** O Menu Principal apresenta exatamente 4 opções de análise (Análise Individual, Média da Volta Ideal, Anomalias Gerais, Anomalias Individuais) organizadas em um grid 2x2, sem elementos decorativos desnecessários. Cada botão contém apenas o ícone representativo, um número de identificação, o nome da funcionalidade e uma descrição curta de uma linha — informação suficiente para a tomada de decisão sem sobrecarregar cognitivamente o usuário.

> **[Inserir print do Menu Principal com os 4 cards de opção]**
