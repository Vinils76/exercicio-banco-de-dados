```sql
SELECT dataDeNascimento FROM alunos
WHERE dataDeNascimento < "2009-01-01"
```

```sql
SELECT nome, primeiraNota, segundaNota, (primeiraNota + segundaNota)/2 AS 'Média' FROM alunos
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
SELECT alunos.nome AS titulo, professores FROM alunos
INNER JOIN cursos ON alunos.cursos_id = cursos.id
INNER JOIN professores  professores.cursos_id = cursos.id
ORDER BY alunos.nome
```

```sql
SELECT cursos.id AS 'Quantidade de alunos', cursos.titulo FROM cursos
INNER JOIN alunos on alunos.curso_id = cursos.id
GROUP BY cursos.id DESC
```

```sql
SELECT alunos.nome AS nome, primeira_nota, segunda_nota, (primeira_nota + segunda_nota)/2 AS 'Média', cursos.titulo FROM alunos
INNER JOIN cursos ON alunos.curso_id = cursos.id
WHERE cursos.id = 1 OR cursos.id = 2
```

```sql
UPDATE 
```