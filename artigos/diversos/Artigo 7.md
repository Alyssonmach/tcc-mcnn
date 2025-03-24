***
## What Clinicians Want: Contextualizing Explainable Machine Learning for Clinical End Use

### 1. **Resumo do Artigo**  

**Objetivo**:  
O estudo visa identificar as necessidades de médicos em relação à explicabilidade de modelos de *machine learning* (ML) em ambientes clínicos, com foco em aumentar a confiança e a adoção sustentada dessas ferramentas. O objetivo é mapear quais tipos de explicações são mais relevantes para profissionais de saúde em contextos de alta pressão, como UTI e Emergência.  

**Metodologia**:  
- **Entrevistas qualitativas** com 10 médicos (6 da UTI e 4 da Emergência), incluindo profissionais seniores e juniores.  
- **Cenários hipotéticos** de uso de ML em situações críticas (ex.: previsão de parada cardíaca na UTI e triagem de pacientes na Emergência).  
- Análise das respostas para categorizar classes de explicações e propor métricas de avaliação.  

**Resultados**:  
- **Classes de explicações prioritárias**: Importância de características (*feature importance*), incerteza do modelo, explicações temporais e design transparente.  
- **Métricas de avaliação**: Representação adequada ao domínio, ação clínica potencial e consistência das explicações.  
- **Insights-chave**: Médicos valorizam explicações que justifiquem decisões clínicas, reduzam sobrecarga cognitiva e permitam validação com conhecimento prévio.  

**Conclusões**:  
A explicabilidade em ML clínico deve ser contextualizada, focando em representações claras e acionáveis. A confiança dos médicos depende da capacidade do modelo de alinhar-se com práticas baseadas em evidências e oferecer transparência sobre suas limitações.  

***
### 2. **Metodologia Utilizada**  

- **Entrevistas qualitativas**:  
  - Realizadas com médicos de UTI e Emergência, utilizando um guia semiestruturado.  
  - Cenários hipotéticos simulando o uso de ML em situações reais (ex.: alertas de parada cardíaca).  
  - Análise temática para identificar padrões nas respostas.  

- **Técnicas de Explicabilidade Analisadas**:  
  - **Importância de características**: Métodos como LIME (*Local Interpretable Model-agnostic Explanations*) e SHAP (*Shapley Values*).  
  - **Incerteza**: Calibração de modelos e métodos Bayesianos para quantificar confiança nas previsões.  
  - **Explicações temporais**: Modelos baseados em atenção (*attention mechanisms*) para trajetórias de pacientes.  

- **Ferramentas de Avaliação**:  
  - Métricas propostas: *Domain Appropriate Representation*, *Potential Actionability* e *Consistency*.  

***
### 3. **Principais Contribuições**  

- **Identificação de Necessidades Clínicas**:  
  - Médicos priorizam explicações que justifiquem decisões, como listas de fatores influentes (*feature importance*) e níveis de confiança do modelo.  
  - Ação clínica imediata é essencial: explicações devem ser concisas e integrar-se ao fluxo de trabalho existente.  

- **Proposta de Classes de Explicações**:  
  - Destaque para **incerteza** (calibração de modelos) e **transparência** (modelos como árvores de decisão).  
  - Crítica a métodos baseados em instâncias similares (*instance-based explanations*), considerados pouco úteis em contextos urgentes.  

- **Métricas para Avaliação**:  
  - Introdução de critérios como **consistência** (explicações estáveis frente a variações) e **representação contextualizada** (evitar redundâncias).  

- **Direcionamento para Pesquisa**:  
  - Chamada para desenvolvimento de técnicas que equilibrem desempenho e explicabilidade, especialmente em dados temporais (ex.: séries temporais de sinais vitais).  

***
### 4. **Limitações e Lacunas**  

- **Amostra Limitada**:  
  - Estudo restrito a 10 médicos de duas especialidades, sem representação de outras áreas (ex.: ambulatório ou psiquiatria).  
  - Viés de seleção: participantes já tinham familiaridade com ML, o que pode não refletir a realidade de todos os profissionais.  

- **Aplicabilidade Prática**:  
  - Métricas propostas (ex.: *consistency*) carecem de validação empírica em ambientes reais.  
  - Não aborda desafios de implementação, como integração a sistemas de prontuários eletrônicos (EHR).  

- **Técnicas Não Exploradas**:  
  - Ausência de discussão sobre modelos de aprendizado por reforço ou métodos explicativos para dados multimodais (ex.: imagens e textos).  

- **Questões Éticas e Regulatórias**:  
  - Lacuna na discussão sobre responsabilidade legal em caso de erros do modelo ou viés em explicações.  

- **Generalização**:  
  - Necessidade de estudos em outras instituições e países para validar as descobertas.  