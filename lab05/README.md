# Apresentação do Lab05 - Marcadores e Taxonomia em Cypher

# Aluno
* 215743: Felipe Pacheco Manoel

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
Match (m:Marcador)-[p]->(c:Categoria {id:"Serviços"})
Return m
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
Match (m:Marcador)-[p]->(c:Categoria {id:"Serviços"})
Match (m1:Marcador)-[p1]->(c10:Categoria)-[s00]->(c00:Categoria {id:"Serviços"})
Match (m2:Marcador)-[p2]->(c21:Categoria)-[s11]->(c11:Categoria)-[s01]->(c01:Categoria {id:"Serviços"})
Return m,m1,m2
~~~
