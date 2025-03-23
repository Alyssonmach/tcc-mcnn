***
## Causability ans explainability of artificial intelligence in medicine 

### 1. **Resumo do Artigo**

**Objetivo**: 
Discutir a importância da explicabilidade e da **causabilidade** (medida da qualidade das explicações para humanos) em sistemas de IA aplicados à medicina. O artigo busca diferenciar esses conceitos, destacar desafios em modelos de IA "caixa-preta" e propor diretrizes para integrar explicações compreensíveis em decisões clínicas.  

**Metodologia**:  
- Revisão teórica de técnicas de IA explicável (XAI), incluindo métodos **pós-hoc** (ex.: LIME, BETA) e **ante-hoc** (ex.: modelos lineares, árvores de decisão).  
- Análise crítica da tensão entre precisão e transparência em modelos como redes neurais profundas (DNNs).  
- Estudo de caso em histopatologia, comparando explicações humanas (posthoc e antehoc) com métodos de interpretação de IA. 

**Resultados**:  
- Definição de **causabilidade** como uma métrica para avaliar a eficácia, eficiência e satisfação das explicações fornecidas por sistemas de IA para profissionais médicos.  
- Demonstração da complexidade das explicações humanas em histopatologia, destacando a necessidade de modelos que integrem conhecimento causal.  
- Discussão sobre a importância de **modelos causais estruturais** (Pearl, 2009) para avançar em direção a sistemas de IA confiáveis.  

**Conclusões**: 
A IA na medicina requer não apenas modelos precisos, mas explicações que permitam **entendimento causal** e **confiança**. A causabilidade deve ser desenvolvida como um campo científico, com métricas para avaliar explicações e interfaces que conectem modelos de IA a contextos clínicos.  

***
### 2. **Metodologia Utilizada**  

- **Abordagens de IA Explicável (XAI)**:  
  - **Pós-hoc**: Técnicas que explicam decisões após a modelagem (ex.: LIME, BETA, análise de gradientes).  
  - **Ante-hoc**: Modelos intrinsecamente interpretáveis (ex.: regressão linear, árvores de decisão, GAMs).  
- **Redes Neurais Profundas (DNNs)**: Discussão sobre métodos de interpretação como **ativação maximizada**, **atribuição de incerteza** (epistêmica e aleatória) e **modelos generativos** (GANs, autoencoders).  
- **Modelos Causais**: Referência à teoria de Pearl (2009) sobre causalidade estrutural e sua aplicação em medicina.  
- **Estudo de Caso em Histopatologia**:  
  - Explicações humanas **posthoc** (descrição detalhada de características histológicas) e **antehoc** (processo hierárquico de diagnóstico).  
  - Comparação com métodos de interpretação de DNNs, como visualização de atributos e protótipos.  

***
### 3. **Principais Contribuições**  

- **Introdução do conceito de "causabilidade"**: Propõe uma métrica para avaliar a qualidade das explicações em IA, análoga à "usabilidade" em interação humano-computador.  
- **Crítica à dicotomia precisão vs. explicabilidade**: Destaca que modelos de alta precisão (ex.: DNNs) são menos transparentes, enquanto modelos interpretáveis (ex.: árvores) podem ser menos precisos.  
- **Estudo de caso prático**: Demonstra a complexidade das explicações em histopatologia, reforçando a necessidade de sistemas que alinhem explicações de IA com modelos mentais humanos.  
- **Defesa de modelos causais**: Argumenta que a IA médica deve avançar além de correlações estatísticas para incorporar raciocínio causal, permitindo intervenções e contra-factuais.  
- **Chamado para padrões de avaliação**: Sugere a criação de métricas para medir eficácia, eficiência e satisfação nas explicações (inspirado em padrões de usabilidade).  

***
### 4. **Limitações e Lacunas**  

- **Abordagem teórica**: O artigo prioriza definições conceituais, com exemplos práticos limitados a estudos de caso específicos (ex.: histopatologia).  
- **Validação empírica insuficiente**: A causabilidade é proposta como conceito, mas sem métricas validadas ou estudos comparativos em larga escala.  
- **Desafios técnicos**:  
  - Dificuldade em integrar modelos causais complexos (ex.: estruturas de Pearl) a sistemas de IA baseados em dados.  
  - Escalabilidade de métodos explicáveis em grandes conjuntos de dados médicos heterogêneos.  
- **Questões não resolvidas**:  
  - Como garantir que explicações de IA sejam adaptadas a diferentes níveis de expertise médica (ex.: residentes vs. especialistas).  
  - Viés em modelos generativos (ex.: GANs) e impacto em explicações.  
  - Privacidade e ética no uso de dados sensíveis para treinar modelos explicáveis.  
- **Aplicação clínica**: A implementação de sistemas de IA explicáveis em ambientes reais ainda é incipiente, com barreiras culturais e operacionais. 