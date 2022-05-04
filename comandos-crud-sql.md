# Comandos AWL para CRUD - Referência 

## Resumo

- C -> Create (inserir dados)
- R -> Read (ler dados)
- U -> Update (atualizar dados)
- D -> Delete (excluir dados)

## INSERT

## FABRICANTES

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```
## PRODUTOS
```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'UltraBook',
    'UltraBook Asus com processador Intel core i12, memória RAM de 16GB e Windows 11',
    6500.99,
    7,
    1
);
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'tablet Android',
    'Tablet com a versão 12 sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB',
    4999,
    3,
    5
);

INSERT INTO proutos(nome, descricao, preco, quantidade, fabricante_id) VALUES 
('Geladeira',
    'Refrigerador Frost-free com acesso à Internet daas coisas e bla bla bla',
    1500,
    10,
    6
),
( 'Iphone 13 Pro Max',
    'Altura durabilidade, processador Bionic 14, 128GB de armazenamento, 6GB de RAM e caro pra caramba',
    6999.99,
    3,
    3

),
(
    'iPad mini',
    'Tablet Apple com tela retina display 4k, memoria interna de 64GB, acesso ao iCLound.',
    5000,
    8,
    3   
);
INSERT INTO protutos(nome, descricao, preco, quantidade, fabricante_id) VALUES 
('Xbox',
    'Console de última geração com acesso aos melhores jogos e bla bla bla',
    2500,
    6,
    7 
),
( 'UltraBook',
    'Equipamento com processador AMD Ryzen5, 12GB RAM, placa de video RTX ',
    4500.68,
    12,
    8
);

```
## SELECT
### Ler dados da tabela produtos
```sql
SELECT * FROM produtos;
SELECT nome, preco FROM produtos;
SELECT nome FROM produtos WHERE preco < 5000;
SELECT nome, descricao FROM produtos WHERE fabricante_id = 3;
```
### Operadores Lógicos:
```sql
SELECT * FROM produtos WHERE preco >= 5000 AND preco < 8000;
SELECT nome, preco FROM produtos WHERE fabricante_id = 3 OR fabricante_id = 7;
SELECT nome , preco, quantidade FROM produtos WHERE * NOT fabricante_id = 3;
SELECT nome , preco, quantidade FROM produtos WHERE fabricante_id != 3; # varsao 2
SELECT nome , preco FROM produtos WHERE fabricante_id IN(3,8);

```
## FILTROS
```sql
SELECT nome, preco FROM produtos ORDER BY nome; -- padrão ASC
SELECT nome, preco FROM produtos ORDER BY nome DESC; -- padrão DECRESCENTE 
-- LIKE
SELECT nome, descricao FROM produtos WHERE descricao LIKE '%processador%'; 
-- % operador coringa (significa qualquer texto)
```
### OPERAÇÕES e FUNÇÕES de agregação 
```sql
SELECT SUM(preco) FROM produtos; -- SOMA
SELECT SUM(preco) AS TOTAL FROM produtos; -- ALIAS (apelido)
SELECT SUM(quantidade) AS "Quantidade em estoque" FROM produtos;
SELECT SUM(quantidade) AS "Quantidade em estoque" FROM produtos WHERE fabricante_id = 3;

--  AVG (AVERAGE) MÉDIA
SELECT AVG(preco) AS "Média dos preços" FROM produtos;
SELECT ROUND(AVG(preco)) AS "Média dos preços" FROM produtos; -- média arredondada 
SELECT COUNT(id) AS "Quantidade produtos" FROM prod2utos;
-- DISTINCT pe um comando para evitar a duplicidade na contagem em campos que não são chave-primária 
SELECT COUNT(DISTINCT fabricante_id) AS "Quantidade fabricantes" FROM produtos;

SELECT nome, preco , quantidade,(preco*quantidade) AS Total FROM produtos;
```
### Agrupamentos
```sql
SELECT fabricante_id, SUM(preco) AS Total FROM produtos GROUP BY fabricante_id;
-- GROUP BY permite segmentar resultados da consulta. neste caso, somamos todos os preços e segmentos/agrupamentos por cada fabricante.

```
## UPDATE  (SEMPRE COM WHERE)
### Atualizar dados de uma tabela 
```sql
UPDATE fabricantes SET nome = 'Microsoft Brasil' WHERE id = 7;

UPDATE produtos SET preco = 5200 WHERE id = 7;
UPDATE produtos SET quantidade = 15 WHERE fabricante_id = 1 OR fabricante_id = 3;
```
<!-- Mudar o preço do Ultrabook da positivo para 5200.00 -->
<!-- Mudar a quantidade dos produtos da Asus para 15 -->
## Excluir dados de uma tabela
```sql
DELETE FROM farbicantes WHERE id = 4;

DELETE FROM produtos WHERE preco <= 2000 AND preco > 500;
```

```sql
INSERT INTO generos (generos) VALUES('Aventura');
INSERT INTO generos (generos) VALUES('Romance'),('Ação'),('Comédia'),('Animação');
INSERT INTO filmes(titulo_do_filme, ano_lancamento, genero_id)VALUES(
    'Indiana Jones e o Templo da perdição',
    1984,
    1
);
INSERT INTO filmes(titulo_do_filme, ano_lancamento, genero_id) VALUES(
    'Uncharted Fora do mapa',
    2022,
    1
);

INSERT INTO filmes(titulo_do_filme,ano_lancamento, genero_id) VALUES(
    'Red: Crescer é uma fera',
    2022,
    5
),
(
    '1917',
    2019,
    3
),
(
    'O Auto da Compadecida',
    2000,
    4
),
(
    'Sr. & Sra. Smith',
    2005,
    1
),
(
    'Titanic',
    1997,
    2
),
(
    'Romeu e Julieta',
    1968,
    2
);


SELECT titulo_do_filme FROM filmes;

SELECT titulo_do_filme, genero_id FROM filmes;
SELECT titulo_do_filme FROM filmes WHERE genero = 3;
```