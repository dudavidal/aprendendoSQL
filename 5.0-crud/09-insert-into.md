## 📌INSERT INTO

**INSER INTO** serve para adicionar novos registros em uma tabela.

🛠️ Detalhes importantes

- Respeite a ordem das colunas listadas.
- Separe valores por vírgula dentro do mesmo registro, e feche cada registro com parênteses.
- Se omitir uma coluna, ela precisa ter valor DEFAULT definido ou permitir NULL.

_exemplo_

INSERT INTO usuarios (nome, datacadastro)
VALUES ('THIAGO', '2025-12-30');

---

## como fazer varias adicioes?

INSERT INTO usuarios (nome,datacadastro) VALUES('THIAGO', '2025-12-30')( 'Taylor','2023-11-25');

- basta separar cada conjunto de valores por vírgula — note que só há um INSERT INTO e vários pares de parênteses.

💡 DICAS

-- Registrar a data e hora atuais
INSERT INTO usuarios (nome, datacadastro)
VALUES ('THIAGO', NOW());

- Use NOW() (ou CURRENT_TIMESTAMP) para gravar data/hora do servidor.

- Não precisa adicionar o id porque é autoincrement
