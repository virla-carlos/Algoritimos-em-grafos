# Grafos e Algoritmos em Python

Projeto acadêmico desenvolvido para estudar a representação de grafos e a aplicação de algoritmos de busca, caminhos mínimos e árvore geradora mínima. Os programas recebem os dados pelo terminal e exibem os resultados de forma textual.

## Funcionalidades

| Recurso | Descrição |
|---|---|
| Matriz de adjacência | Representa as ligações entre os vértices por uma matriz de zeros e uns. |
| Lista de adjacência | Exibe os vizinhos de cada vértice. |
| Busca em profundidade (DFS) | Explora um caminho antes de retornar para visitar outros vizinhos. |
| Busca em largura (BFS) | Visita os vértices por níveis a partir do vértice inicial. |
| Dijkstra | Calcula as menores distâncias a partir de um vértice em grafos com pesos não negativos. |
| Prim | Encontra uma árvore geradora mínima em um grafo não orientado e conexo. |

As implementações incluem exemplos de grafos orientados e não orientados. As validações variam entre os programas, incluindo verificação de vértices, arestas repetidas e pesos válidos nas versões que oferecem esses controles.

## Tecnologias

- Python 3.
- `heapq`, da biblioteca padrão, para filas de prioridade em Prim e Dijkstra.
- Listas, dicionários e conjuntos para representar e percorrer os grafos.

Não é necessário instalar bibliotecas externas.

## Como executar

1. Baixe ou clone o repositório.
2. Abra a pasta no VS Code ou em outro editor.
3. Abra um terminal na pasta do programa desejado.
4. Execute o arquivo Python:

```bash
python nome_do_arquivo.py
```

Substitua `nome_do_arquivo.py` pelo nome do script que deseja executar. No Windows, também é possível utilizar:

```powershell
py nome_do_arquivo.py
```

Informe um valor por vez e pressione **Enter** após cada entrada. A identificação dos vértices depende do programa: as versões de matriz, lista, DFS e BFS usam números de **1 a n**; a versão de Prim usa **0 a n − 1**; as versões de Dijkstra recebem nomes, como **A, B, C e D**.

## Exemplo: grafo orientado com DFS e BFS

No programa com menu, estão disponíveis as opções:

```text
1 - Criar Grafo
2 - Mostrar Grafo
3 - Busca em Profundidade
4 - Busca em Largura
5 - Sair
```

Selecione a opção **1**, informe **4 vértices** e **4 arestas** e cadastre as ligações nesta ordem:

| Aresta | Origem | Destino |
|---|---:|---:|
| 1 | 1 | 2 |
| 2 | 1 | 3 |
| 3 | 2 | 4 |
| 4 | 3 | 4 |

Na opção **2**, o resultado esperado é:

```text
MATRIZ DE ADJACÊNCIA
[0, 1, 1, 0]
[0, 0, 0, 1]
[0, 0, 0, 1]
[0, 0, 0, 0]

LISTA DE ADJACÊNCIA
1 -> [2, 3]
2 -> [4]
3 -> [4]
4 -> []
```

Selecione a opção **3** e use o vértice inicial **1**:

```text
BUSCA EM PROFUNDIDADE:
1 2 4 3
```

Selecione a opção **4** e use o vértice inicial **1**:

```text
BUSCA EM LARGURA:
1 2 3 4
```

A ordem de visita depende da ordem em que os vizinhos foram cadastrados. As buscas visitam apenas os vértices alcançáveis a partir do vértice inicial, respeitando o sentido das arestas.

## Exemplo: Dijkstra

Cadastre os vértices **A, B, C e D** e as seguintes **5 arestas**:

| Origem | Destino | Peso |
|---|---|---:|
| A | B | 2 |
| A | C | 5 |
| B | C | 1 |
| B | D | 6 |
| C | D | 3 |

Com **A** como vértice inicial, as menores distâncias esperadas são:

```text
A -> A = 0
A -> B = 2
A -> C = 3
A -> D = 6
```

Essas distâncias são as mesmas para as versões orientada e não orientada com os dados deste exemplo. Na versão orientada com validação, vértices inalcançáveis são exibidos como `Sem caminho`.

## Exemplo: Prim

Informe **4 vértices**, identificados de **0 a 3**, e **5 arestas**:

| Origem | Destino | Peso |
|---|---|---:|
| 0 | 1 | 2 |
| 0 | 2 | 3 |
| 1 | 2 | 1 |
| 1 | 3 | 4 |
| 2 | 3 | 5 |

Resultado esperado:

```text
=== ÁRVORE GERADORA MÍNIMA ===
Aresta: 0 -- 1, Peso: 2
Aresta: 1 -- 2, Peso: 1
Aresta: 1 -- 3, Peso: 4
Peso total da AGM: 7
Quantidade de arestas da AGM: 3
```

Caso o grafo não seja conexo, o programa informa que não é possível gerar uma árvore geradora mínima.

## Conceitos estudados

- Representação de grafos orientados e não orientados.
- Matrizes e listas de adjacência.
- Recursão na busca em profundidade.
- Uso de fila na busca em largura.
- Filas de prioridade com `heapq`.
- Caminhos mínimos e árvore geradora mínima.
- Entrada de dados e validações no terminal.

## Observações

Em grafos orientados, uma ligação de A para B não implica uma ligação de B para A. Em grafos não orientados, a ligação é registrada nos dois sentidos.

Os exemplos são didáticos. Nas versões sem validação da quantidade máxima de arestas, informe uma quantidade compatível com os vértices e com a proibição de laços e arestas repetidas. Os scripts com conversão direta por `int(input(...))` exigem entradas numéricas válidas.

## Autor

Carlos Alberto Virla Neto — estudante de Ciência da Computação.

