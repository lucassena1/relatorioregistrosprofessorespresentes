# Sistema 21ª GRE — Acompanhamento de Aulas

Dashboard estático para acompanhar a carga horária registrada, com base inicial acumulada até o mês 09.

## Abrir localmente

O navegador precisa servir os arquivos por HTTP para carregar o CSV inicial. Na pasta do projeto, inicie um servidor local, por exemplo:

```bash
python -m http.server 8000
```

Depois abra `http://localhost:8000`.

## Atualizar os dados

1. Clique em **Importar nova planilha CSV**.
2. Selecione o arquivo CSV separado por vírgulas (também aceita ponto e vírgula).
3. Informe o mês e se o arquivo representa aquele mês ou um acumulado até ele.
4. A página recalcula os indicadores e guarda os dados no navegador atual.

O CSV inicial não tem coluna de mês; por isso a base inicial é identificada como acumulada até o mês 09. As novas importações recebem a referência escolhida pelo usuário. Os dados ficam locais naquele navegador e não são sincronizados automaticamente entre usuários.

## Gerar o PDF

Clique em **Baixar relatório em PDF** e, na janela de impressão do navegador, selecione **Salvar como PDF**. O relatório inclui indicadores, ranking e tabela de professores conforme os filtros ativos. O CPF não aparece na página nem no relatório.

## Publicar na Vercel

Publique a pasta do projeto como um site estático. O arquivo `vercel.json` já direciona as rotas para `index.html`. Mantenha a pasta `data` ao lado do HTML para o carregamento da base inicial.

## Cálculo

Percentual geral e por escola = soma de CH REGIS. ÷ soma de CH ESP. × 100. O cálculo não usa média simples dos percentuais dos professores.
