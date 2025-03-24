***
## On the early diagnosis of Alzheimers's Disease from multimodal signals: A survey

### 1. **Resumo do Artigo**  

**Objetivo**: 
Revisar sinais multimodais (fisiológicos, comportamentais, cognitivos e psicológicos) para o diagnóstico precoce do Alzheimer (DA), com foco em métodos automáticos, contínuos e não invasivos.  

**Metodologia**: 
Revisão sistemática de estudos publicados entre 2005–2016, utilizando bases como PubMed e Compendex. Foram analisados marcadores fisiológicos (MRI, EEG, PET) e comportamentais (ambientes *smart homes*, análise da fala) e sua precisão diagnóstica.  

**Resultados**:  
- MRI apresentou alta precisão (98,95%) na distinção entre DA e controles saudáveis.  
- EEG destacou-se na detecção de Comprometimento Cognitivo Leve (MCI) vs. controles (97,88%) e MCI vs. DA (94,05%).  
- Dados comportamentais (como padrões de sono e mobilidade em *smart homes*) mostraram correlação significativa com declínio cognitivo.  
**Conclusões**: Sistemas multimodais, combinando dados fisiológicos (MRI, EEG) e comportamentais, são essenciais para detectar alterações sutis e melhorar o diagnóstico precoce.  

***
### 2. **Metodologia Utilizada** 

**Técnicas e Ferramentas**:  
- **Processamento de Imagens Médicas**:  
  - Segmentação e registro de imagens (MRI, PET, SPECT).  
  - Análise volumétrica (ex.: atrofia do hipocampo).  
  - Uso de toolboxes como SPM (Statistical Parametric Mapping) e FreeSurfer.  
- **Aprendizado de Máquina**:  
  - Classificadores como SVM (*Support Vector Machines*) e redes neurais (ANNs).  
  - Redução de dimensionalidade (PCA, LDA).  
- **Análise de Sinais Fisiológicos**:  
  - EEG: parâmetros de complexidade (entropia, coerência espectral).  
  - Eye-tracking: latência e precisão de movimentos sacádicos.  

**Bases de Dados**:  
- ADNI (Alzheimer’s Disease Neuroimaging Initiative) para dados longitudinais de MRI e PET.  
- Conjuntos públicos como OASIS e ORCATECH para dados comportamentais.  

***
### 3. **Principais Contribuições**  

- **Síntese de Biomarcadores**: Identificou marcadores promissores, como atrofia do hipocampo (MRI), alterações na atividade elétrica cerebral (EEG) e padrões de movimento ocular.  
- **Integração Multimodal**: Defendeu a combinação de dados fisiológicos e comportamentais para aumentar a sensibilidade diagnóstica.  
- **Ferramentas Práticas**: Listou bancos de dados públicos (ADNI) e toolboxes (SPM, DPABI) para facilitar pesquisas futuras.  
- **Discussão de Desafios**: Abordou questões como "ruído de rótulo" em dados clínicos e a necessidade de padronização em estudos multi-sítio.  

***
### 4. **Limitações e Lacunas** 

**Limitações**:  
- **Variabilidade Metodológica**: Diferenças nos protocolos de aquisição de imagens (ex.: ressonâncias magnéticas de diferentes fabricantes) dificultam comparações.  
- **Foco em Estudos Transversais**: Poucos estudos longitudinais analisam a progressão temporal da doença.  
- **Sensibilidade em Estágios Iniciais**: Métodos como MRI têm limitações na detecção de alterações no estágio pré-clínico.  

**Lacunas**:  
- **Integração de Dados Temporais**: Falta de modelos que analisem a evolução de sintomas ao longo do tempo.  
- **Validação Clínica**: A maioria dos estudos é baseada em laboratório; há necessidade de testes em ambientes reais.  
- **Acesso a Dados Comportamentais**: Poucos conjuntos de dados públicos incluem informações comportamentais contínuas.  