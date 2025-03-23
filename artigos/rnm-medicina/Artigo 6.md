***
## A transfer learning-based multimodal neural network combining metadata and multiple medcal imagens for glaucoma type diagnosis

### 1. **Resumo do Artigo**  

**Objetivo:**  
Desenvolver uma rede neural multimodal (**GMNNnet**) para diagnóstico e classificação de subtipos de glaucoma, combinando metadados clínicos e múltiplas imagens médicas. O estudo também propõe o conjunto de dados **GM367**, o primeiro com cinco categorias de glaucoma e quatro modalidades de imagens.  

**Metodologia:**  
- **Dados:** Construção do GM367, contendo 367 pacientes com registros eletrônicos, imagens de OCT, fundo de olho, UBM e RNFL, além de cinco classes de glaucoma.  
- **Modelo:**  
  - **GMNNnet**: Arquitetura com três ramos:  
    1. **Ramificação 1**: Processamento de metadados (idade, pressão intraocular) via redes convolucionais e LSTM.  
    2. **Ramificação 2**: Segmentação de características oftalmológicas (vasos, CDR) com M-Unet.  
    3. **Ramificação 3**: Extração de padrões globais/locais de imagens usando ResFormer (combinação de ResNet e Transformer).  
  - **Transfer Learning**: Fine-tuning de modelos pré-treinados no ImageNet para adaptação a dados médicos.  
  - **Interpretabilidade**: Grad-CAM para destacar regiões relevantes nas imagens.  

**Resultados:**  
- **Acurácia**: **95,1%** (superando modelos como ResNet e U-Net).  
- **Sensibilidade (SEN)**: 93,2%; **Especificidade (SPE)**: 93,2%; **AUC**: 96,2%.  
- **Eficiência**: Tempo de inferência de **0,02 segundos por paciente**, viável para uso clínico.  

**Conclusões:**  
A GMNNnet demonstra superioridade na classificação de subtipos de glaucoma, integrando dados multimodais e transfer learning. O uso de Grad-CAM aumenta a transparência, facilitando a adoção clínica.  

***
### 2. **Metodologia Utilizada**  

- **Técnicas de Processamento de Dados:**  
  - **Pré-processamento de Imagens**: Recorte automático em torno do disco óptico, aumento de dados (rotações, flip).  
  - **Normalização**: Min-max para características numéricas e one-hot encoding para categóricas.  
  - **Balanceamento**: Expansão de classes minoritárias via aumento de dados.  

- **Arquitetura da Rede:**  
  - **M-Unet**: Variante da U-Net para segmentação de vasos retinianos e cálculo de CDR.  
  - **ResFormer**: Combinação de ResNet50 (ajustada com GroupNorm) e Transformer para capturar padrões em imagens de alta resolução.  
  - **Fusão Multimodal**: Combinação de saídas dos três ramos via CatBoost.  

- **Treinamento:**  
  - **Loss Function**: *Focal Loss* para lidar com desbalanceamento de classes.  
  - **Otimização**: Adam (*learning rate* = 0,0001) com validação cruzada de 5 folds.  

- **Ferramentas:**  
  - Frameworks: Keras e PyTorch.  
  - Hardware: NVIDIA Tesla A100.  

***
### 3. **Principais Contribuições**  

- **Dataset GM367**: Primeiro conjunto multimodal com **cinco classes de glaucoma** e quatro tipos de imagens (OCT, fundo de olho, UBM, RNFL), preenchendo lacunas de datasets públicos existentes.  
- **Arquitetura Multimodal**: Integração de metadados, segmentação baseada em conhecimento clínico (M-Unet) e processamento avançado de imagens (ResFormer).  
- **Transfer Learning Eficaz**: Redução de **72% no loss** comparado a treinamento do zero, viabilizando uso em pequenos datasets médicos.  
- **Interpretabilidade Clínica**: Grad-CAM com **Dice = 0,85** alinhado a regiões de interesse médico, aumentando confiança no modelo.  

***
### 4. **Limitações e Lacunas**  

- **Generalização Limitada**: Validação apenas no GM367; desempenho em populações diversas ou outros protocolos de imagem não foi testado.  
- **Dependência de Pré-processamento**: Recorte manual de regiões de interesse e tratamento de dados faltantes (**até 60% em variáveis como "fumante"**) podem comprometer a escalabilidade.  
- **Complexidade Temporal**: Dados longitudinais (ex.: evolução da pressão intraocular) não foram incorporados, limitando a previsão de progressão da doença.  
- **Interpretabilidade Parcial**: Embora Grad-CAM destaque regiões, a correlação com critérios clínicos específicos (ex.: padrões de campo visual) não foi explorada.  
- **Viés de Seleção**: Exclusão de pacientes com menos de duas visitas, potencialmente sub-representando casos iniciais.  