# 🗄️ SQL Dojo

Um treinador de SQL gamificado, no estilo "mapa de fases" de jogo retrô — para praticar de **SELECT básico** até **procedures, DDL, DML, DCL e TCL**, com correção automática, fila de revisão e efeitos sonoros 8-bit.

**🎮 Jogue agora:** **[andressafan.github.io/sql-dojo](https://andressafan.github.io/sql-dojo/)** · versão original: [Claude Artifact](https://claude.ai/code/artifact/da0b2f31-eac6-4d82-a8e2-1e224eb60541)

> Este projeto é uma página HTML única (`index.html`), sem dependências de build — pode ser aberta direto no navegador ou servida por qualquer host estático (inclusive GitHub Pages).

---

## O que é

O SQL Dojo é uma ferramenta de estudo que roda **inteiramente no navegador**: não tem backend, não tem banco de dados de verdade por trás. Todo o SQL é interpretado e executado por um motor escrito em JavaScript puro, construído especificamente para este projeto — com tokenizer, parser e executor próprios, sem usar nenhuma biblioteca de banco de dados.

A correção é feita **pelo resultado**, não pelo texto da consulta: duas respostas diferentes que produzem o mesmo resultado (ou o mesmo estado final dos dados, no caso de `INSERT`/`UPDATE`/`DELETE`/DDL/transações) são ambas aceitas.

## Funcionalidades

- **22 lições em 6 categorias/fases**, na ordem DQL → DML → DDL → TCL → DCL → Procedures & Cenários Reais, cada uma liberada só depois da anterior ser concluída.
- **Motor de SQL próprio**, cobrindo:
  - `SELECT` com `WHERE`, `LIKE`, `IN`, `BETWEEN`, `IS NULL`, `ORDER BY`, `GROUP BY`/`HAVING`, `INNER`/`LEFT JOIN`, agregações (`COUNT`/`SUM`/`AVG`/`MIN`/`MAX`), subconsultas escalares e com `IN`, autorrelacionamento (self-join), `COALESCE`/`IFNULL`, `UPPER`/`LOWER`/`ROUND`;
  - `INSERT`, `UPDATE`, `DELETE`;
  - `CREATE TABLE`, `ALTER TABLE` (`ADD`/`DROP`/`MODIFY COLUMN`, `ADD CONSTRAINT ... FOREIGN KEY`), `DROP TABLE`, com `PRIMARY KEY`, `NOT NULL`, `UNIQUE`, `FOREIGN KEY`;
  - `BEGIN`/`COMMIT`/`ROLLBACK` (transações de verdade, com desfazimento de estado);
  - `GRANT`/`REVOKE`;
  - `CREATE PROCEDURE`/`EXEC` com parâmetros (`@param`).
- **Correção pelo resultado**, não pelo texto — aceita qualquer consulta equivalente.
- **Fila de revisão**: errar uma questão não reseta o progresso da lição — ela só volta pra fila e reaparece mais tarde (podendo ser em outra lição), até você acertar sozinho(a).
- **Resumo de conteúdo automático** ao errar, além da dica sob demanda e da opção de ver a solução.
- **Cenários reais de empresa** na fase final, combinando várias categorias num problema só.
- **Estética "mapa de fases" de jogo retrô**: HUD estilo caixa de diálogo 16-bit, barra lateral como mapa de níveis, banner de "fase concluída" com bonequinho pixelado correndo de um nível para o outro, e sons 8-bit sintetizados na hora (sem arquivos de áudio) com botão de mudo.
- Progresso salvo no navegador (`localStorage`) — sem conta, sem servidor, sem coleta de dados.
- **Código de backup**: gera um código para copiar e colar em outro navegador/dispositivo e continuar de onde parou — sem senha e sem e-mail (o site é uma página estática pública, então isso é feito inteiramente no seu navegador).

## Como rodar localmente

Não precisa de instalação nem de build. Basta abrir o arquivo:

```bash
git clone https://github.com/andressafan/sql-dojo.git
cd sql-dojo
# abra index.html no navegador, ou sirva com qualquer servidor estático:
python3 -m http.server 8000
```

## Stack

- HTML + CSS + JavaScript puro (sem frameworks, sem bibliotecas externas de banco de dados)
- Uma única fonte externa (Google Fonts, para as tipografias)
- Todo o "banco de dados" (`ESCOLA_SQL`) e o motor de SQL vivem no próprio arquivo

## Feito com Claude

Este projeto — motor de SQL, conteúdo pedagógico das 135+ questões, interface e estética — foi criado com a ajuda do [Claude](https://claude.com), da Anthropic, em conversa com a autora.

## Licença

[MIT](LICENSE) — sinta-se à vontade para usar, adaptar e compartilhar.
