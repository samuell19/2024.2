# Arquiteturas de Sistemas Operacionais

## Informações gerais

- Capítulo: [Arquitetura de SO](https://wiki.inf.ufpr.br/maziero/lib/exe/fetch.php?media=socm:socm-03.pdf)
- Disciplina: *sistemas operacionais*
- Livro: [Sistemas Operacionais: Conceitos e Mecanismos](https://wiki.inf.ufpr.br/maziero/doku.php?id=socm:start)

## Aluno

- nome: Samuel Medeiros de Oliveira  
- matrícula: 20232014040009

## Respostas dos exercícios
1- Monolítica:
Benefícios:
Desempenho: Desempenho maior, pois não tem sobrecarga
Simplicidade: A estrutura monolítica é mais simples de implementar e entender.

Deficiências:
Manutenção: Modificações em uma parte do núcleo podem afetar outras partes, tornando a manutenção complexa.
Confiabilidade: Um erro em um componente pode comprometer todo o sistema.
Portabilidade: A forte dependência do hardware dificulta a portabilidade para outras plataformas.


Microkernel:
Benefícios:
Modularidade: Cada componente do sistema opera como um processo separado, facilitando a manutenção e atualização.
Segurança: O isolamento dos componentes aumenta a segurança do sistema, pois uma falha em um componente não compromete todo o sistema.
Confiabilidade: A modularidade e o isolamento contribuem para uma maior confiabilidade.
Portabilidade: A separação entre o núcleo e os serviços facilita a portabilidade para diferentes plataformas.

Deficiências:
Desempenho: A comunicação entre os componentes via troca de mensagens pode gerar sobrecarga e reduzir o desempenho.
Complexidade: A implementação de um microkernel é mais complexa do que a de um núcleo monolítico.


Híbrida:
Benefícios:
Combinação: Combina as vantagens das arquiteturas monolítica e microkernel, permitindo otimizar o desempenho de componentes críticos e garantir a modularidade e a segurança de outros componentes.
Flexibilidade: Permite adaptar-se a diferentes cenários e requisitos de desempenho.

Deficiências:
Complexidade: A definição da fronteira entre os componentes monolíticos e microkernel pode ser complexa.
Balanceamento: É necessário encontrar um equilíbrio entre desempenho e modularidade.

2-Nem um nem outro, pois devido a presença de módulos de kernel, a modularidade de alguns de seus componentes o aproximam de um sistema híbrido. A classificação exata pode variar dependendo do ponto de vista e da versão do Linux em questão.

3-a)  Incorreto, uma máquina virtual pode executar diversas linguagens, não se limita e é abstrata


b) Correto
  
  
  c)  Incorreto, no modelo de micronúcleo, apenas as funcionalidades mais essenciais são executadas no núcleo. 
  
  
  d) Incorreto, de fato, eles são robustos e possuem alto desempenho, no entanto eles não são fáceis no quesito da manutenção, pois como são interligados, se der problema em alguma parte, esse problema pode ir para 
     diversos cantos, tornando difícil a manutenção.
  
  
  e) Correto

