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
),
```
```sql
```
```sql
```