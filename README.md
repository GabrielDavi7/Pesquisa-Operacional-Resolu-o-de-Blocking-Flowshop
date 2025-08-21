O código, desenvolvido em Python, implementa uma estratégia de resolução em duas fases:


**Fase Construtiva:** Utiliza a heurística NEH (Nawaz, Enscore e Ham) para gerar uma solução inicial de boa qualidade de forma rápida e eficiente. A função heuristica_neh ordena as tarefas pelo somatório de seus tempos de processamento e as insere iterativamente na melhor posição da sequência parcial.


**Fase de Refinamento:** A solução inicial da NEH é aprimorada por duas meta-heurísticas distintas:

**Busca Local com Interchange:** Uma busca local iterativa que explora a vizinhança trocando a posição de todos os pares de tarefas, sempre aplicando a melhor troca encontrada (estratégia Best Improvement) até atingir um ótimo local.

**Simulated Annealing (SA):** Uma meta-heurística que também utiliza a vizinhança de Interchange, mas com a capacidade de aceitar movimentos de piora para escapar de ótimos locais e explorar o espaço de soluções de forma mais ampla.


**Resultados Encontrados**
Os algoritmos foram testados e comparados com as melhores soluções conhecidas da literatura (BKS), usando o Desvio Percentual Relativo (RPD) como métrica. Os resultados mostraram que:NEH + Interchange foi extremamente rápido, mas ficou preso em ótimos locais de baixa qualidade, resultando em um RPD médio de 52.51% para as instâncias 50x20.NEH + Simulated Annealing apresentou um desempenho misto, com um RPD médio de 53.92%, muitas vezes não conseguindo melhorar a solução inicial da NEH.


A **conclusão** do estudo é que, embora os métodos implementados sejam funcionalmente corretos, sua abordagem single-start (refinando uma única solução inicial) é significativamente inferior a algoritmos mais complexos, como o GRASP Reativo, que é multi-start e explora milhares de soluções diferentes, alcançando resultados muito superiores. O trabalho evidencia o clássico trade-off entre tempo de execução e qualidade da solução em problemas de otimização
