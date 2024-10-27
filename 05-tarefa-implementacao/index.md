# Implementação de tarefas

## Informações gerais

- Capítulo: [Implementação de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-05.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Samuel Medeiros de Oliveira
- matrícula: 20232014040009

## Respostas dos exercícios
1-O TCB (Task Control Block) é uma estrutura de dados usada pelo sistema operacional para gerenciar cada tarefa ou processo. Ele contém informações essenciais como a identificação do processo, o estado atual (executando, pronto, suspenso, etc.), registradores e o contador de programa para armazenar o contexto do processo e permitir sua retomada após interrupções.O TCB é fundamental para que o sistema operacional controle e rastreie o estado e a execução dos processos.

3-Com a linha de comando "a.out 4 3 2 1", o programa imprimirá 3 letras 'x' na tela. Isso ocorre porque serão criados 3 processos: o processo pai e 2 processos filhos, e cada um deles imprimirá uma letra 'X'

4-Threads são como pequenas tarefas dentro de um programa maior. Elas permitem que um programa faça várias coisas ao mesmo tempo, como se fossem vários programas menores rodando juntos. Isso torna os programas mais rápidos, responsivos e capazes de lidar com diversas tarefas simultaneamente.

5-Vantagens: Menor sobrecarga, compartilhamento de recursos, melhor aproveitamento de recursos, melhor responsividade.
Desvantagens: Complexidade e dificuldade de depuração

6-Tarefas sequenciais: O ganho de paralelismo é limitado quando as tarefas dependem diretamente umas das outras.
Contenção: O excesso de sincronização pode anular o benefício das threads.

7-a-Many-to-One (N:1)

b-One-to-One (1:1)


c-One-to-One (1:1)

d-Many-to-One (N:1)

e-Many-to-Many (N:M)

f-Many-to-One (N:1)

g-One-to-One (1:1)

h-Many-to-One (N:1)

i-One-to-One (1:1)
