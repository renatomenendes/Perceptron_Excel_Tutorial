# Perceptron Implementado em Microsoft Excel: Uma Abordagem Educacional para a Classificação Binária

---

### **Resumo**

Este artigo apresenta uma implementação de um Perceptron de um único neurônio utilizando Microsoft Excel como ferramenta principal. O Perceptron é um dos algoritmos mais fundamentais no aprendizado de máquina, utilizado para tarefas de classificação binária. Aqui, discutimos a teoria por trás do Perceptron, detalhamos a construção de uma planilha de Excel que simula o processo de treinamento do modelo e analisamos os resultados obtidos. A proposta tem como objetivo oferecer uma abordagem acessível para o aprendizado de redes neurais simples, permitindo uma visualização clara do processo de ajuste de pesos e bias. O estudo evidencia como o Excel, embora não sendo uma ferramenta tradicional para aprendizado de máquina, pode ser utilizado de maneira didática e eficaz em cenários educacionais.

---

### 1. **Introdução**

Nos últimos anos, o campo do **aprendizado de máquina** tem ganhado ampla popularidade devido aos avanços em algoritmos de redes neurais e ao crescimento exponencial dos dados disponíveis para treinamento de modelos. Um dos algoritmos clássicos nesse domínio é o **Perceptron**, introduzido por **Frank Rosenblatt** em 1958. O Perceptron é um algoritmo supervisionado de classificação binária e é considerado a base para redes neurais mais complexas, como as redes multicamadas.

Tradicionalmente, o Perceptron é implementado em linguagens de programação como Python ou R, utilizando bibliotecas de aprendizado de máquina. No entanto, este artigo explora uma abordagem diferente: a implementação de um Perceptron utilizando o Microsoft Excel. A escolha do Excel, ferramenta amplamente acessível e familiar, visa democratizar o acesso ao aprendizado de conceitos fundamentais em aprendizado de máquina, possibilitando que estudantes e profissionais sem formação em programação visualizem e compreendam o funcionamento de um modelo de classificação simples.

Neste artigo, descrevemos em detalhes a construção de uma planilha que simula o treinamento de um Perceptron, abordamos as questões teóricas envolvidas e discutimos os resultados obtidos. Esta abordagem é particularmente útil para ambientes educacionais, onde a interação com o modelo é essencial para o aprendizado.

---

### 2. **Teoria do Perceptron**

#### 2.1. **O Perceptron: Um Modelo Linear**

O **Perceptron** é um modelo de classificação binária, utilizado para distinguir duas classes distintas, por exemplo, "positivo" e "negativo" ou, como no caso deste estudo, "Risco" e "Imune". O Perceptron opera como um **classificador linear**, o que significa que ele é capaz de separar as duas classes se houver uma linha reta (ou hiperplano, em dimensões maiores) que as separa no espaço dos dados.

A estrutura básica de um Perceptron consiste em:
- **Entradas**: As características ou atributos dos exemplos, representados por um vetor de entradas **x**.
- **Pesos**: Cada entrada possui um peso associado que indica a importância relativa dessa característica na previsão final.
- **Bias**: Um termo adicional que ajuda a deslocar a função de ativação, permitindo que o Perceptron seja mais flexível na criação de uma fronteira de decisão.
- **Função de Ativação**: Para determinar a classe final, o Perceptron utiliza uma função de ativação que transforma o somatório ponderado das entradas em uma saída binária.

Matematicamente, o Perceptron é descrito pela seguinte equação:

\[
z = \sum_{i=1}^{n} w_i \cdot x_i + \text{bias}
\]

Onde:
- **\(x_i\)** representa os valores das entradas (genes no exemplo),
- **\(w_i\)** são os pesos ajustáveis associados a cada entrada,
- **bias** é o termo de viés,
- **z** é o somatório ponderado.

#### 2.2. **Função de Ativação**

A função de ativação usada no Perceptron é a **função degrau**. Ela produz uma saída binária (0 ou 1) com base no valor do somatório ponderado. Se o valor de \( z \) for maior que zero, a saída é 1, e se for menor ou igual a zero, a saída é 0.

\[
\text{saída} = 
\begin{cases}
1 & \text{se } z > 0 \\
0 & \text{se } z \leq 0
\end{cases}
\]

Essa saída corresponde à previsão da classe feita pelo modelo.

#### 2.3. **Treinamento do Perceptron**

O treinamento do Perceptron é um processo iterativo em que os pesos e o bias são ajustados para minimizar o erro de previsão. O algoritmo ajusta os pesos e o bias sempre que a previsão feita pelo Perceptron é diferente da classe real do exemplo. A regra de atualização é baseada no erro entre a saída prevista e o valor real da classe, com o objetivo de reduzir o erro em iterações subsequentes.

A regra de ajuste dos pesos é descrita pela equação:

\[
w_{\text{novo}} = w_{\text{atual}} + \alpha \times \text{erro} \times x_i
\]

E a regra de ajuste do bias:

\[
\text{bias}_{\text{novo}} = \text{bias}_{\text{atual}} + \alpha \times \text{erro}
\]

Onde:
- **\(\alpha\)** é a **taxa de aprendizado**, um valor fixo que controla o tamanho do passo na atualização dos pesos,
- **erro** é a diferença entre o valor real e a previsão.

O processo de treinamento continua até que o Perceptron atinja um número predeterminado de épocas ou até que o erro se torne suficientemente pequeno.

#### 2.4. **Limitações do Perceptron**

Embora o Perceptron seja eficaz para problemas **linearmente separáveis**, ele falha em lidar com problemas mais complexos, onde as classes não podem ser separadas por uma linha reta (como o problema do XOR). Para esses casos, são necessários modelos mais avançados, como o **Perceptron Multicamadas** (MLP), que podem aprender fronteiras de decisão não lineares.

---

### 3. **Metodologia**

A implementação do Perceptron foi realizada em uma planilha Microsoft Excel, permitindo a visualização de cada etapa do processo de aprendizado. O Excel foi escolhido por sua acessibilidade e pela possibilidade de criar um ambiente interativo e visual para estudantes que estão aprendendo sobre aprendizado de máquina.

#### 3.1. **Configuração dos Dados**

Os dados consistem em uma matriz de valores binários representando **genes** de pacientes. Cada linha da matriz representa um paciente e cada coluna representa um gene. A última coluna contém a **classe real** do paciente ("Risco" ou "Imune"), que foi convertida para valores binários (1 para "Risco" e 0 para "Imune").

| Registro   | Gene1 | Gene2 | Gene3 | ... | Gene9 | Classe  |
|------------|-------|-------|-------|-----|-------|---------|
| Paciente1  | 0     | 1     | 0     | ... | 1     | Risco   |
| Paciente2  | 1     | 0     | 1     | ... | 0     | Imune   |

#### 3.2. **Passo a Passo na Planilha Excel**

##### 3.2.1. **Somatório Ponderado (Coluna L)**

O somatório ponderado para cada paciente foi calculado com base nos valores dos genes e nos pesos iniciais. A fórmula no Excel para a célula **L2** foi:

```excel
=SOMA(B2*$B$16, C2*$B$17, D2*$B$18, ..., J2*$B$24) + $B$25
```

##### 3.2.2. **Função de Ativação (Coluna M)**

A função de ativação foi implementada na coluna **M**, onde o valor do somatório ponderado foi comparado com 0 para gerar uma saída binária (0 ou 1). A fórmula utilizada foi:

```excel
=SE(L2 > 0, 1, 0)
```

##### 3.2.3. **Conversão da Classe Real (Coluna N)**

A classe real foi convertida para um valor binário (1 para "Risco" e 0 para "Imune") na coluna **N**, utilizando a fórmula:

```excel
=SE(K2="Risco", 1, 0)
```

##### 3.2.4. **Ajuste dos Pesos e Bias (Colunas O a W, e Coluna X)**

Os pesos e o bias foram ajustados com base na diferença entre a previsão (coluna M) e a classe real convertida (coluna N). As fórmulas para o ajuste dos pesos (coluna O) e do

 bias (coluna X) foram:

```excel
Peso_Gene1 (Coluna O2): =B16 + $B$26*(N2 - M2)*B2
Bias (Coluna X2): =B25 + $B$26*(N2 - M2)
```

##### 3.2.5. **Taxa de Assertividade**

A taxa de acerto foi calculada com base na comparação entre as previsões e as classes reais convertidas. A fórmula utilizada foi:

```excel
{=SOMA(SE(M2:M13=N2:N13,1,0))/CONT.VALORES(N2:N13)*100}
```

#### 3.3. **Configuração dos Pesos e Bias**

Os pesos foram inicializados com valores aleatórios no intervalo entre -1 e 1, utilizando a fórmula:

```excel
=ALEATÓRIO()*2 - 1
```

O **bias** também foi inicializado com um valor aleatório dentro do mesmo intervalo. A **taxa de aprendizado** foi fixada em **0.1**.

---

### 4. **Resultados**

#### 4.1. **Treinamento e Convergência**

Após várias iterações de treinamento (épocas), o modelo Perceptron começou a ajustar seus pesos e bias de forma a minimizar o erro entre a previsão e a classe real. A taxa de acerto aumentou à medida que os pesos foram sendo atualizados, resultando em uma melhor performance do modelo.

#### 4.2. **Análise da Convergência**

O modelo apresentou rápida convergência para os dados utilizados, pois o problema era linearmente separável. Em experimentos com dados não linearmente separáveis, o Perceptron falhou em convergir, o que é esperado devido às suas limitações.

#### 4.3. **Comparação com Outros Modelos**

Comparado a modelos mais avançados, como o Perceptron Multicamadas (MLP), o Perceptron de um único neurônio mostrou limitações em problemas mais complexos. No entanto, sua simplicidade e a facilidade de visualização em ferramentas como o Excel tornam-no uma ferramenta poderosa para aprendizado introdutório.

---

### 5. **Conclusão**

O estudo demonstrou que o Microsoft Excel pode ser uma plataforma eficaz para ensinar os conceitos básicos de aprendizado de máquina, especialmente em um ambiente educacional. A implementação do Perceptron em Excel oferece uma visualização clara e detalhada do processo de treinamento e ajuste de pesos, permitindo que os estudantes interajam diretamente com os parâmetros e observem os efeitos das mudanças.

Embora o Perceptron tenha suas limitações, sua implementação em uma ferramenta como o Excel destaca seu potencial como uma primeira introdução aos conceitos de redes neurais e aprendizado de máquina. Futuras explorações podem envolver a implementação de perceptrons multicamadas ou o uso de dados mais complexos para estudar as limitações do modelo.

---

### **Referências**:

- Rosenblatt, F. (1958). The Perceptron: A probabilistic model for information storage and organization in the brain. *Psychological Review*, 65(6), 386–408.
- Goodfellow, I., Bengio, Y., & Courville, A. (2016). *Deep Learning*. MIT Press.
- Nielsen, M. (2015). *Neural Networks and Deep Learning*. Determination Press.

---

