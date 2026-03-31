# Análise Preditiva de Potabilidade da Água: Uma Abordagem Data-Driven

Este projeto foi desenvolvido como parte da disciplina **SCC0275 – Introdução à Ciência de Dados** no Instituto de Ciências Matemáticas e de Computação (ICMC-USP). O objetivo principal é a criação de um modelo de Machine Learning capaz de classificar a potabilidade da água com base em parâmetros físico-químicos, priorizando a segurança sanitária.

## 🎯 Objetivo
Desenvolver um pipeline de classificação para prever se a água é potável (1) ou não potável (0). O projeto destaca-se pela aplicação de técnicas para lidar com classes desequilibradas e pelo ajuste fino de limiares de decisão para minimizar riscos à saúde pública.

## 🛠️ Tecnologias e Ferramentas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, NumPy, Scikit-learn, Imbalanced-learn (SMOTE), Matplotlib e Seaborn.
* **Ambiente:** Jupyter Notebook / Google Colab.

## 🚀 Pipeline do Projeto

### 1. Exploração de Dados (EDA)
Análise detalhada das 3.276 amostras para identificar correlações, distribuições e a presença de valores ausentes nos parâmetros como pH, Dureza, Sólidos, Cloramina, entre outros.

### 2. Pré-processamento e Engenharia de Dados
Para garantir a integridade dos resultados e evitar o **vazamento de dados (data leakage)**, seguiu-se um fluxo rigoroso:
* **Imputação:** Tratamento de valores nulos utilizando a média estatística.
* **Padronização:** Aplicação de `StandardScaler` para normalizar as escalas das variáveis.
* **Balanceamento (SMOTE):** O ajuste de classes foi realizado **estritamente após a divisão de treino e teste**, garantindo que o modelo fosse avaliado em dados reais e não sintéticos.
* **Redução de Dimensionalidade:** Exploração de PCA para análise de componentes.

### 3. Modelagem e Seleção
Foram testados e comparados oito algoritmos de classificação. Os que apresentaram maior robustez foram:
* **Random Forest** (Acurácia realista de ~69% e AUC ~0.70).
* **SVM (Support Vector Machine).**

### 4. O Diferencial: Threshold Tuning (Barreira Sanitária)
O ponto central deste trabalho foi a implementação do **Ajuste de Limiar**. Em contextos de saúde pública, o custo de um "Falso Negativo" (dizer que água contaminada é potável) é crítico. 
* O modelo foi ajustado para atuar como uma **barreira rigorosa**, atingindo um **Recall de 100% para a classe não potável**. 
* Embora isso aumente o rigor sobre a água potável, garante que nenhuma amostra contaminada seja classificada incorretamente como segura.

## 📈 Conclusões
O estudo demonstrou que a predição baseada em parâmetros físico-químicos é complexa devido à sobreposição das classes. Contudo, o projeto prova que a Ciência de Dados pode ser utilizada para criar camadas de segurança automatizadas que priorizam a vida humana acima da eficiência operacional.

---
**Autor:** Gabriel de Araujo Lima  
**Instituição:** ICMC - USP
