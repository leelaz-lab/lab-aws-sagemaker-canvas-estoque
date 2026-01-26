# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Projeto desenvolvido como requisito para conclusão do Bootcamp "Nexa - Machine Learning e GenAI na Prática". Utilizei um dataset de 1.000 registros com informações de preço, categoria e níveis de estoque para prever a demanda futura.

## 🛠️ Tecnologias
- Amazon SageMaker Canvas (AutoML)

- Dataset: 1.000 registros (Séries Temporais Multivariadas)


## 📈 Performance do Modelo (Versão 2)
Após iterações, o modelo final apresentou as seguintes métricas:

- MASE: 0.402 (Indica que o modelo é ~60% superior a uma previsão simples).

- MAPE: 0.647 (Redução significativa em relação à versão inicial).

- RMSE: 11.11 (Margem de erro absoluta em unidades). Ao concluir, envie a URL do seu repositório com a solução na plataforma da DIO.

<img width="1780" height="848" alt="Captura de tela 2026-01-23 170228" src="https://github.com/user-attachments/assets/1736fb0f-ff49-4918-a2ca-b7ce96ce6094" />

💡 Insights Extraídos
- Elasticidade-Preço: O preço foi identificado como um dos principais influenciadores na velocidade de escoamento do estoque.

- Agrupamento por Categoria: O modelo aprendeu padrões distintos para categorias de alta prioridade (Alimentos/Saúde) vs baixa prioridade.

## 🚀 Passo a Passo

### 1. Selecionar Dataset

-   Escolhido dataset com 1000 registros e campos ID_PRODUTO, DATA_EVENTO, QUANTIDADE_ESTOQUE.
-   Adicionado novos campos para análise conforme categoria e prioridade: CATEGORIA, PRIORIDADE e FORNECEDOR.
-   Dados adicionados com o seguinte padrão:

| ID_PRODUTO | CATEGORIA | PRIORIDADE | FORNECEDOR |
| ---------- | --------- | ---------- | ---------- |
| 1, 2 | Eletrônicos | Alta | Log Tech |
| 3, 4 | Eletrodomésticos | Média | Home Co |
| 5, 6 | Limpeza | Baixa | Clean S.A. |
| 7, 8 | Alimentos | Alta | Brasil Food |
| 9, 10 | Bebidas| Média | BevGroup |
| 11, 12 | Pets | Baixa | PetLove |
| 13, 14 | Saúde |Alta |FarmaLog |
| 15, 16 | Beleza | Média | GlowCorp |
| 17, 18 | Papelaria | Baixa | OfficeMax |
| 19, 20 | Ferramentas | Alta | IronWorks |
| 21, 22 | Jardim | Baixa | BioPlant |
| 23, 24 | Brinquedos | Média | KidsJoy |
| 25 | Esportes | Alta | SportLife |

### 2. Construir/Treinar

-   O dataset foi importado e o modelo foi criado a partir das seguintes configurações:
<img width="1190" height="822" alt="Captura de tela 2026-01-23 123810" src="https://github.com/user-attachments/assets/68149bbb-eef8-4ce0-80e5-b07b41e98706" />
<img width="817" height="565" alt="Captura de tela 2026-01-23 125622" src="https://github.com/user-attachments/assets/feb9e351-ae57-47ae-98ba-37f5c1fac2c3" />
<img width="701" height="485" alt="Captura de tela 2026-01-23 125630" src="https://github.com/user-attachments/assets/f3ab4d54-68a9-4909-b891-9f6984cbd66b" />
<img width="1732" height="822" alt="Captura de tela 2026-01-23 131310" src="https://github.com/user-attachments/assets/88f0f514-b097-47a2-b023-9d11f6de3d8b" />

-   ID_PRODUTO foi escolhido como campo chave.
-   CATEGORIAS
-   Inicie o treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

### 3. Analisar

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.
