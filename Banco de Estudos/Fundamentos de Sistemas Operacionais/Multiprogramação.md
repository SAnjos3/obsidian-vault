Apesar de ser um conceito interessante e relativamente de fácil aplicação, o modelo multi-thread levanta questões a se considerar:

- O compartilhamento de dados pode causar muitos problemas.
- Alguns desafios são solucionados com boas práticas de programação.
- Projetar programas multi-thread que cooperem para resolver o mesmo problema é muito difícil
- Em sistemas modernos, normalmente as threads estão sujeitas a um escalonador preemptivo e que não sabemos como vai se comportar
