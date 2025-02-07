# Predição de Custos de Seguros de Saúde

## Descrição

Este projeto visa prever os custos de seguros de saúde utilizando algoritmos de machine learning. A ideia é explorar diferentes técnicas de aprendizado supervisionado em um problema real de regressão, aplicando práticas de ciência de dados e seleção de modelos para obter previsões precisas.

### Motivação

O projeto foi desenvolvido para aprofundar conhecimentos em:

- Análise exploratória de dados (EDA);
- Construção de pipelines de machine learning;
- Validação cruzada e seleção de modelos;
- Uso de visualizações para interpretação de resultados.

### Objetivos

- Comparar diferentes modelos de regressão e selecionar o melhor para prever os custos de seguros.
- Criar uma pipeline eficiente que automatize o processo de treinamento e previsão.

---

## Estrutura do Projeto

```plaintext
project/
├── data/
│   └── insurance.csv      # Conjunto de dados utilizado no projeto
├── models/
│   └── model.pkl          # Modelo treinado salvo para uso futuro
├── notebooks/
│   ├── insurance_tmp.ipynb # Versão inicial para testes rápidos
│   └── insurance.ipynb     # Notebook final com abordagem avançada
├── README.md                 # Documentação do projeto
└── requirements.txt          # Dependências do projeto
```

### Explicação dos Arquivos

- **data/insurance.csv**: Conjunto de dados utilizado, contendo informações sobre idade, sexo, IMC, filhos, região, se é fumante e o custo do seguro.
- **models/model.pkl**: Modelo final treinado e salvo para previsões futuras.
- **notebooks/insurance\_tmp.ipynb**: Versão inicial do notebook para testes e prototipação.
- **notebooks/insurance.ipynb**: Notebook completo com visualização de dados, treinamento e seleção do modelo.
- **requirements.txt**: Lista de dependências necessárias para reproduzir o projeto.

---

## Instalação

Para reproduzir o projeto localmente, siga os passos abaixo:

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/projeto-seguro.git
   cd projeto-seguro
   ```

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   source venv/bin/activate  # ou "venv\Scripts\activate" no Windows
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Execute os notebooks no Jupyter Notebook ou JupyterLab.

---

## Uso

### **Análise Completa**

Abra o arquivo `insurance.ipynb` para:

- Visualizar a análise exploratória de dados;
- Executar o treinamento e avaliação dos modelos;
- Verificar as métricas de desempenho e previsões.

### **Prototipação Rápida**

Utilize o arquivo `insurance_tmp.ipynb` para testes simples e rápidos com regressão linear.

### **Modelo Treinado**

O modelo treinado (Gradient Boosting Regressor) está salvo em `models/model.pkl` e pode ser carregado para previsões futuras:

```python
import pickle

with open('models/model.pkl', 'rb') as f:
    model = pickle.load(f)

# Prever custos de seguros
predictions = model.predict(novos_dados)
```

---

## Conjunto de Dados

### Descrição

O conjunto de dados utilizado é o [Insurance Dataset](https://github.com/stedy/Machine-Learning-with-R-datasets/blob/master/insurance.csv). Ele contém informações sobre:

- **age**: Idade do cliente.
- **sex**: Sexo do cliente (male/female).
- **bmi**: Índice de Massa Corporal.
- **children**: Número de filhos.
- **smoker**: Se o cliente é fumante (yes/no).
- **region**: Região de residência (northeast, northwest, southeast, southwest).
- **charges**: Custo do seguro (variável alvo).

---

## Detalhes Técnicos

### **1. Carregamento e Visualização de Dados**

- As bibliotecas `pandas` e `seaborn` são usadas para explorar o dataset.
- Gráficos como scatterplots e heatmaps ajudam a entender as relações entre variáveis.

### **2. Processamento de Dados**

- **Numéricas**: Imputadas com a média e normalizadas com `MinMaxScaler`.
- **Categóricas**: Tratadas com imputadores de frequência e codificadas com `OneHotEncoder`.

### **3. Modelagem**

- Modelos testados:
  - Regressão Linear
  - LassoCV
  - RidgeCV
  - Random Forest Regressor
  - Gradient Boosting Regressor
- Validação cruzada com `GridSearchCV` para otimização de hiperparâmetros.

### **4. Avaliação**

- Métricas utilizadas:
  - R²
  - MAE (Erro Absoluto Médio)
  - MAPE (Erro Absoluto Percentual Médio)
  - RMSE (Raiz do Erro Quadrático Médio)
- Visualizações de erros e previsões com `yellowbrick`.

---
