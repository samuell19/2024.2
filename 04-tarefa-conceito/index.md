# Conceito de tarefas

## Informações gerais

- Capítulo: [Conceito de tarefas](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-04.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Samuel Medeiros de Oliveira
- matrícula: 20232014040009

## Respostas dos exercícios
1-permite que múltiplos usuários ou processos compartilhem os recursos de um único sistema de maneira eficiente. Em um ambiente de time sharing, o sistema operacional aloca pequenos intervalos de tempo (chamados de quantum) para cada processo ou usuário. Isso cria a ilusão de que todos estão utilizando o sistema simultaneamente, mesmo que na realidade o processador esteja alternando rapidamente entre eles.

2-A duração de um quantum é escolhida para equilibrar responsividade e eficiência do sistema. Quanto menores tornam o sistema mais responsivo, já que os processos alternam mais rapidamente, enquanto quanta maiores aumentam a eficiência, pois reduzem a sobrecarga de trocas de contexto. Em sistemas interativos, costuma-se usar quanta menores para respostas rápidas, enquanto sistemas de processamento em lote tendem a adotar quantidades maiores para melhor eficiência.

3-Significado dos estados:
Novo (e1): O processo foi criado, mas ainda não está pronto para ser executado.

Pronta (e2): O processo está preparado para execução e aguarda na fila de prontos.

Executando (e3): O processo está em execução no processador.

Terminada (e4): O processo foi finalizado e liberou os recursos.

Suspensa (e5): O processo está temporariamente suspenso, aguardando algum evento para voltar à fila de prontos.

Significado das transições:

t1 (Novo → Executando): O processo é escalonado para execução imediatamente após ser criado.

t2 (Executando → Terminada): O processo concluiu sua execução.

t3 (Executando → Suspensa): O processo é suspenso, geralmente aguardando algum recurso ou evento.

t4 (Suspensa → Executando): O processo suspenso é retomado e passa para o estado de execução.

t5 (Novo → Pronta): O processo é movido para a fila de prontos após ser criado.

t6 (Pronta → Executando): O processo é escalonado da fila de prontos para a execução.

Transição que falta (t6):



4-E → P: Não é possível

S → S: Possível

S → T: Possível

E → T: Possível

S → E: Possível

P → N: Não é possível

N → S: Não é possível

P → S: Não é possível

5-
[N]

[P]

[E]

[T]

[P]

[P]

[S]

[E]

[E]

[S]
