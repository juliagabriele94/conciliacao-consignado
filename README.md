# Conciliação do Consignado · Crédito do Trabalhador

Ferramenta para o Departamento Pessoal conferir, todo mês, os descontos de empréstimo consignado do **Crédito do Trabalhador**, contrato a contrato.

## Os dois passos

| Passo | O que confere | Quando usar |
|---|---|---|
| **1 · Emprega Brasil × Folha** | Se os descontos lançados na folha batem com os contratos da planilha baixada do portal Emprega Brasil | Antes de fechar a folha |
| **2 · Folha × Guia FGTS** | Se a guia do FGTS Digital trouxe exatamente o que foi descontado na folha | Depois do fechamento do eSocial |

Cada contrato é localizado pelo **número do contrato**. Depois, a ferramenta confere os dados do empréstimo: CPF, nome, matrícula eSocial, competência, instituição financeira (código e nome) e valor da parcela.

## O que a ferramenta faz

- Mostra a situação de cada contrato: **Conferido**, **Atenção**, **Divergente**, **Só no Emprega Brasil**, **Só na guia** ou **Só na folha**
- Explica o que verificar em cada pendência
- Permite registrar o tratamento de cada pendência, com observação
- Apresenta os totais por instituição financeira e a quantidade de colaboradores
- Gera o Excel da conferência e um relatório em PDF para arquivo e assinatura
- Transforma o PDF da guia do FGTS Digital em planilha Excel, mesmo sem fazer a conferência

## Arquivos necessários

**Planilha da folha** (Excel exportado do sistema de folha)

| Colunas obrigatórias | Colunas opcionais |
|---|---|
| Colaborador, CPF, Cod. Inst. Fin, Nro. Contrato, Valor Descontado | RE, Matrícula esocial, Evento, Inst. Financeira |

**Planilha do Emprega Brasil**: o arquivo exatamente como é baixado do portal.

**PDF do FGTS Digital**: a Relação de Trabalhadores do Crédito do Trabalhador, baixada do portal.

## Uma competência por vez

A ferramenta confere uma competência de cada vez e não guarda histórico. Ao terminar as tratativas, salve o registro da conferência em **Excel** ou em **PDF**.

## 🔒 Privacidade

**Nenhum dado sai do computador de quem usa.** As planilhas e o PDF são lidos apenas no navegador. Nenhuma informação é enviada, armazenada ou utilizada pelo site.

Os arquivos importados são apagados ao fechar a página. Os tratamentos ficam salvos só no navegador de quem usa, até clicar em **Limpar**.

---

Utiliza as bibliotecas SheetJS, PDF.js e ExcelJS.

Desenvolvido por: Julia Gabriele P. Luis
