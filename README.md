# Sistema 21ª GRE — acompanhamento mensal

Projeto estático para publicar na Vercel. O filtro já mostra todos os meses de fevereiro a dezembro de 2026. A base inicial continua identificada separadamente como acumulada até setembro; não é usada como dado de um mês específico.

## Importar CSVs no navegador

Use **Importar CSVs mensais** e selecione um ou mais arquivos. O sistema tenta identificar o mês no nome, por exemplo `2026-02-fevereiro.csv`. Se não identificar, escolha o mês na lista para cada arquivo. É aceito um arquivo por mês; uma nova importação pergunta antes de substituir apenas o mês correspondente.

As importações feitas pelo botão ficam guardadas apenas no navegador usado para importá-las. Para disponibilizar arquivos mensais a todos os usuários do site, adicione os CSVs à pasta do mês correspondente em `data/2026/`, atualize o manifesto e publique novamente na Vercel.

## Publicar arquivos mensais na Vercel

Cada mês já tem uma pasta própria em `data/2026/`, e o manifesto está pré-configurado para procurar um arquivo CSV em cada pasta. Copie os arquivos para os caminhos abaixo, mantendo os nomes indicados:

- `data/2026/02-fevereiro/fevereiro.csv`
- `data/2026/03-marco/Março.csv`
- `data/2026/04-abril/abril.csv`
- `data/2026/05-maio/Maio.csv`
- `data/2026/06-junho/junho.csv`
- `data/2026/07-julho/julho.csv`
- `data/2026/08-agosto/agosto.csv`
- `data/2026/09-setembro/setembro.csv`
- `data/2026/10-outubro/outubro.csv`
- `data/2026/11-novembro/novembro.csv`
- `data/2026/12-dezembro/dezembro.csv`

Se os nomes dos arquivos forem mantidos, não é necessário alterar o manifesto. Se renomear um CSV, ajuste o caminho do mês correspondente em `data/2026/manifest.json`. Depois, publique novamente o projeto na Vercel. Os meses sem arquivo continuarão aparecendo como **Sem arquivo**.

## Formato dos CSVs

O mínimo para percentuais é ter `ESCOLA`, `PROFESSOR` e um par de valores: `CH REGIS.` e `CH ESP.`, ou `AULAS REGISTRADAS` e `AULAS PREVISTAS`. Para mostrar aulas pendentes, inclua `AULAS PENDENTES` ou os campos `AULAS PREVISTAS` e `AULAS REGISTRADAS`. Sem esses campos de aulas, o sistema mostra **CH pendente (h)** calculada pela diferença entre CH esperada e CH registrada. O CPF não é armazenado pela página.

Cada arquivo precisa conter resultados do próprio mês. A base fornecida, acumulada até setembro, permanece em `data/base-inicial.csv` e aparece como visão acumulada separada.

## PDF e faixas de cor

O relatório de impressão inclui ranking, professores e resultados mensais de fevereiro a dezembro. Selecione **Salvar como PDF** e habilite a impressão de gráficos de fundo para preservar as cores: verde a partir de 100%, laranja de 97% a menos de 100% e vermelho abaixo de 97%.
