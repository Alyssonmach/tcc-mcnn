***
## End-to-End Multimodal Emotion Recognition using Deep Neural Networks

### 1. **Resumo do Artigo**  

**Objetivo:**  
Desenvolver um sistema de reconhecimento de emoções multimodais (arousal e valência) de forma *end-to-end*, integrando dados auditivos (voz) e visuais (expressões faciais), sem depender de características manuais.  

**Metodologia:**  
- **Arquitetura Multimodal:**  
  - **Modo Auditivo:** CNN processa o sinal de voz bruto (6 segundos, 16 kHz) para extrair características espectrais.  
  - **Modo Visual:** ResNet-50 pré-treinada no ImageNet analisa rostos em vídeos (96x96 pixels).  
  - **Integração Temporal:** LSTMs (2 camadas, 256 células cada) modelam o contexto temporal das características extraídas.  
  - **Função de Perda:** Maximização do coeficiente de correlação de concordância (CCC) para alinhar predições com anotações.  
- **Treinamento:** Fine-tuning das redes unimodais (áudio e visual) e treinamento conjunto com otimizador Adam.  

**Resultados:**  
- **Unimodal:**  
  - **Áudio:** Melhor desempenho em *arousal* (CCC = 0.715 no teste).  
  - **Visual:** Melhor desempenho em *valência* (CCC = 0.620 no teste).  
- **Multimodal:** Superou modelos existentes em *valência* (CCC = 0.620), mas não em *arousal*.  
- **Interpretabilidade:** Células específicas nas LSTMs correlacionaram-se com características prosódicas (ex.: intensidade da voz).  

**Conclusões:**  
O sistema *end-to-end* mostrou-se eficaz, especialmente para *valência*, e demonstrou a viabilidade de aprender características diretamente de dados brutos. A integração multimodal trouxe ganhos, mas há espaço para melhorias em *arousal*.  

***
### 2. **Metodologia Utilizada**  

- **Extração de Características:**  
  - **Voz:** CNN com camadas convolucionais temporais (filtros de 5 ms e 500 ms) e *max-pooling*.  
  - **Visão:** ResNet-50 fine-tuned com dados faciais do RECOLA.  
- **Modelagem Temporal:**  
  - LSTMs para capturar dependências temporais em sequências de 150 subjanelas (40 ms cada).  
- **Função de Perda:**  
  - Minimização de \( \mathcal{L}_c = 1 - \rho_c \), onde \( \rho_c \) é o CCC, substituindo o erro quadrático médio (MSE).  
- **Pré-processamento:**  
  - **Voz:** Segmentação em janelas de 6s, normalização (média zero, variância unitária).  
  - **Visão:** Detecção e rastreamento facial com MDNet, aumento de dados (*random cropping*, ajuste de brilho/saturação).  
- **Pós-processamento:** Filtragem por mediana, ajuste de escala e deslocamento temporal nas predições.  

***
### 3. **Principais Contribuições**  

1. **Abordagem *End-to-End*:** Primeiro trabalho a integrar redes neurais profundas para processar voz e vídeo brutos em reconhecimento de emoções, eliminando a necessidade de características manuais.  
2. **Otimização por CCC:** Introdução do CCC como função de perda, alinhando o treinamento à métrica de avaliação e melhorando desempenho.  
3. **Análise de Interpretabilidade:** Identificação de neurônios em LSTMs correlacionados com atributos acústicos (ex.: frequência fundamental), validando hipóteses da literatura.  
4. **Desempenho Superior:** Superou métodos tradicionais e modelos do desafio AVEC 2016, especialmente em *valência*.  
5. **Integração Multimodal Eficiente:** Combinação de redes pré-treinadas (ResNet) e fine-tuning conjunto para aproveitar sinergias entre modalidades.  

***
### 4. **Limitações e Lacunas**  

1. **Dependência de Pré-treinamento:** A ResNet-50 foi inicializada com pesos do ImageNet, limitando generalização para domínios não relacionados.  
2. **Complexidade Computacional:** Treinamento de LSTMs com sequências longas (150 subjanelas) exigiu hardware avançado e ajustes para evitar instabilidade.  
3. **Dataset Restrito:** RECOLA contém apenas 46 participantes, majoritariamente franceses, limitando diversidade cultural e linguística.  
4. **Desempenho em *Arousal*:** A integração multimodal não superou métodos unimodais em *arousal*, sugerindo falhas na fusão de características.  
5. **Pós-processamento Empírico:** Etapas como filtragem e deslocamento temporal foram ajustadas manualmente, sem garantias de otimalidade.  