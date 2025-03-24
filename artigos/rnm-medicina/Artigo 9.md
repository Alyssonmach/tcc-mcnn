***
## Interpretability-Based Multimodal Convolutional Neural Networks for Skin Lesion Diagnosis

#### 1. **Resumo do Artigo** 

**Objetivo**: Desenvolver um modelo de rede neural convolucional multimodal (IM-CNN) para diagnóstico de lesões de pele, combinando imagens dermatoscópicas e metadados de pacientes. O objetivo é melhorar a precisão e a interpretabilidade do diagnóstico, facilitando a confiança de dermatologistas e a colaboração humano-máquina.  

**Metodologia**:  
- **Três ramos de processamento**:  
  1. **Metadados**: Idade, sexo e localização da lesão.  
  2. **Características baseadas em domínio**: Extração automática de padrões (ABCDPT) de imagens segmentadas (U-Net) e análise de textura (GLCM).  
  3. **Imagens de lesões**: Uso de EfficientNetB5 para extração de características globais.  
- **Fusão multimodal**: Combinação das saídas dos três ramos usando focal loss para dados desbalanceados.  
- **Interpretabilidade**: Grad-CAM para visualização de regiões de interesse em imagens e SHAP para análise de importância de metadados.  

**Resultados**:  
- O modelo IM-CNN superou modelos unimodais, com **melhoria média de 72% em sensibilidade** e **21% em AUC_SEN_80**.  
- **Acurácia de 95,1%** e **AUC de 97,8%** no conjunto HAM10000, superando redes como ResNet50 e DenseNet.  
- Visualizações explicativas destacaram características críticas (idade, cor, localização) para decisões clínicas.  

**Conclusões**:  
- A fusão multimodal e a interpretabilidade são essenciais para diagnósticos precisos e confiáveis.  
- O modelo abre caminho para aplicações clínicas práticas, reduzindo erros humanos e melhorando a eficiência diagnóstica.  

***
#### 2. **Metodologia Utilizada**  

- **Segmentação de lesões**: U-Net para isolamento de regiões de interesse.  
- **Extração de características**:  
  - **ABCDPT**: Asimetria, bordas irregulares, variação de cor, diâmetro, padrões e textura.  
  - **GLCM**: Análise de textura via matriz de coocorrência.  
- **Classificadores**:  
  - **CatBoost**: Para metadados.  
  - **EfficientNetB5**: Para processamento de imagens.  
- **Fusão**: Combinação ponderada com focal loss para lidar com desbalanceamento de classes.  
- **Interpretabilidade**:  
  - **Grad-CAM**: Identificação de regiões críticas em imagens.  
  - **SHAP**: Explicação da contribuição de metadados.  
- **Avaliação**: Métricas como AUC, sensibilidade, especificidade e AUC_SEN_80 (nova métrica proposta).  

**Ferramentas**: Keras, TensorFlow, conjunto de dados HAM10000 (10.015 imagens de 7 classes).  

***
#### 3. **Principais Contribuições**  

- **Modelo IM-CNN**: Primeira abordagem a integrar multimodalidade (imagens + metadados) e interpretabilidade em diagnóstico de lesões de pele.  
- **Métrica AUC_SEN_80**: Foco em alta sensibilidade (>80%), crítica para detecção precoce de melanoma.  
- **Visualizações explicativas**:  
  - Grad-CAM para destacar regiões suspeitas em imagens.  
  - SHAP para identificar metadados influentes (ex.: idade e cor).  
- **Superação de modelos existentes**: Desempenho superior a redes como ResNet e DenseNet, com **sensibilidade de 83,5%** para melanoma.  
- **Aplicabilidade clínica**: Facilita a aceitação por dermatologistas ao fornecer explicações transparentes.  

***
#### 4. **Limitações e Lacunas** 

- **Limitações**:  
  - **Dependência de segmentação precisa**: Erros na segmentação (U-Net) podem comprometer a extração de características.  
  - **Generalização**: Validação restrita ao HAM10000; necessidade de testes em dados heterogêneos (ex.: diferentes dispositivos de captura).  
  - **Complexidade computacional**: Treinamento requer hardware avançado (GPU NVIDIA RTX 2080 Ti), limitando acesso em ambientes com recursos escassos.  
- **Lacunas**:  
  - **Falta de dados textuais**: Metadados clínicos adicionais (ex.: histórico do paciente) não foram integrados.  
  - **Avaliação clínica real**: Não houve comparação direta com dermatologistas usando o modelo como ferramenta auxiliar.  
- **Desafios futuros**:  
  - Incorporação de mais modalidades (ex.: registros eletrônicos de saúde).  
  - Adaptação para diagnósticos em tempo real em dispositivos móveis.  
  - Melhoria da robustez a ruídos e variações em imagens não padronizadas.  