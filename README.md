# Automacao de Processamento de Documentos Financeiros

Pipeline automatizado para processamento de documentos financeiros recebidos por email, desenvolvido com n8n e modelos de linguagem de grande escala (LLMs).

## Sobre o projeto

O sistema monitora uma caixa de entrada de email em busca de documentos financeiros anexados em PDF, processa cada arquivo automaticamente e registra os dados extraidos em uma planilha do Google Sheets, eliminando a necessidade de digitacao manual e reduzindo erros operacionais.

## Como funciona

Ao receber um email com anexo em PDF, o fluxo extrai o texto do documento e o envia para um modelo de IA que classifica o tipo do arquivo entre boleto, nota fiscal, fatura e combinacoes como nota fiscal com boleto ou fatura com boleto. Em seguida, um segundo modelo extrai os campos estruturados do documento, como CNPJ do fornecedor, razao social, endereco, numero da fatura, data de emissao, vencimento, valor, contrato, referencia e codigo de barras.

## Tecnologias utilizadas

- n8n para orquestracao do fluxo de automacao
- Google Gemini para classificacao e extracao de dados dos documentos
- Google Sheets como destino final dos dados estruturados
- Gmail como gatilho de entrada dos documentos

## Tipos de documentos suportados

O sistema e capaz de identificar e processar boletos bancarios, notas fiscais eletronicas (NF-e, NFCom), notas de debito, faturas de servicos e documentos hibridos que combinam mais de um tipo em um unico PDF.
