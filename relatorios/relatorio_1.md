# Relatório — Votação simulada

## Viabilidade

- Grupo: Dupla 10
- Integrantes: Gilson Lima Mourão Filho
- Repositório: https://github.com/GilsonFilhoQA/Sistema-de-Votacao
- Stack: Java 17, Spring Boot, PostgreSQL, Maven, Swagger e Git.
- Veredito: Viável

Uma API de enquete simulada é um escopo fechado: criar votação, opções, um voto por participante, bloquear fora do período e apurar. Não há interface além do Swagger. 

## SWOT

### Forças

Regras de negócio verificáveis: voto único, período e encerramento. Spring Boot, validação e Swagger bastam para demonstrar o sistema sem frontend. A proposta declara que a votação é simulada.

### Fraquezas

Não diz como o participante se identifica, então “voto único” ainda não tem chave. PostgreSQL é cedo para o que H2 resolveria.

### Oportunidades

H2 e Swagger como interface da disciplina. Identidade do votante por um código simples, sem login completo. Uma tela mínima só se a API já estiver especificada e testada.

### Ameaças

Sem identidade, a regra de voto duplicado não é testável. Crescer para eleição real muda o problema (sigilo, auditoria, fraude).

## Stack técnica

**Parecer: Adequada com ajuste.** Java, Spring Boot, Maven e Swagger estão adequados a uma API; H2 é mais recomendado que PostgreSQL nesta etapa.

O projeto é uma API, e a stack acompanha isso. Spring Boot organiza endpoint, validação e regra de voto único. Maven constrói o projeto. O Swagger permite criar a enquete, registrar o voto e mostrar a apuração sem escrever uma tela. IntelliJ ou NetBeans servem para Java. Não vale trocar para outra linguagem.

PostgreSQL é o excesso. Enquanto os casos de voto duplicado e voto fora do período não estiverem testados, H2 entrega a mesma persistência com menos instalação. A stack recomendada nesta etapa é Java 17, Spring Boot, Maven, validação, H2 e Swagger. PostgreSQL fica para quando a API já demonstrar essas regras.

## Recomendação

**Identifiquem o participante com um código simples e demonstrem a votação pelo Swagger, com H2, antes de passar ao PostgreSQL.**

A API de votação simulada é um projeto fechado e adequado, se a constitution explicar quem é o participante. Hoje a proposta diz que cada pessoa vota uma vez, mas não diz como o sistema reconhece essa pessoa. Sem um identificador simples, a regra do voto duplicado não pode ser testada. Esse identificador pode ser um código informado na hora do voto; ainda não é necessário um login completo. Para a disciplina, o H2 guarda votações, opções e votos, e o Swagger é a interface com que a dupla demonstra criar a enquete, registrar o voto, recusar um segundo voto e recusar voto fora do período. O PostgreSQL entra depois, quando esses casos já estiverem cobertos. O PDF mistura os campos e aponta uma URL com grafia diferente da do repositório, Sistema-de-Votacao, que ainda está vazio. 
