***

## Multimodal fusion with deep neural networks for leveraging CT imaging and electronic health record: a case‑study in pulmonary embolism detection

### 1. **Resumo do Artigo**  
***

**Objetivo**: 
Desenvolver modelos de fusão multimodal que integrem dados de imagens de Tomografia Computadorizada (CTPA) e prontuário eletrônico (EMR) para melhorar a detecção automatizada de Embolia Pulmonar (PE).  

**Metodologia**:  
- Coleta de 108.991 estudos de CTPA do Stanford University Medical Center (2000–2016).  
- Seleção de 2.500 estudos estratificados (positivos/negativos para PE) e revisão manual por radiologistas, resultando em 1.837 estudos válidos.  
- Treinamento de modelos unimodais (imagem: PENet, uma rede neural 3D; EMR: redes neurais *feed-forward* e ElasticNet) e 7 arquiteturas de fusão (fusão precoce, tardia e conjunta).  
- Avaliação com métricas como AUROC, sensibilidade, especificidade e valor preditivo positivo (PPV).  

**Resultados**:  
- O modelo de **fusão tardia "Late Elastic Average"** (média das probabilidades do PENet e ElasticNet) obteve o melhor desempenho: **AUROC de 0.947** (0.962 excluindo PE subsegmentares).  
- Superou modelos unimodais: AUROC de 0.833 (imagem) e 0.921 (EMR).  
- Sensibilidade de 97,2% com PPV de 86,2% ao ajustar o ponto de operação para priorizar detecção de casos críticos.  

**Conclusões**:  
- A integração de dados clínicos (EMR) e de imagem (CT) melhora significativamente a precisão diagnóstica de PE.  
- Modelos multimodais reduzem falsos negativos e são adequados para triagem clínica, acelerando o diagnóstico.  

***
### 2. **Metodologia Utilizada**  

**Técnicas e Modelos**:  
- **Imagem (CTPA)**:  
  - Rede neural 3D (PENet) pré-treinada em vídeos (Kinetics-600) e ajustada para PE.  
  - Pré-processamento: normalização de unidades Hounsfield, janelas deslizantes de 24 fatias.  
  - Função de perda focal para lidar com desbalanceamento de classes.  
- **EMR**:  
  - Redes neurais *feed-forward* e ElasticNet para dados estruturados (demográficos, medicamentos, exames laboratoriais, diagnósticos).  
  - Normalização e codificação *one-hot* para variáveis categóricas.  
- **Fusão Multimodal**:  
  - **Fusão Tardia**: Combinação de probabilidades de modelos unimodais (ex.: média ponderada).  
  - **Fusão Precoce**: Concatenção de características extraídas de imagem e EMR antes da classificação.  
  - **Fusão Conjunta**: Aprendizado simultâneo de representações de ambas as modalidades.  

**Ferramentas e Validação**:  
- Divisão dos dados em treino (1.454 estudos), validação (193) e teste (190), sem sobreposição de pacientes.  
- *Grid search* para otimização de hiperparâmetros (ativadores, camadas ocultas, *dropout*).  
- Métricas estatísticas: Intervalos de confiança (bootstrap) e teste de DeLong para comparação de AUROC.  

***

### 3. **Principais Contribuições**  

- **Integração Contextual**: Demonstração prática de que a fusão de dados clínicos e de imagem, semelhante à prática clínica humana, melhora a detecção de PE.  
- **Abordagem End-to-End**: Eliminação de pré-processamento complexo de imagens (ex.: segmentação de vasos), facilitando implementação clínica.  
- **Exploração de Estratégias de Fusão**: Comparação sistemática de 7 arquiteturas, identificando a fusão tardia como mais eficaz.  
- **Impacto Clínico Potencial**: Modelo com alta sensibilidade (97,2%) pode priorizar casos urgentes, reduzindo atrasos no diagnóstico.  

***

### 4. **Limitações e Lacunas**  

- **Generalização**: Dados de uma única instituição (Stanford), sem validação externa.  
- **Viés Retrospectivo**: Dados históricos podem não refletir cenários clínicos dinâmicos.  
- **Exclusão de PE Subsegmentares**: Apesar de clinicamente questionáveis, sua exclusão limita a avaliação em contextos onde são relevantes.  
- **Falsos Positivos**: Casos com comorbidades não foram tratados pelo modelo, podendo gerar alertas irrelevantes.  
- **Dependência de EMR Completo**: O modelo não foi testado em situações com dados clínicos incompletos.  
- **Falta de Interpretabilidade**: As decisões do modelo não são explicáveis, o que pode limitar a aceitação clínica.  