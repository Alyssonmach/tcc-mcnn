***
## A Review on Explainability in Multimodal Deep Neural Nets"

### 1. **Resumo do Artigo**  

**Objetivo**: 
O artigo visa revisar a literatura sobre explicabilidade em redes neurais profundas multimodais, com foco em tarefas de visão e linguagem. Busca destacar a importância da transparência em modelos complexos, métodos de fusão de dados multimodais, técnicas de explicação e desafios emergentes.  

**Metodologia**:
Realizou-se uma revisão sistemática de trabalhos publicados, abordando:  
- Técnicas de fusão de dados (early, late, híbrida).  
- Métodos de explicação (atenção, contra-factuais, atribuição de características).  
- Aplicações em domínios críticos (saúde, veículos autônomos).  
- Avaliação de explicações e lacunas na área.  

**Resultados**:  
- Classificação de métodos de fusão e explicação em uma taxonomia clara.  
- Identificação de desafios como viés multimodal e falta de alinhamento entre explicações e percepção humana.  
- Destaque para a necessidade de métricas padronizadas para avaliação de explicações.  

**Conclusões**:  
- A explicabilidade é crucial para a aceitação social de sistemas de IA multimodal.  
- Abordagens como contra-factuais e gráficos de conhecimento são promissoras.  
- Futuras pesquisas devem focar em integração de conhecimento prévio, robustez a ataques adversariais e envolvimento humano no ciclo de avaliação.  

***
### 2. **Metodologia Utilizada**  

- **Técnicas de Fusão Multimodal**:  
  - **Early Fusion**: Combinação de dados brutos ou características iniciais.  
  - **Late Fusion**: Integração de decisões ou saídas de modelos unimodais.  
  - **Hybrid Fusion**: Fusão em camadas intermediárias de redes neurais.  
  - Métodos recentes: *Tensor Fusion Networks*, *Low-Rank Multimodal Fusion*.  

- **Métodos de Explicabilidade**:  
  - **Baseados em Atenção**: Grad-CAM, mecanismos de atenção em VQA (Visual Question Answering).  
  - **Contra-Factuais**: Geração de explicações contrastivas (ex: "por que X e não Y?").  
  - **Atribuição de Características**: SHAP, LIME, Integrated Gradients.  
  - **Abordagens Interativas**: Sistemas com feedback humano (ex: XAlgo).  

- **Ferramentas e Datasets**:  
  - **Datasets**: VQA-X (explicações para respostas), CUB (atributos visuais), VQA-CP (viés em VQA).  
  - **Modelos Pré-Treinados**: CLIP (OpenAI), DALL-E (geração de imagens a partir de texto).  

- **Abordagem de Revisão**:  
  - Análise qualitativa de mais de 200 referências.  
  - Organização em taxonomias (ex: métodos *intrínsecos* vs. *pós-hoc*).  

***
### 3. **Principais Contribuições**  

- **Sistematização do Conhecimento**:  
  - Revisão abrangente de técnicas de fusão e explicação, categorizando-as em taxonomias claras.  
  - Discussão de aplicações em domínios críticos (ex: diagnóstico médico, navegação autônoma).  

- **Inovações Conceituais**:  
  - Defesa da **multimodalidade nas explicações** (ex: justificativas textuais + mapas de atenção visual).  
  - Proposta de **avaliação baseada em causalidade** para explicar decisões.  

- **Direcionamentos Práticos**:  
  - Identificação de *benchmarks* emergentes (ex: VQA-X) e necessidade de datasets com anotações de explicações.  
  - Recomendações para mitigar viés multimodal (ex: regularização baseada em entropia funcional).  

***
### 4. **Limitações e Lacunas**  

- **Limitações do Artigo**:  
  - **Falta de Análise Quantitativa**: Não compara o desempenho de técnicas de explicação em métricas padronizadas.  
  - **Dependência de Datasets Específicos**: Muitos métodos são validados em datasets sintéticos (ex: CLEVR), limitando a generalização.  

- **Desafios na Área**:  
  - **Alinhamento Humano-Modelo**: Mapas de atenção não garantem fidelidade à percepção humana.  
  - **Avaliação Subjetiva**: Métricas como BLEU e METEOR não capturam completude ou causalidade nas explicações.  
  - **Robustez**: Explicações são vulneráveis a ataques adversariais (ex: perturbações em pixels ou texto).  

- **Lacunas de Pesquisa**:  
  - **Integração de Conhecimento Externo**: Poucos trabalhos incorporam *knowledge graphs* para melhorar interpretabilidade.  
  - **Explicações Dinâmicas**: Necessidade de sistemas adaptáveis a diferentes stakeholders (ex: médicos vs. pacientes).  