# Paralelismo multi-core

Seu trabalho nesta atividade será criar uma implementação paralela do algoritmo de busca local. 

## Compilação do programa

Seu programa multi-core deverá ser gerado a partir do mesmo código fonte do sequencial. Ou seja, compilar com `-fopenmp` habilita o programa paralelo. Compilar sem obtem os resultados sequenciais. Caso seu programa use as chamadas do OpenMP para códigos auxiliares (alocação de memória, etc), você pode checar se seu programa foi compilado com esta flag seguindo o exemplo abaixo. 

```cpp
#ifdef _OPENMP
    // código específico para multi-core aqui
#else
    // código específico para sequencia aqui
#endif 
```

## Correção automática

Se seu programa for compilado com `-fopenmp` ele deverá rodar usando todas as CPUs pelo máximo de tempo possível. O corretor automático checará as seguintes condições:

1. o tempo de execução cai ao menos pela metade ao rodar a versão paralela. Cheque as instruções de contagem de tempo na parte de [/projetos/desempenho-sequencial](desempenho sequencial).
2. o consumo médio de CPU durante a execução do programa é maior que `75%` para cada core.
3. as mesmas checagens do algoritmo sequencial serão feitas. Ou seja, seu programa deverá funcionar de maneira idêntica ao algoritmo sequencial. **Os resultados não precisam ser exatamente os mesmos, mas o programa deverá gerar soluções com as mesmas propriedades.**

Execute o corretor de dentro da pasta `busca-local` para ver os resultados do teste multi-core.