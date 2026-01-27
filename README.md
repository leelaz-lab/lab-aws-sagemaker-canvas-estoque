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

### Selecionar Dataset

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

### Construir/Treinar

-   O dataset foi importado e o modelo foi criado a partir das seguintes configurações:
<img width="1190" height="822" alt="Captura de tela 2026-01-23 123810" src="https://github.com/user-attachments/assets/68149bbb-eef8-4ce0-80e5-b07b41e98706" />
<img width="817" height="565" alt="Captura de tela 2026-01-23 125622" src="https://github.com/user-attachments/assets/feb9e351-ae57-47ae-98ba-37f5c1fac2c3" />
<img width="701" height="485" alt="Captura de tela 2026-01-23 125630" src="https://github.com/user-attachments/assets/f3ab4d54-68a9-4909-b891-9f6984cbd66b" />
<img width="1732" height="822" alt="Captura de tela 2026-01-23 131310" src="https://github.com/user-attachments/assets/88f0f514-b097-47a2-b023-9d11f6de3d8b" />

-   ID_PRODUTO foi escolhido como campo chave.
-   CATEGORIA foi selecionado como coluna de agrupamento de forma a prever a variação de estoque de acordo com a categoria do produto.
-   Escolhido o tempo de 14 dias para p Forecast Horizon por se aproximar de uma previsão mais próxima da realidade onde os reabastecimentos giram em torno de uma a duas semanas.
-   Treinamento realizado na versão Standard durando por volta de 2 horas.


### Prever

<img width="1771" height="586" alt="single_prediction_results" src="https://github.com/user-attachments/assets/431036a8-9ba6-498a-8019-69085381930b" />
