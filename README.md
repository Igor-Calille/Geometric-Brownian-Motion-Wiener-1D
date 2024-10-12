
# Movimento Browniano Geométrico para 1 Dimensão - Processo de Wiener

Este repositório contém uma implementação em Python para simular séries temporais usando o modelo de Movimento Browniano Geométrico (GBM). O GBM é utilizado para modelar o comportamento estocástico de preços de ações ou séries temporais semelhantes ao longo do tempo.

## Visão Geral

O movimento Browniano é um conceito que se originou da física para descrever o movimento aleatório de partículas. No entanto, nos mercados financeiros, geralmente reduzimos isso para uma única dimensão, onde apenas um valor (geralmente relacionado ao preço) é analisado.

Para lidar com esse problema unidimensional, este projeto aplica o **processo de Wiener**, um método bem conhecido em finanças quantitativas, devido às suas propriedades matemáticas.

## Por que usar o GBM?

O **Movimento Browniano Geométrico (GBM)** é ideal para dados de séries temporais financeiras, pois representa um processo estocástico contínuo onde o logaritmo das variáveis aleatórias segue o processo de Wiener com uma drift.

Em termos simples, o GBM é utilizado para gerar dados sintéticos de séries temporais que podem mostrar tendências de alta ou baixa, com diferentes graus de volatilidade. Isso se encaixa quase perfeitamente para simular preços de ações, permitindo tanto tendências quanto aleatoriedade.

## Formulação

### Movimento Browniano Geométrico (GBM)

A equação do **Geometric Brownian Motion** é dada por:

\[
dS_t = \mu S_t \, dt + \sigma S_t \, dW_t
\]

Onde:
- \( S_t \) é o valor do ativo no tempo \( t \).
- \( \mu \) é o drift (taxa de crescimento esperada).
- \( \sigma \) é a volatilidade (desvio padrão dos retornos do ativo).
- \( dW_t \) é o incremento do processo de Wiener (movimento Browniano padrão).

A solução da equação estocástica para \( S_t \) é:

\[
S_t = S_0 \exp\left(\left(\mu - rac{\sigma^2}{2}
ight)t + \sigma W_t
ight)
\]

### Processo de Wiener (Movimento Browniano Padrão)

O **Processo de Wiener** \( W_t \) é definido por:

\[
dW_t \sim \mathcal{N}(0, dt)
\]

Ou seja, o incremento \( dW_t \) segue uma distribuição normal com média zero e variância \( dt \). Em termos de integração, ele é dado por:

\[
W_t = W_0 + \int_0^t dW_s
\]

Onde:
- \( W_0 = 0 \), pois o processo inicia em zero.
- \( dW_s \) representa os incrementos independentes normalmente distribuídos.

## Funcionalidades

- Simula caminhos utilizando o Movimento Browniano Geométrico (GBM)
- Permite ajuste de parâmetros como drift, volatilidade e número de caminhos
- Visualiza caminhos de séries temporais para análise

## Requisitos

- Python 3.x
- Jupyter Notebook
- NumPy
- Matplotlib

## Arquivos

- `main.ipynb`: Contém a implementação do modelo GBM e gráficos para as séries temporais.

## Como Usar

1. Instale as bibliotecas necessárias:
    ```bash
    pip install numpy matplotlib
    ```

2. Execute o Jupyter Notebook:
    ```bash
    jupyter notebook main.ipynb
    ```

3. Modifique os parâmetros no notebook para ajustar as configurações da simulação:
    - `s0`: Preço inicial
    - `mu`: Parâmetro de drift (tendência)
    - `sigma`: Volatilidade (aleatoriedade)
    - `time`: Período de tempo para a simulação
    - `paths`: Número de caminhos de simulação

4. Visualize os resultados usando os gráficos fornecidos para observar os caminhos de preço simulados ao longo do tempo.

## Licença

Este projeto está licenciado sob a licença MIT.
