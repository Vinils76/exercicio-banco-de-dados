 
```sql
SELECT dataDeNascimento FROM alunos
WHERE dataDeNascimento < "2009-01-01"
```

```sql
SELECT nome, primeiraNota, segundaNota, ROUND(AVG(primeiraNota + segundaNota)/2,2) AS 'Média' FROM alunos
GROUP BY nome
```

```sql
SELECT titulo, cargaHoraria, ROUND(cargaHoraria * 0.25) AS 'Limite de faltas' FROM cursos
ORDER BY titulo
```

```sql
SELECT nome, areaDeAtuacao FROM professores 
WHERE areaDeAtuacao = "desenvolvimento"
```

```sql
SELECT areaDeAtuacao, COUNT(nome) AS "Professores" FROM professores 
GROUP BY areaDeAtuacao 
```

```sql
SELECT 
    alunos.nome AS alunos, titulo, cursos.cargaHoraria AS cargaHoraria
FROM alunos INNER JOIN cursos
ON alunos.cursos_id = cursos.id
ORDER BY alunos.nome;
```

```sql
SELECT 
    professores.nome AS professores, titulo
FROM professores INNER JOIN cursos
on professores.cursos_id = cursos.id
ORDER BY professores.nome
```

```sql
SELECT alunos.nome AS titulo, professores FROM 
INNER JOIN cursos on alunos.cursos_id = cursos.id
INNER JOIN professores on professores.cursos_id = cursos.id
ORDER BY alunos.nome
```

```sql
SELECT cursos.id AS 'Quantidade de alunos', cursos.titulo FROM cursos
INNER JOIN alunos on alunos.curso_id = cursos.id
GROUP BY cursos.id DESC
```

```sql
SELECT alunos.nome AS nome, primeira_nota, segunda_nota, ROUND(AVG(primeiraNota + segundaNota)/2,2) AS 'Média', cursos.titulo FROM alunos
INNER JOIN cursos ON alunos.cursos_id = cursos.id
WHERE cursos.id = 1 OR cursos.id = 2
```

```sql
UPDATE cursos SET titulo = "Adobe XD", cargaHoraria = 15
WHERE id = 4
```

```sql
UPDATE alunos SET cursos_id = 5 WHERE
id = 10 
```

```sql
DELETE FROM alunos WHERE cursos_id = 3 
```

```sql
DELETE FROM alunos WHERE id = 11 
OR nome = 'moana' 
```

```sql
SELECT alunos.nome AS nome, cursos.titulo FROM alunos
INNER JOIN cursos ON alunos.cursos_id = cursos.id
ORDER BY alunos.nome
```

### Desafios

```sql
SELECT nome AS nome, TIMESSTAMPDIFF(YEAR, dataDeNascimento, curdate()) AS idade FROM alunos
```

```sql
SELECT nome, primeiraNota, segundaNota, (primeiraNota + segundaNota)/2 AS 'média' FROM alunos
WHERE (primeiraNota + segundaNota)/2 >= 7
```

```sql
SELECT nome, primeiraNota, segundaNota, (primeiraNota + segundaNota)/2 AS 'média' FROM alunos
WHERE (primeiraNota + segundaNota)/2 < 7
```

```sql
SELECT COUNT(nome) AS 'Qtd de alunos acima da média' FROM alunos
WHERE (primeiraNota + segundaNota)/2 >= 7 
```


