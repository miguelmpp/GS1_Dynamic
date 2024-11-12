# ⚙️ Otimização da Alocação de Processos em Servidores

## 👥 Integrantes do Projeto
- **Matheus Farias de Lima** - RM554254
- **Miguel Mauricio Parrado Patarroyo** - RM554007

### 👨‍🏫 Professor
- Gabriel Sobral

## 📘 Descrição do Projeto
Este projeto foi desenvolvido como parte do trabalho de Engenharia de Software para otimizar a alocação de processos em múltiplos servidores, minimizando a carga total do sistema. O objetivo é ajudar uma empresa fictícia a reduzir o consumo de energia, distribuindo processos entre servidores de forma eficiente. A carga do sistema é definida pela maior carga entre todos os servidores.

Utilizamos uma abordagem gulosa para distribuir os processos, atribuindo cada processo ao servidor com a menor carga acumulada no momento, com o objetivo de balancear a carga de trabalho e reduzir o pico de uso.

## 📊 Exemplo de Problema
Dado um conjunto de processos com tempos de execução específicos e três servidores disponíveis, o objetivo é distribuir esses processos de modo que a maior carga entre os servidores seja a menor possível.

### 🔹 Exemplo de Dados de Entrada
- **Tempos dos processos**: `[4, 2, 1, 5, 9, 2, 6]`
- **Servidores**: `M1, M2, M3`

### 🔹 Exemplo de Saída Esperada
A distribuição dos processos nos servidores pode ser representada como:

- **Alocação de processos nos servidores**: `[[4, 2, 6], [2, 9], [1, 5]]`
- **Carga de cada servidor**: `[12, 11, 6]`
- **Carga do sistema** (máxima carga entre os servidores): `12`

> Neste exemplo, a carga total do sistema é `12`, que corresponde à carga do servidor `M1`, o servidor mais carregado.

## 🧠 Algoritmo Utilizado
Utilizamos uma estratégia gulosa para resolver o problema:

1. Inicializamos uma lista de servidores, cada um representado por uma lista de processos.
2. Para cada processo, atribuimos ao servidor com a menor carga atual.
3. Atualizamos a carga do servidor após cada atribuição.
4. Calculamos a carga total do sistema como o valor máximo das cargas entre os servidores.

## 💻 Código
O código principal está implementado em Python no arquivo `main.py`, contendo a função `distribuir_processos`, que recebe os tempos dos processos e o número de servidores, e retorna a distribuição de processos e a carga total do sistema.

## 📂 Estrutura do Projeto
- **main.py**: Código Python com a implementação do algoritmo de alocação de processos.
- **README.md**: Documentação do projeto.
- **Exemplos e Testes**: Exemplos de uso e resultados esperados para validação do algoritmo.

## 📋 Requisitos
- **Python** 3.x (Qualquer versão atual do Python)
- Não é necessário instalar bibliotecas adicionais.

## 🚀 Como Executar o Projeto
1. Clone o repositório:
   ```bash
   git clone https://github.com/miguelmpp/GS1_Dynamic
   ```
2. Acesse o diretório do projeto:
   ```bash
   cd repositorio
   ```
3. Execute o script principal:
   ```bash
   python main.py
   ```
O script exibirá a distribuição dos processos entre os servidores, a carga de cada servidor, e a carga total do sistema.

## 📈 Estrutura de Saída
A função `distribuir_processos` retorna:

- **Alocação de processos em cada servidor**: Uma lista de listas onde cada sublista representa os processos atribuídos a um servidor.
- **Carga de cada servidor**: Uma lista com a soma dos tempos de execução dos processos atribuídos a cada servidor.
- **Carga total do sistema**: O valor máximo entre as cargas dos servidores.

## 📝 Exemplo de Código
```python
tempos_processos = [4, 2, 1, 5, 9, 2, 6]
num_servidores = 3

servidores, carga_servidores, carga_sistema = distribuir_processos(tempos_processos, num_servidores)

print("Alocação de processos nos servidores:", servidores)
print("Carga de cada servidor:", carga_servidores)
print("Carga do sistema (máxima carga entre os servidores):", carga_sistema)
```