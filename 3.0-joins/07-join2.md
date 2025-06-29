## 📌 AVANÇADO DO JOIN

| Tipo         | Mantém linhas de…                                                     |
| ------------ | --------------------------------------------------------------------- |
| `INNER JOIN` | Apenas quando há correspondência nas duas tabelas                     |
| `LEFT JOIN`  | Todas as linhas da tabela da esquerda + as correspondentes da direita |
| `RIGHT JOIN` | Todas as linhas da tabela da direita + as correspondentes da esquerda |
| `FULL JOIN`  | Todas as linhas de ambas as tabelas, combinando quando possível       |

---

🔄 Quando usar cada um

- A tabela antes do JOIN é chamada de tabela da esquerda

- A tabela depois do JOIN é chamada de tabela da direita

**LOGO**

🛠️ LEFT JOIN

- Retorna todas as linhas da tabela da esquerda, mesmo que não tenha correspondência na tabela da direita.

- Para as linhas sem correspondência na direita, os campos da tabela direita virão como NULL.

🛠️ RIGHT JOIN

- Retorna todas as linhas da tabela da direita, mesmo que não tenha correspondência na tabela da esquerda.

- Para as linhas sem correspondência na esquerda, os campos da tabela esquerda virão como NULL.

🛠️ INNER JOIN

- Retorna apenas as linhas onde há correspondência em ambas as tabelas, ou seja, só quando os registros se relacionam entre si.

💡 DICA

- O tipo de JOIN que você deve usar depende do que você quer receber como resultado.

- Na prática, o LEFT JOIN costuma ser o mais utilizado, pois permite visualizar todos os dados principais (da tabela da esquerda) e complementar com os dados relacionados (da direita), quando existirem — além de facilitar a identificação de registros que não estão se relacionando corretamente entre as tabelas.
