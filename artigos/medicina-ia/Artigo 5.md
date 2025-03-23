***
### 1. **Resumo do Artigo**  

**Objetivo**: 
Revisar as aplicações de *deep learning* em diagnósticos médicos, abordando três questões principais:  
- A diversidade de aplicações na área médica.  
- A possibilidade de substituição de médicos por sistemas de *deep learning*.  
- O futuro dessa tecnologia (permanência ou obsolescência).  

**Metodologia**: 
Revisão sistemática seguindo o protocolo PRISMA, com análise de mais de 300 artigos (46 selecionados após triagem). Fontes incluíram periódicos como *IEEE Transactions Medical Imaging* e *Nature*.  

**Resultados Principais**:  
- **CNNs (Redes Neurais Convolucionais)** são o método mais utilizado (32 dos 46 artigos), principalmente em imagens médicas (MRI, CT, mamografia).  
- Aplicações dominantes: segmentação (14 artigos), classificação (8), detecção (8) e diagnóstico (6).  
- *Deep learning* demonstrou alta precisão em tarefas como detecção de câncer (até 99% de acurácia) e segmentação de estruturas anatômicas.  

**Conclusões**:  
- A tecnologia é promissora e diversificada, mas ainda não substitui médicos, atuando como suporte.  
- Tendência de expansão contínua, com potencial para melhorar eficiência e reduzir diagnósticos tardios.  

***
### 2. **Metodologia Utilizada**  

- **Revisão Sistemática**: Seguiu o protocolo PRISMA para seleção e análise de artigos (identificação, triagem, elegibilidade, inclusão).  
- **Fontes de Dados**: Artigos de periódicos renomados (ex.: *Briefings in Bioinformatics*, *Medical Image Analysis*), publicados entre 2014–2018.  
- **Critérios de Busca**: Palavras-chave como "*deep learning and medical diagnosis*", "*deep learning CT*", e termos relacionados a segmentação e classificação.  
- **Modelos e Técnicas**:  
  - **Modelos**: CNNs (mais frequente), U-Net, DBN (Deep Belief Networks), SDAE (Stacked Denoising Autoencoders).  
  - **Tarefas**: Segmentação (ex.: tumores cerebrais), classificação (ex.: câncer de mama), detecção (ex.: nódulos pulmonares).  
- **Análise Qualitativa**: Foco em aplicações, fontes de dados e resultados, sem meta-análise quantitativa.  

***
### 3. **Principais Contribuições**  

- **Síntese de Evidências**: Compilação de 46 estudos em uma revisão acessível, destacando tendências (ex.: predominância de CNNs e imagens de MRI/CT).  
- **Tabelas Estruturantes**:  
  - Tabela 2: Resume métodos, fontes de dados e aplicações por estudo.  
  - Tabela 3: Síntese estatística por tipo de método, fonte de dados e aplicação.  
- **Discussão Prática**: Respostas às questões-chave:  
  - Diversidade de aplicações confirmada (ex.: oncologia, neurologia, oftalmologia).  
  - Papel complementar ao trabalho médico, não substitutivo.  
  - Futuro promissor, com expansão para outras áreas da saúde.  
- **Referência para Não Especialistas**: Linguagem simplificada, útil para pesquisadores de outras áreas.  

***
### 4. **Limitações e Lacunas** 

- **Viés de Seleção**: Foco em artigos recentes (2015–2018) e com termos como "*deep learning*" no título, possivelmente negligenciando estudos mais antigos ou com abordagens híbridas.  
- **Falta de Análise Quantitativa**: Não há comparação estatística entre métodos (ex.: acurácia média entre CNNs e outras redes).  
- **Aplicações Restritas**: Concentração em câncer (devido à abundância de estudos) e imagens médicas, com pouca ênfase em dados não estruturados (ex.: prontuários eletrônicos).  
- **Desafios Não Explorados**:  
  - Necessidade de grandes conjuntos de dados anotados.  
  - Questões éticas (ex.: responsabilidade em diagnósticos automatizados).  
  - Viabilidade clínica (ex.: integração com sistemas hospitalares).  
- **Futuro**: Sugere-se revisões periódicas para acompanhar avanços e explorar áreas emergentes (ex.: *transfer learning*, explicaibilidade de modelos).  