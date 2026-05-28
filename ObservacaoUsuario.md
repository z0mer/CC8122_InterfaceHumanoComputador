# Método de Avaliação de Usabilidade por Observação do Usuário
**[1 solução completa por pessoa da equipe]**
**(o número de usuários observados é igual ao número de membros da equipe)**

**Sistema avaliado:** Análise Pupilométrica — Sistema de integração entre Eye Tracking (Pupil) e Telemetria (MoTeC) para análise de desempenho de pilotos.

---

## 1) Fluxograma de Avaliação de Usabilidade por Observação do Usuário
**[1 solução por equipe]**

```
┌─────────────────────────────────────────┐
│         INÍCIO DO TESTE                 │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Preparação do ambiente                 │
│  - Servidor backend rodando             │
│  - Frontend acessível no browser        │
│  - CSVs de teste (Pupil + MoTeC)        │
│    disponíveis para o usuário           │
│  - Gravação de tela ativa               │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Apresentação do sistema                │
│  - Explicar o contexto geral            │
│  - NÃO explicar como usar              │
│  - Entregar o roteiro de tarefas        │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Preenchimento do Perfil do Usuário     │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Execução das Tarefas pelo Usuário      │
│  (pensar em voz alta — think aloud)     │
└──────────────────┬──────────────────────┘
                   │
         ┌─────────┴─────────┐
         ▼                   ▼
┌────────────────┐  ┌────────────────────┐
│  Usuário       │  │  Usuário não        │
│  completou     │  │  completou ou       │
│  a tarefa?     │  │  cometeu erros      │
│  SIM           │  │  NÃO               │
└───────┬────────┘  └─────────┬──────────┘
        │                     │
        ▼                     ▼
┌────────────────┐  ┌────────────────────┐
│  Registrar:    │  │  Registrar:         │
│  - Tempo gasto │  │  - Tipo de erro     │
│  - Satisfação  │  │  - Ponto de         │
│                │  │    abandono         │
│                │  │  - Tempo até erro   │
└───────┬────────┘  └─────────┬──────────┘
        └─────────┬───────────┘
                  │
                  ▼
┌─────────────────────────────────────────┐
│  Próxima tarefa?                        │
│  SIM → retorna para "Execução"          │
│  NÃO → segue para conclusão             │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Entrevista pós-teste (satisfação)      │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│  Compilação dos resultados              │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│         FIM DO TESTE                    │
└─────────────────────────────────────────┘
```

---

## 2) Descrição do Procedimento de Preparação do Teste
**[1 solução por equipe]**

### Passo 1: Preparação do Ambiente Técnico

Antes de iniciar o teste com o usuário, o avaliador deve garantir que:

- O servidor backend (FastAPI + Uvicorn) está rodando em `http://127.0.0.1:8000`
- O frontend (React + Vite) está acessível em `http://127.0.0.1:5173`
- O banco de dados está limpo ou contém dados de sessão de teste pré-configurados
- Os arquivos CSV de teste estão disponíveis:
  - `teste_pupil.csv` — arquivo de eye tracking no formato do Pupil Labs
  - `teste_motec.csv` — arquivo de telemetria no formato do MoTeC
  - `teste_fixations.csv` — arquivo de fixações (opcional)
- A gravação de tela está ativa (OBS, Loom ou similar)
- Um link de vídeo do Google Drive (público) está disponível para a tarefa de cadastro

### Passo 2: Lista de Tarefas que o Usuário Deve Cumprir

As tarefas foram ordenadas seguindo o fluxo natural de uso do sistema:

**Tarefa 1 — Criar uma nova sessão de análise**
> Acesse o sistema e crie uma nova sessão chamada "Sessão Teste 01".

**Tarefa 2 — Cadastrar um piloto com arquivos CSV**
> Adicione um piloto chamado "Piloto Teste" à sessão criada. Faça o upload dos arquivos CSV de Pupil e MoTeC fornecidos. Observe as voltas detectadas automaticamente e selecione a Volta 1.

**Tarefa 3 — Preencher os dados da Volta de Ouro**
> Assista ao vídeo da sessão pelo link do Drive fornecido e preencha os campos de Fixação Inicial, Fixação Final e o Frame do Marco Zero (utilize os valores indicados no roteiro: Marco Zero = 1135, Fixação Inicial = 1200, Fixação Final = 1750).

**Tarefa 4 — Processar os dados e visualizar os resultados**
> Clique no botão principal para processar os dados e navegar até a tela de Visualização de Traçado e Relatórios.

**Tarefa 5 — Baixar o relatório gerado**
> Na tela de resultados, localize o relatório PDF do piloto cadastrado e faça o download.

**Tarefa 6 — Adicionar um segundo piloto sem fazer upload de CSV**
> Volte ao formulário, selecione o piloto já existente no banco (utilize o nome de um piloto pré-cadastrado fornecido pelo avaliador) e processe os resultados sem novo upload de arquivos.

### Passo 3: Formulário de Perfil do Usuário

O formulário a seguir deve ser preenchido pelo participante antes do início das tarefas:

```
FORMULÁRIO DE PERFIL DO USUÁRIO

Nome (opcional): ___________________________________
Idade: ___________
Gênero: ( ) Masculino  ( ) Feminino  ( ) Outro  ( ) Prefiro não informar

1. Qual é o seu nível de familiaridade com sistemas de análise de dados?
   ( ) Nenhum   ( ) Básico   ( ) Intermediário   ( ) Avançado

2. Você já utilizou algum software de eye tracking ou pupilometria antes?
   ( ) Nunca   ( ) Raramente   ( ) Ocasionalmente   ( ) Frequentemente

3. Você possui experiência com softwares de telemetria de corrida (MoTeC, AiM, etc.)?
   ( ) Nunca ouvi falar   ( ) Conheço, mas nunca usei   ( ) Já usei   ( ) Uso regularmente

4. Com que frequência você utiliza aplicações web no seu dia a dia?
   ( ) Raramente   ( ) Algumas vezes por semana   ( ) Diariamente

5. Você se considera um usuário de tecnologia:
   ( ) Iniciante   ( ) Intermediário   ( ) Avançado

6. Você já participou de um teste de usabilidade antes?
   ( ) Sim   ( ) Não
```

### Passo 4: Orientações ao Participante

Antes de iniciar, o avaliador deve ler ao participante:

> "Neste teste, você irá utilizar um sistema de análise de dados chamado Análise Pupilométrica. Nosso objetivo é avaliar o sistema, não avaliar você. Não existe resposta certa ou errada. Por favor, tente verbalizar em voz alta o que você está pensando enquanto realiza cada tarefa — isso nos ajuda a entender seu raciocínio. Se tiver dificuldades, continue tentando por até 3 minutos antes de nos pedir ajuda. Você pode desistir de qualquer tarefa a qualquer momento."

### Passo 5: Materiais Necessários

- Computador com acesso ao sistema (backend + frontend em execução)
- Arquivos CSV de teste impressos/anotados (valores de referência para as tarefas)
- Roteiro de tarefas impresso para o participante
- Formulário de perfil impresso ou digital
- Cronômetro
- Ferramenta de gravação de tela ativa
- Bloco de anotações para o avaliador registrar erros e comportamentos

---

## 3) Resultados do Teste
**[1 solução por equipe]**

### Avaliação de Cada Tarefa — Usuário 1

| Tarefa | Grau de Sucesso | Total de Erros Cometidos | Tipos de Erros | Tempo Necessário | Grau de Satisfação |
|---|---|---|---|---|---|
| **1 — Criar sessão** | Sucesso Total | 0 | — | 18 segundos | Satisfeito |
| **2 — Cadastrar piloto com CSV** | Sucesso Parcial | 2 | (1) Não identificou onde fazer upload do CSV de Fixações; (1) Confusão entre CSV Pupil e CSV MoTeC | 1 min 45 seg | Confusão Moderada |
| **3 — Preencher Volta de Ouro** | Sucesso Parcial | 3 | (1) Não compreendeu o campo "Marco Zero"; (1) Tentou digitar o frame no campo MoTeC Inicial (campo errado); (1) Confundiu Fixação Inicial com Marco Zero | 2 min 30 seg | Confusão Alta |
| **4 — Processar e visualizar** | Sucesso Total | 0 | — | 12 segundos | Satisfeito |
| **5 — Baixar relatório PDF** | Sucesso Total | 1 | (1) Demorou para localizar a seção de download por estar colapsada (card expandível) | 35 segundos | Satisfação Moderada |
| **6 — Adicionar piloto existente sem CSV** | Sucesso Total | 0 | — | 22 segundos | Satisfeito |

---

### Avaliação de Cada Tarefa — Usuário 2

| Tarefa | Grau de Sucesso | Total de Erros Cometidos | Tipos de Erros | Tempo Necessário | Grau de Satisfação |
|---|---|---|---|---|---|
| **1 — Criar sessão** | Sucesso Total | 0 | — | 14 segundos | Satisfeito |
| **2 — Cadastrar piloto com CSV** | Sucesso Total | 1 | (1) Não percebeu que o CSV de Fixations é opcional, ficou procurando o arquivo | 1 min 10 seg | Satisfação Moderada |
| **3 — Preencher Volta de Ouro** | Falha | 4 | (1) Não entendeu o conceito de "Volta de Ouro"; (1) Tentou inserir o número da volta no campo de Frame; (1) Deixou o campo MoTeC Inicial vazio; (1) Tentou clicar em Processar sem preencher nenhum campo da volta | 3 min (abandonou) | Frustração Alta |
| **4 — Processar e visualizar** | Sucesso Total | 0 | — | 10 segundos | Satisfeito |
| **5 — Baixar relatório PDF** | Sucesso Total | 0 | — | 28 segundos | Satisfeito |
| **6 — Adicionar piloto existente sem CSV** | Sucesso Parcial | 1 | (1) Tentou fazer upload de CSV mesmo após ver que os dados foram preenchidos automaticamente | 40 segundos | Satisfação Moderada |

---

### Avaliação de Cada Tarefa — Usuário 3

| Tarefa | Grau de Sucesso | Total de Erros Cometidos | Tipos de Erros | Tempo Necessário | Grau de Satisfação |
|---|---|---|---|---|---|
| **1 — Criar sessão** | Sucesso Total | 0 | — | 20 segundos | Satisfeito |
| **2 — Cadastrar piloto com CSV** | Sucesso Total | 0 | — | 58 segundos | Satisfeito |
| **3 — Preencher Volta de Ouro** | Sucesso Parcial | 2 | (1) Inseriu o valor do MoTeC Final menor que o Inicial sem receber aviso; (1) Precisou ler o tooltip para entender o campo de Fixação Inicial | 1 min 50 seg | Satisfação Moderada |
| **4 — Processar e visualizar** | Sucesso Total | 0 | — | 8 segundos | Muito Satisfeito |
| **5 — Baixar relatório PDF** | Sucesso Total | 0 | — | 20 segundos | Satisfeito |
| **6 — Adicionar piloto existente sem CSV** | Sucesso Total | 0 | — | 18 segundos | Satisfeito |

---

### Links dos vídeos

- Vídeo do teste — Usuário 1: `[link do Google Drive]`
- Vídeo do teste — Usuário 2: `[link do Google Drive]`
- Vídeo do teste — Usuário 3: `[link do Google Drive]`

---

### Respostas do Formulário do Usuário

**Usuário 1:**
- Familiaridade com análise de dados: Intermediário
- Experiência com eye tracking: Nunca
- Experiência com telemetria: Já usei
- Uso de aplicações web: Diariamente
- Perfil tecnológico: Avançado
- Participou de teste de usabilidade antes: Não

**Usuário 2:**
- Familiaridade com análise de dados: Básico
- Experiência com eye tracking: Nunca
- Experiência com telemetria: Nunca ouvi falar
- Uso de aplicações web: Diariamente
- Perfil tecnológico: Intermediário
- Participou de teste de usabilidade antes: Não

**Usuário 3:**
- Familiaridade com análise de dados: Avançado
- Experiência com eye tracking: Já usei
- Experiência com telemetria: Uso regularmente
- Uso de aplicações web: Diariamente
- Perfil tecnológico: Avançado
- Participou de teste de usabilidade antes: Sim

---

### Conclusão da Avaliação por Observação do Usuário

Os testes realizados com 3 usuários revelaram padrões consistentes de dificuldade, concentrados principalmente na **Tarefa 3 (Preenchimento da Volta de Ouro)**, que apresentou os maiores índices de erro (média de 3 erros por usuário) e os maiores tempos de execução. Esta tarefa exige conhecimento prévio de dois sistemas distintos (Pupil Player e MoTeC) e correlação mental entre timestamps de telemetria e frames de vídeo, sem que a interface ofereça suporte visual para essa correlação.

A **Tarefa 1 (Criar sessão)** e a **Tarefa 4 (Processar e Visualizar)** foram concluídas com sucesso total por todos os usuários, indicando que o fluxo principal da aplicação é intuitivo para ações de alto nível. O principal problema de usabilidade identificado está na **terminologia técnica específica do domínio** (Marco Zero, Volta de Ouro, Fixação Inicial/Final, timestamps MoTeC) sem tradução para linguagem compreensível por usuários não especialistas.

**Principais problemas identificados:**
- Ausência de validação inline dos campos numéricos (MoTeC Inicial/Final, frames)
- Terminologia técnica sem contextualização adequada (Marco Zero, Volta de Ouro)
- Falta de integração visual entre o player de vídeo e os campos de frame
- Distinção insuficiente entre CSV de Fixations (opcional) e os demais CSVs (obrigatórios)

**Recomendações prioritárias:**
1. Adicionar validação em tempo real nos campos de frame e tempo, com mensagens de erro inline
2. Incluir um glossário contextual ou tutorial rápido para os conceitos de domínio (Marco Zero, Volta de Ouro)
3. Implementar um mecanismo de correlação entre o timestamp atual do vídeo e os campos de frame (ex.: botão "Capturar frame atual")
4. Diferenciar visualmente os campos obrigatórios dos opcionais com rótulos mais claros além da badge de texto
