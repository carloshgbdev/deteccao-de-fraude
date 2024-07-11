
![](https://img.shields.io/github/languages/top/carloshgbdev/deteccao-de-fraude
) ![](https://img.shields.io/badge/Deep_Learning-blue
) ![](https://img.shields.io/badge/Fraud_Detection-orange
) ![](https://img.shields.io/badge/UFG-BIA-orange
)

# Credit Card Fraud Detection


### [Installation](#installation) | [Links](#links) | [Contribuitors](#contribution)

Repository for credit card fraud detection using Deep Learning. Final project for the Data Analytical Thinking course.

Below is AGEMC of this project, similar to  CRISP-DM.

### A - Ask a Question
 
Pergunta: Dado uma nova transação, ela é fraudulenta?

### G - Get the Data

Download do `CSV` fornecido pelo [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?resource=download).

### E - Explore data

Lemos o artigo do Medium que nos explicava o que cada representava.

Utilizamos clusters para auxiliar na identificação de outliers. Com os cluster, usamos as distancias dos pontos ao centroide do cluster, isso serve como uma feature a mais, na modelagem seguinte.

O algoritmo utilizado foi o K-Means com `k=5`, foi testado o DBSCAN, entretanto não aplicado por conta do seu tempo de processamento. Não utilizamos o SMOTE como no artigo.

### M - Modeling

Na modelagem, utilizamos AutoEncoders para detecção de outliers, pois a nossa abordagem é não supersionada, diferente do artigo.

#### Como um Autoencoder detecta outlier?

  Durante o treinamento da rede, a função de loss é o erro de representação da entrada com a saída. Esse é sempre minimizado quanto os dados são inliers, pois a rede aprende esse padrão. Quando um outlier entra na rede, o erro de representação se torna alto e visivel que aquela transação será fraudulenta

Além disso foi testado diferentes arquiteturas de AutoEncoder como VAE. Entretanto, uma arquitetura mais simples apresentou melhor resultado!

### C - Communicate

Para detecção de outliers criamos um modelo de aprendizado não supervisionado que não depende de labels para classificar os resultados em uma matrix de confusão

![imagem](/assets/images/output.png)

A nossa resolução é melhor pois não depende de uma transação fraudulente acontecer para treinar o modelo, o nosso consegue detectar o crime mesmo que seja uma nova forma de fraudular uma transação. 

Para uso comercial, o nosso modelo é mais adequado pois é mais robusto!

## Organization

### Installation

To install dependencies, run:

    git clone https://github.com/carloshgbdev/deteccao-de-fraude
    pip install -r requirements.txt

Use venv or locally

### venv:

A virtual environment where the packages are installed to facilitate running the code:

Change the Python interpreter to the "venv": Press "Ctrl + Shift + P" and click on "Select Python Interpreter."

Activate the virtual environment:

    Windows: .\venv\Scripts\activate
    Linux/Mac OS: source venv/bin/activate

If you encounter issues with "ipykernel," the environment is not within the correct kernel. To fix this, inside the notebook, click on the kernel shown in the top right corner, displaying the Python version, and choose the one that includes "venv_kernel" before the Python version. This will fully activate the environment.

When finished running the code, deactivate the virtual environment with deactivate.

After, download [dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?resource=download).

### Links

- [Original Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud?resource=download)
- [Medium Article](https://towardsdatascience.com/credit-card-fraud-detection-9bc8db79b956)

### Licence: MIT 2.0

### Contribution

<a href="https://github.com/carloshgbdev/deteccao-de-fraude/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=carloshgbdev/deteccao-de-fraude" />
</a>
Carlos Henrique | Pedro Saraiva | Guilherme Frazão | {} | {}
