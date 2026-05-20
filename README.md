# 🌸 Classificador de Flores Iris com Scikit-Learn e Streamlit

Projeto didático para demonstrar, na prática, o fluxo básico de uma aplicação de **Machine Learning** usando Python.

A proposta é desenvolver o projeto em duas etapas principais:

1. Primeiro, será feito um **Jupyter Notebook** para treinar e avaliar um modelo de Machine Learning com o dataset Iris.
2. Depois, o modelo será aplicado em um **site feito com Streamlit**, uma aplicação real onde o usuário informa as características da planta e recebe uma previsão da espécie.

---

## 🎯 Objetivo do projeto

O objetivo é mostrar aos alunos como um modelo de Machine Learning pode sair do ambiente de estudo e ser usado em uma aplicação interativa.

Durante o projeto, serão trabalhados conceitos como:

- aprendizado supervisionado;
- classificação;
- dataset Iris;
- separação entre dados de treino e teste;
- treinamento de modelo com Scikit-Learn;
- avaliação de modelo;
- exportação do modelo treinado com `joblib`;
- criação de interface web com Streamlit;
- simulação de uma aplicação real de predição.

---

## 🧠 Contexto do problema

O dataset Iris é um conjunto de dados clássico de Machine Learning.

Ele possui informações sobre flores do gênero Iris e contém quatro características principais:

- comprimento da sépala;
- largura da sépala;
- comprimento da pétala;
- largura da pétala.

Com base nessas características, o modelo tenta prever a espécie da flor.

As espécies possíveis são:

- Iris setosa;
- Iris versicolor;
- Iris virginica.

---

## 🧩 Etapas do projeto

### 1. Treinamento do modelo no Jupyter Notebook

Na primeira etapa, será desenvolvido um notebook para estudar e treinar o modelo.

O notebook deverá conter:

- carregamento do dataset Iris;
- criação de um DataFrame para visualização dos dados;
- separação entre `X` e `y`;
- divisão dos dados em treino e teste;
- treinamento de um modelo de classificação;
- avaliação do desempenho do modelo;
- teste com novos valores;
- exportação do modelo treinado usando `joblib`.

Exemplo de fluxo:

```python
modelo = KNeighborsClassifier(n_neighbors=3)
modelo.fit(X_train, y_train)

joblib.dump(modelo, "modelo_iris.joblib")
```

---

### 2. Criação da aplicação com Streamlit

Na segunda etapa, será criada uma aplicação web simples com Streamlit.

A aplicação deverá conter:

- título do projeto;
- campos para o usuário informar as medidas da flor;
- botão para realizar a previsão;
- estrutura preparada para carregar o modelo treinado;
- exibição do resultado previsto.

Inicialmente, a aplicação pode apenas coletar os dados e simular o botão de previsão.

Depois, ela será integrada ao modelo exportado no notebook.

---

## 📁 Estrutura sugerida do projeto

```text
iris-ml-streamlit/
│
├── notebooks/
│   └── treinamento_modelo_iris.ipynb
│
├── models/
│   └── modelo_iris.joblib
│
├── app.py
│
├── requirements.txt
│
└── README.md
```

---

## ⚙️ Instalação

Crie um ambiente virtual:

```bash
python -m venv .venv
```

Ative o ambiente virtual:

### Windows

```bash
.venv\Scripts\activate
```

### Linux/macOS

```bash
source .venv/bin/activate
```

Instale as dependências:

```bash
pip install scikit-learn pandas matplotlib streamlit joblib
```

Ou, se estiver usando um arquivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

---

## 📦 Dependências principais

O projeto utiliza:

```text
scikit-learn
pandas
matplotlib
streamlit
joblib
```

---

## ▶️ Executando o notebook

A primeira etapa deve ser feita no Jupyter Notebook.

Execute:

```bash
jupyter notebook
```

Depois, abra o arquivo:

```text
notebooks/treinamento_modelo_iris.ipynb
```

Nesse notebook, o modelo será treinado, avaliado e exportado para a pasta `models/`.

---

## 🌐 Executando a aplicação Streamlit

Depois de criar o arquivo `app.py`, execute:

```bash
streamlit run app.py
```

A aplicação será aberta no navegador.

O usuário poderá inserir as características da flor Iris e clicar no botão para simular ou realizar a previsão da espécie.

---

## 🧪 Exemplo de entrada esperada

A aplicação deve receber quatro valores numéricos:

```text
Comprimento da sépala
Largura da sépala
Comprimento da pétala
Largura da pétala
```

Esses valores serão organizados em uma estrutura compatível com o modelo:

```python
entrada_modelo = [[
    sepal_length,
    sepal_width,
    petal_length,
    petal_width
]]
```

---

## 🤖 Integração futura com o modelo

Após o treinamento no notebook, o modelo poderá ser carregado na aplicação Streamlit:

```python
import joblib

modelo = joblib.load("models/modelo_iris.joblib")
predicao = modelo.predict(entrada_modelo)
```

O resultado numérico poderá ser convertido para o nome da espécie:

```python
nomes_especies = ["setosa", "versicolor", "virginica"]
especie = nomes_especies[predicao[0]]
```

---

## 🏭 Relação com uma aplicação real

Este projeto simula um fluxo real de desenvolvimento de Machine Learning:

```text
1. Coleta e análise dos dados
2. Treinamento do modelo
3. Avaliação do modelo
4. Exportação do modelo treinado
5. Criação de uma aplicação para o usuário final
6. Uso do modelo em uma interface interativa
```

Esse fluxo é comum em aplicações de Ciência de Dados, Inteligência Artificial e sistemas inteligentes.

---

## ✅ Resultado esperado

Ao final do projeto, o aluno deverá ser capaz de:

- compreender o fluxo básico de um projeto de Machine Learning;
- treinar um modelo simples com Scikit-Learn;
- exportar um modelo treinado;
- criar uma interface com Streamlit;
- preparar dados de entrada para um modelo;
- entender como uma aplicação real pode utilizar um modelo de Machine Learning.

---

## 🚀 Próximos passos

Possíveis melhorias futuras:

- mostrar a probabilidade de cada espécie;
- melhorar a visualização dos resultados;
- adicionar imagens das espécies;
- criar validações de entrada;
- publicar a aplicação online.
