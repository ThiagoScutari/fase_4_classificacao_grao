#  Implementando algoritmos de Machine Learning com Scikit-learn

##  Grupo: 57

### 👨‍💻 Integrantes:

* Thiago Scutari - RM562831 | [thiago.scutari@outlook.com](mailto:thiago.scutari@outlook.com)
* Henrique Ribeiro Siqueira - RM565044 | [henrique.ribeiro1201@gmail.com](mailto:henrique.ribeiro1201@gmail.com)
* Mariana Cavalante Oliveira - RM561678 | [mari.kvalcant@gmail.com](mailto:mari.kvalcant@gmail.com)

### 👩‍🏫 Professores:

* Leonardo Ruiz Orabona
* Andre Godoi Chiovato

---

## 🎯 Objetivo

Desenvolver e comparar modelos de aprendizado de máquina com foco na **classificação de grãos de trigo** utilizando o conjunto de dados `seeds_dataset`. Aplicar a metodologia **CRISP-DM**, contemplando análise exploratória, pré-processamento, modelagem, avaliação de desempenho e interpretação de resultados.

---

## 💻 Descrição do que foi executado no código `Fase_4_classificacao_grao.ipynb`

1. **Importação e visualização inicial dos dados**: o conjunto de dados foi carregado, suas primeiras linhas exibidas, e os nomes das colunas atribuídos.
2. **Análise exploratória**:
   - Cálculo de estatísticas descritivas: média, mediana, desvio padrão;
   - Visualizações com histogramas e gráficos de dispersão para detectar padrões e relações entre atributos.
3. **Pré-processamento**:
   - Conversão de classes numéricas para nomes das variedades de trigo (Kama, Rosa, Canadian);
   - Divisão dos dados em treino e teste (70/30);
   - Aplicação de normalização com `StandardScaler`.
4. **Modelagem com diferentes algoritmos**:
   - Treinamento dos modelos: KNN, Random Forest e Regressão Logística;
   - Avaliação com métricas: acurácia, precisão, recall, F1-score e matriz de confusão.
5. **Otimização de hiperparâmetros** com GridSearchCV para os melhores modelos.
6. **Visualizações finais** dos desempenhos de cada modelo para análise comparativa.

---

## 📊 Insights Extraídos

- Os dados são bem distribuídos entre as classes, com características claramente diferenciáveis entre as variedades de trigo.
- A normalização contribuiu significativamente para a performance de algoritmos sensíveis à escala, como SVM e KNN.
- Os modelos **SVM e Random Forest** apresentaram os melhores resultados em termos de acurácia e F1-score.
- GridSearchCV ajudou a melhorar ainda mais o desempenho de alguns classificadores, ajustando hiperparâmetros como:

- param_knn = {  
     'knn__n_neighbors': [3, 5, 7, 9],  
     'knn__weights': ['uniform', 'distance'],  
     'knn__p': [1, 2]  # p=1: Manhattan, p=2: Euclidean  
}  
- param_logreg = {  
     'logreg__C': [0.01, 0.1, 1, 10],  
     'logreg__penalty': ['l2'],  
     'logreg__solver': ['lbfgs'],  
}  
- param_clf = {  
     'n_estimators': [50, 100, 200],  
     'max_depth': [None, 5, 10],  
     'min_samples_split': [2, 5],  
}  

---

## ✅ Conclusão

O projeto demonstrou a eficácia do uso de algoritmos de machine learning para classificação de grãos agrícolas, destacando a importância do pré-processamento adequado e da avaliação sistemática de diferentes modelos. A abordagem baseada na metodologia CRISP-DM garantiu uma estrutura robusta para análise de dados, promovendo decisões baseadas em evidências e garantindo reprodutibilidade.
A partir das análises conduzidas, foi percebido:

- Uma relação estreitamente proporcional entre Área e Perímetro do grão das variedades;
- Uma relação proporcional entre a Largura e o Comprimento do Núcleo, embora esta seja mais dispersa;
- A relação entre compacidade e comprimento do sulco não é tão proporcional. A compacidade é mais similar entre as variedades Kama e Rosa, enquanto a compacidade da variedade Canadian é normalmente menor, ainda apresentando alguns pontos similares com as outras variedades;
- Grãos da variedade Kama apresentam menores coeficientes de assimetria, enquanto Canadians apresentam maiores coeficientes de assimetria. Assim, o coeficiente de assimetria do grão não é proporcional a área do grão

