# Registro do ciclo de TDD

## Comportamentos escolhidos

- Cobrar a taxa inicial para uma distância de 2 km.
- Acrescentar R$ 2,00 por quilômetro acima de 3 km.
- Conceder entrega gratuita para pedidos a partir de R$ 100,00.

## Ciclo 1 — taxa inicial até 3 km

### Red

**Teste criado:** `test_calcula_taxa_de_entrega_ate_tres_km`

**Motivo da falha:** a função `calcular_taxa_entrega` ainda não existia no módulo `src.pedido`.

### Green

**Implementação realizada:** criada a função retornando a taxa fixa de R$ 5,00 para o primeiro cenário.

## Ciclo 2 — quilômetro excedente

### Red

**Teste criado:** `test_acrescenta_dois_reais_por_km_excedente`

**Motivo da falha:** a implementação inicial ainda retornava R$ 5,00 para 4 km, mas o valor esperado era R$ 7,00.

### Green

**Implementação realizada:** acrescentados R$ 2,00 para cada quilômetro acima de 3 km.

## Ciclo 3 — entrega gratuita

### Red

**Teste criado:** `test_isenta_entrega_para_pedidos_a_partir_de_cem_reais`

**Motivo da falha:** sem a regra de gratuidade, um pedido de R$ 100,00 a 5 km resultava em R$ 9,00, mas o esperado era R$ 0,00.

### Green

**Implementação realizada:** adicionada a verificação de que pedidos com total maior ou igual a R$ 100,00 retornam taxa zero.

## Refactor

**Melhoria realizada:** a função foi organizada com a regra de gratuidade primeiro, seguida da regra de distância, mantendo cada comportamento explícito e sem alterar os resultados dos testes.

**Resultado final:** toda a suíte foi executada com `python -m pytest -v`: 7 testes passaram.
