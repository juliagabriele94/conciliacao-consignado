# Conciliação do Consignado · Crédito do Trabalhador

Ferramenta web para o Departamento Pessoal conferir, todo mês, os descontos de empréstimo consignado do **Crédito do Trabalhador**, contrato a contrato.

| Passo | Compara | Quando usar |
|---|---|---|
| **1 · Emprega Brasil × Folha** | Planilha baixada do portal Emprega Brasil × planilha de descontos da folha | Antes de fechar a folha |
| **2 · Folha × Guia FGTS** | Planilha da folha × PDF da Relação de Trabalhadores do FGTS Digital | Depois do fechamento do eSocial |

O vínculo é feito pelo **número do contrato**. Depois disso são comparados CPF, nome, matrícula eSocial, competência, instituição financeira (código e nome) e valor da parcela.

## 🔒 Privacidade

**Nenhum dado sai do computador de quem usa.**

- As planilhas e o PDF são lidos apenas no navegador. Nenhuma informação é enviada, armazenada ou utilizada pelo site.
- A página não depende de serviços de terceiros: as bibliotecas estão na pasta `lib/` deste repositório e não há fontes externas, analytics ou cookies.
- O arquivo `vercel.json` aplica uma política de segurança (Content-Security-Policy com `connect-src 'none'`) que **impede a página de enviar dados pela internet**, mesmo por engano.
- Os arquivos importados não ficam salvos: ao fechar ou recarregar a página, são apagados e precisam ser importados de novo.
- Os tratamentos das pendências ficam salvos só no navegador de quem usa (`localStorage`), apenas para a competência em conferência, e são apagados no botão **Limpar**.
- O Excel e o PDF exportados contêm dados pessoais e devem ser guardados conforme as regras de cada empresa.

**Não publique neste repositório planilhas, PDFs ou exportações com dados reais.** O `.gitignore` já bloqueia esses formatos.

> Esta é uma ferramenta de apoio. A conferência final é de responsabilidade do usuário.

## Uma competência por vez

A ferramenta confere **uma competência de cada vez** e não guarda histórico. Ao concluir as tratativas, salve o registro da conferência em **Excel** (Exportar Excel) ou em **PDF** (Relatório PDF → Salvar como PDF). O relatório traz resumo, totais por instituição, pendências com tratamento e observação, contratos conferidos e campos para assinatura.

## Planilha da folha

| Obrigatórias | Opcionais |
|---|---|
| Colaborador, CPF, Cod. Inst. Fin, Nro. Contrato, Valor Descontado | RE, Matrícula esocial, Evento, Inst. Financeira |

A ordem das colunas não importa. Linhas de total e cabeçalhos repetidos são ignorados.

## Estrutura

```
index.html      a ferramenta (página única, sem build)
lib/            bibliotecas usadas, servidas pelo próprio site
vercel.json     cabeçalhos de segurança
README.md
.gitignore
```

Bibliotecas (licenças próprias, incluídas sem alteração):

- [SheetJS Community](https://sheetjs.com/) 0.18.5: leitura de Excel (Apache 2.0)
- [PDF.js](https://mozilla.github.io/pdf.js/) 3.11.174: leitura do PDF do FGTS Digital (Apache 2.0)
- [ExcelJS](https://github.com/exceljs/exceljs) 4.4.0: geração do Excel formatado (MIT)

## Publicação no Vercel

1. Envie todos os arquivos e a pasta `lib/` para um repositório no GitHub.
2. No Vercel, importe o repositório. Framework Preset: **Other**. Deixe o comando de build em branco.
3. Publique. O `index.html` e os cabeçalhos do `vercel.json` são aplicados automaticamente.

---

Desenvolvido por: Julia Gabriele P. Luis
