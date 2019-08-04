# sonic-player-ia
Trabalho de Computação Bioinspirada - Inteligencia Artificial que joga Sonic The Hedgehog, treinada com rede neuroevolutiva.

# ...

## Funcionamento
### O que é NEAT?
O algoritmo NEAT (Neuroevolution of Augmenting Topologies) une redes neurais com algoritmos genéticos.

### Diferença entre Fixed Topology e Augmenting Topology

Topologia fixa:

- Aprende o peso das conexões
- Estrutura (quantidade de neurônios e camadas) deve ser pré-definida por um humano 
- Isso faz com que uma estrutura boa precise ser encontrada por tentativa e erro

Topologia augmentada:
- Além de aprender o peso das conexões, também aprende qual é a quantidade de neurônios e camadas ideal


### Seleção
- Cada genoma joga o jogo
- Cada um deles tem um score baseado na sua performance durante o jogo
- A metade com maior score passa para a próxima geração
- A metade com menor score morre
- O campeão com maior score é “coroado” como o campeão

### Reprodução
- Repopular a próxima geração com genomas
- Copia o campeão da geração passada
- Clonagem (25% dos genomas da geração passada):
- Escolha aleatória entre os sobreviventes
- Crossover (75% restantes):
- Escolhe dois genomas aleatórios para cruzar
- Mutação pode ocorrer em todos os genomas.

### Crossover
- Resole o problema de combinações destrutivas
![]()
![]()

- Crossover resolve o problema com a representação da rede neural com Innovation Number e ligação entre entrada e saída
![]()
![]()

### Mutação
- Pode ser aplicado em todos os genomas.
- Tipos de mutação:
  - Mutação dos pesos
  - Mutação estrutural

### Mutação dos pesos
- Altera peso do genoma (80%):
- Ajusta o peso atual (90%) 
- Novo peso aleatório (10%)
- Enable/Disable genoma (20%)

### Mutação estrutural
- Adiciona novo genoma (5%)
- Adiciona novo nodo (3%)

### Especiação

Problema: Genomas mais complexos seriam mortos pela seleção por demorarem mais tempo para otimizar do que as redes mais simples.

Solução: Se uma rede evolui o suficiente para ser diferente estruturalmente das outras redes, ela é separada em uma nova espécie.
A cada iteração do algoritmo, checamos se todos os genomas ainda fazem parte da sua  respectiva espécie.
Se não estiver, ele fará parte de uma nova espécie.

### Morte de espécies:
- Estagnação: Não converge após n iterações
- Extinção: População muito baixa para sobreviver.


### Referencias
NEAT FlapPyBio: https://github.com/michael-iuzzolino/FlapPyBio
Hannah Le, NeuroEvolution, NEAT Algorithm and My NEAT: https://medium.com/datadriveninvestor/neuroevolution-neat-algorithm-and-my-neat-b83c5174d8b0


