***

## A Review on Multimodal Medical Image Fusion: Compendious Analysis of Medical Modalities, Multimodal Databases, Fusion Techniques and Quality Metrics

#### 1. **Resumo do Artigo** 

**Objetivo**: 
O artigo visa fornecer uma revisão abrangente sobre fusão de imagens médicas multimodais (MMIF), abordando desde modalidades de imagem, bancos de dados públicos, técnicas de fusão até métricas de avaliação de qualidade. Seu objetivo é servir como guia para profissionais da saúde e pesquisadores, auxiliando na seleção de métodos e recursos para diagnósticos mais precisos.  

**Metodologia**:  
- **Classificação de modalidades**: Categorização baseada em radiação, luz visível, microscopia e multimodalidade.  
- **Análise de bancos de dados**: Comparação de cinco bancos públicos (OASIS, TCIA, BrainWeb Atlas, ADNI, MIDAS) em termos de modalidades, órgãos-alvo e formatos.  
- **Técnicas de fusão**: Divisão em seis categorias: fusão em frequência, espacial, em nível de decisão, deep learning, híbrida e representação esparsa.  
- **Métricas de qualidade**: Avaliação quantitativa (MI, SSIM, RMSE) e qualitativa (análise visual).  

**Resultados**:  
- Técnicas baseadas em **deep learning** e **híbridas** mostraram melhor desempenho quantitativo.  
- O banco de dados **AANLIB (Harvard)** foi o mais utilizado, principalmente para imagens cerebrais.  
- Fusão de modalidades como MRI/CT e PET/MRI permite combinar informações anatômicas e funcionais, melhorando diagnósticos de doenças como Alzheimer e tumores.  

**Conclusões**:  
- A fusão multimodal é essencial para diagnósticos precisos, mas enfrenta desafios como registro inadequado e artefatos.  
- Futuras pesquisas devem focar em técnicas de deep learning, métricas sem referência e expansão de bancos de dados para outros órgãos além do cérebro.  

***
#### 2. **Metodologia Utilizada**  

- **Classificação de técnicas**:  
  - **Domínio espacial**: PCA, IHS, Brovey.  
  - **Domínio de frequência**: Transformadas (Wavelet, Contourlet, Shearlet).  
  - **Deep learning**: Redes neurais convolucionais (CNN), modelos baseados em sparse representation.  
  - **Híbridas**: Combinação de técnicas (ex: NSCT + PCNN).  
- **Ferramentas**: MATLAB, Python, bancos de dados públicos (OASIS, ADNI).  
- **Avaliação**:  
  - **Qualitativa**: Comparação visual de resultados de fusão.  
  - **Quantitativa**: Métricas como MI (Mutual Information), SSIM (Structural Similarity), SD (Standard Deviation).  

***
#### 3. **Principais Contribuições**  

- **Taxonomia detalhada**: Classificação inédita de modalidades de imagem por espectro eletromagnético, invasividade e fonte de energia.  
- **Banco de dados comparativos**: Análise estatística de uso de bancos públicos ao longo de cinco anos, destacando lacunas (ex.: falta de dados para olhos e laringe).  
- **Revisão de técnicas**: Síntese de 60+ trabalhos, com tabelas comparativas de vantagens/desvantagens (ex.: deep learning requer grandes datasets, técnicas espaciais são rápidas mas sofrem distorção espectral).  
- **Aplicações clínicas**: Resumo de técnicas usadas em doenças específicas (ex.: Alzheimer, neurocisticercose).  
- **Métricas de qualidade**: Compilação de 12 métricas (MI, SSIM, QXY/F) com fórmulas e descrições.  

***
#### 4. **Limitações e Lacunas**  

- **Limitações**:  
  - **Viés em bancos de dados**: Foco excessivo em imagens cerebrais (ex.: 80% dos estudos usaram AANLIB).  
  - **Falta de padronização**: Métricas de qualidade variam entre estudos, dificultando comparações diretas.  
  - **Deep learning**: Dependência de hardware avançado e datasets grandes, limitando aplicação em cenários com dados escassos.  
- **Lacunas**:  
  - **Órgãos negligenciados**: Poucos dados disponíveis para fusão de imagens de olhos, laringe e coração.  
  - **Falta de ground truth**: Dificuldade em validar resultados sem imagens de referência ideais.  
  - **Técnicas emergentes**: Necessidade de explorar fusão 3D e métodos adaptativos para redução de ruído.  
- **Desafios futuros**:  
  - Desenvolvimento de métricas sem referência robustas.  
  - Integração de pré-processamento (ex.: segmentação de regiões de interesse) antes da fusão.  