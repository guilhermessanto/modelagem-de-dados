```sql
CREATE DATABASE cinema CHARACTER SET utf8mb4;

CREATE TABLE generos(
    id INT  NOT NULL PRIMARY KEY AUTO_INCREMENT,
    generos VARCHAR(45)
);

CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTP_INCREMENT,
    titulo_do_filme VARCHAR(45) NOT NULL,
    ano_lancamento YEAR(4) NOT NULL,
    genero_id INT NOT NULL
);

ALTER TABLE filmes 
    ADD CONSTRAINT fk_filmes_generos 
    FOREIGN KEY(genero_id) REFERENCES generos(id);
```