# Entrega do Projeto - Clima Pipeline

#  Checklist da Funcionalidade 1

## - [x] O pipeline rodou para as 7 cidades e terminou com "Pipeline concluído".
![Pipeline 7 cidades](prints/Imagem1.png)

## - [x] No banco, a tabela `clima_diario` tem `sensacao_media` preenchida para Belém.
![Banco de dados Belem](prints/Imagem2.png)

## - [x] Em http://127.0.0.1:8000/docs, o endpoint `/cidades` mostra 7 cidades.
![Endpoint cidades](prints/Imagem3.png)

## - [x] Em `/clima/diario`, com `cidade = PR`, aparecem os dados de Curitiba com `sensacao_media` e `sensacao_max`.
![Dados Curitiba](prints/Imagem4.png)

## - [x] No dashboard, Belém e Curitiba aparecem na lista de cidades.
![Dashboard Lista Cidades](prints/Imagem6.png)

## - [x] No dashboard, `sensacao_media` aparece no seletor do gráfico comparativo e a linha é desenhada.
![Dashboard Sensacao Media](prints/Imagem7.png)

## - [x] Os comandos `python -m` de `cleaner`, `aggregator` e `sqlite_repository` rodam sem erro.
![Comando cleaner](prints/Imagem8.png)
![Comando aggregator](prints/Imagem9.png)
![Comando sqlite](prints/Imagem10.png)


#  Checklist da Funcionalidade 2 (Resumo do Período)

## - [x] `python -m clima_pipeline.transform.resumo` mostra os valores esperados da tabela do Passo 1.
![Teste terminal resumo](prints/Imagem11.png)

## - [x] Em `/docs`, os 4 testes do Passo 3 dão os resultados esperados (200, 200, 404, 404).
![Teste Swagger 200 normal](prints/Imagem12.png)
![Teste Swagger 200 com periodo](prints/Imagem13.png)
![Teste Swagger 404 cidade inexistente](prints/Imagem14.png)
![Teste Swagger 404 sem dados](prints/Imagem15.png)

## - [x] O `/clima/diario` continua funcionando (agora usando `_filtrar_periodo`).
![Teste diario funcionando](prints/Imagem16.png)

## - [x] As linhas que filtram por data aparecem **uma vez só** no código, dentro de `_filtrar_periodo`.
![Codigo refatorado](prints/Imagem17.png)

## - [x] O dashboard mostra os cartões de resumo de cada cidade selecionada.
![Dashboard Cartoes](prints/Imagem18.png)

## - [x] Os cartões mudam quando as datas mudam na barra lateral.
![Dashboard Cartoes Atualizados](prints/Imagem19.png)

## - [x] `docs/api/transform.rst` e `README.md` foram atualizados.
![Documentacao Atualizada](prints/Imagem20.png)

---

# Sobre o desenvolvimento

A parte mais difícil do projeto foi lidar com o banco de dados e garantir a persistência correta das informações no SQLite durante a execução do pipeline (como o preenchimento da tabela `clima_diario` e o upsert dos dados). Resolvi isso revisando com calma a lógica do `sqlite_repository`, lendo os erros no terminal com atenção e rodando os comandos módulo a módulo no terminal até confirmar que a gravação estava a funcionar sem falhas.

