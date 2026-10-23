# App de Treinos — Documentação do projeto

Criado em 23/10/2026 com a ajuda do Claude (conversa anônima, não salva).

- **App online:** https://arturbarros25-eng.github.io/Treinos/
- **Repositório:** https://github.com/arturbarros25-eng/Treinos
- **Arquivos do app:** `index.html` (o app inteiro) e `sw.js` (funcionamento offline)

---

## 1. O que é

Um app de registro de treinos de musculação no estilo Hevy/Strong, feito para uso pessoal, sem limite de histórico e sem custo.

É um web app (PWA): roda no Safari e pode ser instalado na tela de início do iPhone, onde abre em tela cheia e funciona offline. Fica hospedado de graça no GitHub Pages.

---

## 2. Funcionalidades

- **Programas e rotinas:** dois programas pré-carregados a partir dos PDFs do treino, cada um com 6 treinos. Dá para criar, renomear e apagar programas e rotinas.
- **Próximo treino:** o app marca qual treino vem na sequência (A, B, C, A2, B2, C2) com base no último treino finalizado do programa.
- **Treino ao vivo:**
  - Cronômetro do treino.
  - Por série: número, RPE alvo (ex.: @8,5), coluna "Anterior" (carga × reps da última vez), campos de kg e reps, botão de check.
  - Atalho do check: com a carga vazia, usa a carga anterior; se a meta de reps for um número fixo, preenche as reps.
  - Para AMRAP ou faixas (7-9), é preciso digitar as reps.
  - Aceita vírgula ou ponto como decimal.
  - Dá para adicionar ou remover séries e exercícios durante o treino, sem alterar a rotina salva.
- **Descanso:** o cronômetro começa sozinho com o tempo próprio do exercício, toca um bipe no fim (se o celular não estiver no silencioso) e tem os botões −15s, +15s e Pular.
- **Super séries:** borda amarela; o descanso só começa depois do último exercício do par.
- **Técnicas:** SLOW, Rest pause, USD e 100/10 aparecem como etiqueta, com a explicação embaixo do nome. AMRAP é marcado nas reps.
- **Editor de rotina:**
  - Nome e ordem dos exercícios.
  - Reps alvo e RPE alvo por série.
  - Descanso, técnica, super série e observação.
- **Histórico:** sem limite. Mostra data, duração, volume e séries; permite repetir ou apagar um treino.
- **Progresso:** gráfico por exercício (1RM estimado pela fórmula de Epley, carga máxima ou volume) e recordes.
- **Biblioteca:** cerca de 70 exercícios por grupo muscular, mais exercícios personalizados.
- **Ajustes:**
  - Conferência dos programas (contagem e verificação das metas).
  - Botão para restaurar os programas dos PDFs.
  - Glossário de técnicas.
  - Descanso padrão do treino livre.
  - Criação de exercícios.
  - Backup (exportar e importar).
- **Ajuda:** página de instruções dentro do app (aba Ajuda), com 10 seções.
- **Visual:** tema inspirado nas cores do Gengar.
  - Fundo roxo escuro `#1D1030`, cartões `#2B1846`.
  - Lilás `#8A5CD6` / `#C9A8FF` nos destaques.
  - Vermelho `#E5404F` nos detalhes (check concluído, "Próximo", cronômetro, gráfico).
  - Ícone de fantasma no cabeçalho e abas fixas embaixo.

---

## 3. Programas carregados (dos PDFs)

**Rotina 1 — ABCABC baixo volume:** A — Legs, B — Push, C — Pull, A2 — Legs 2, B2 — Push 2, C2 — Pull 2

**Rotina 2 — Push Pull Legs:** A — Push, B — Pull, C — Legs, A2 — Push 2, B2 — Pull 2, C2 — Legs 2

### Interpretações feitas na transcrição (conferir se quiser)

- **Super séries:** eram marcadas em amarelo no PDF, cor que não aparece no texto. Foram deduzidas pelos exercícios com "sem descanso" ou "entre séries":
  - Rotina 1 — Legs 2: cadeira extensora + cadeira flexora
  - Rotina 1 — Push 2: tríceps corda + coice
  - Rotina 1 — Pull 2: rosca barra reta + rosca martelo
  - Rotina 2 — Legs: goblet squat + leg press pés altos e abertos
  - Rotina 2 — Push 2: tríceps corda + tríceps testa
  - Rotina 2 — Pull 2: rosca direta halter + rosca martelo
  - Rotina 2 — Legs 2: cadeira extensora + cadeira flexora
- **Séries em branco no PDF:** coice, flexora (Legs 2) e rosca martelo (Pull 2), todos na Rotina 1, receberam o mesmo esquema do exercício que faz par com eles.
- **RPE com erro de digitação:** a RPE "8/5" da flexora (Rotina 2, Legs) foi interpretada como 8,5.
- **Descanso não informado:** pec deck reverso e rotação externa (Rotina 2, Pull 2) ficaram com 1 min.
- **Faixas de descanso:** OHP "2-2,5 min" ficou com 2,5 min; "10-20s" (USD) ficou com 15s.
- **USD e Rest Pause sem número de séries:** ficaram com 1 série de 10 reps; dá para adicionar séries na hora.
- **Nomes unificados** para o progresso não se dividir:
  - "Rosca barra reta" = "Rosca direta barra" → Rosca direta com barra
  - "Desenvolvimento militar" = "OHP" → Desenvolvimento militar (OHP)
  - "Rosca halter simultâneo" → Rosca direta com halteres
  - "Ponte (Hip Thruster)" → Hip thrust
  - "Afundo (Bulgarian Split Squat)" (Rotina 1) → Agachamento búlgaro
  - "Flexora" (Rotina 2) → Cadeira flexora

---

## 4. Como foi publicado (passo a passo)

1. Criar uma conta gratuita em github.com (Sign up).
2. Criar um repositório: botão **+ → New repository**, nome `Treinos`, **Public**, marcar **Add a README file**, depois **Create repository**.
3. Criar o arquivo `index.html`: **Add file → Create new file**, colar o código e fazer **Commit changes**.
4. Criar o arquivo `sw.js` do mesmo jeito.
5. Ativar o Pages: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**. Em 1 ou 2 minutos aparece "Your site is live at…".

## 5. Instalação no iPhone

1. Abrir `arturbarros25-eng.github.io/Treinos/` no **Safari** (com o T maiúsculo).
2. Tocar em **Compartilhar → Adicionar à Tela de Início → Adicionar**.
3. Abrir pelo ícone uma vez com internet, para salvar o app para uso offline.
4. **Usar sempre pelo ícone.** Os dados do ícone e os do Safari ficam separados.

---

## 6. Como os dados funcionam

- **Onde ficam:** os dados ficam salvos só no celular, no armazenamento local do navegador (localStorage). Não há servidor nem banco de dados.
- **Cada usuário é independente:** cada pessoa que abre o link tem sua própria cópia, com os programas dos PDFs. O que um preenche não aparece para ninguém.
- **Repositório público:** quem tiver o link vê o app e as rotinas dos PDFs, mas nunca os treinos de outra pessoa.
- **Risco de perda:** apagar o ícone do app ou trocar de celular sem backup apaga o histórico.
- **Backup:** em Ajustes → **Exportar**, guardar o texto no Notas, Arquivos ou Drive. Para restaurar: colar no campo e tocar em **Importar**.

---

## 7. Como atualizar o app

1. No GitHub, abrir o `index.html`, tocar no lápis (Edit), apagar tudo e colar a versão nova.
2. Fazer **Commit changes**.
3. O app se atualiza na próxima vez que for aberto com internet. Os dados de todos continuam intactos.

**Atenção:** mudanças nos treinos pré-carregados só entram sozinhas para quem abrir o app pela primeira vez. Quem já usa precisa tocar em **Ajustes → Restaurar programas dos PDFs**. Isso adiciona os programas novamente, sem apagar os antigos.

---

## 8. Como pedir alterações ao Claude no futuro

Abrir uma conversa nova e enviar:

1. Este arquivo `PROCESSO.md` (ou o conteúdo dele).
2. O conteúdo atual do `index.html` (abrir no GitHub → botão **Raw** → copiar tudo).
3. Os PDFs do treino, se a alteração envolver as rotinas.

Exemplo de mensagem:

> Tenho um app de treinos em PWA hospedado no GitHub Pages. Segue a documentação (PROCESSO.md) e o código atual do index.html. Quero [descrever a alteração]. Me devolva o index.html completo atualizado, mantendo a chave de armazenamento `treinos_v2` para não perder os dados.

---

## 9. Detalhes técnicos (para quem for mexer no código)

- **Tecnologia:** HTML, CSS e JavaScript puro, num único arquivo, sem frameworks.
- **Ícones:** Tabler Icons via CDN (`cdn.jsdelivr.net/npm/@tabler/icons-webfont@3`).
- **Armazenamento:** `localStorage`, chave **`treinos_v2`**. Não mudar a chave, senão os dados somem para os usuários.
- **Estrutura dos dados (objeto `S`):**
  - `S.p`: programas `{id, n}`
  - `S.r`: rotinas `{id, p (id do programa), n, ex: [{id (nome do exercício), rest (segundos), tec, ss (super série com o próximo), nt (observação), sets: [{r (reps alvo), rpe}]}]}`
  - `S.w`: histórico, do mais novo para o mais antigo: `{id, n, t (início), e (fim), rid, pid, ex: [{id, sets: [{kg, r}]}]}`
  - `S.a`: treino em andamento, ou `null`
  - `S.c`: exercícios personalizados `{id, n, g}`
  - `S.rest`: descanso padrão
  - `S.seed`: indica se os programas já foram carregados
- **Programas pré-carregados:** ficam na constante `SEED`. Formato de cada exercício: `[nome, descanso_s, técnica, superSérie(0/1), 'séries', 'observação']`.
  - Séries: `'1x5@7.5,2x5@8'` (1 série de 5 reps @7,5 e 2 de 5 @8).
  - Barra divide RPE por série: `'3x15@8/8.5/9'`.
  - Reps podem ser `AMRAP` ou faixa `7-9`.
- **Biblioteca de exercícios:** constante `LIB`, uma linha por grupo muscular, nomes separados por `|`. O nome é o identificador do exercício.
- **Técnicas:** constantes `TN` (nomes) e `TEC` (explicações).
- **Instruções:** constante `HELP`.
- **Cores do tema:** variáveis CSS no bloco `.fr` do `<style>`.
- **sw.js:** service worker "network-first". Busca a versão mais nova quando há internet e usa o cache quando está offline.
- **Ícone do app:** gerado por canvas no carregamento (haltere lilás com dois pontos vermelhos). Se o iPhone não usar o ícone, a alternativa é subir um `icon.png` de 180×180 no repositório e apontar o `<link rel="apple-touch-icon">` para ele.

---

## 10. Ideias para o futuro

- Notas por treino ou por série
- Séries de aquecimento marcadas separadamente
- Medidas corporais e peso
- Calculadora de anilhas
- Sincronização entre aparelhos ou compartilhar treino com amigos (exigiria login e banco de dados online)
