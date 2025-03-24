***
## Unbox the black-box for the medical explainable AI via multi-modal and multi-centre data fusion: A mini-review, two showcases and beyond

### 1. **Resumo do Artigo**  

**Objetivo**: 
O artigo visa discutir a importância da Inteligência Artificial Explicável (XAI) em aplicações médicas, destacando a necessidade de transparência em modelos de IA para aumentar a confiança clínica. Foca em métodos que integram fusão de dados multimodais (imagens de diferentes modalidades) e multicêntricos (dados de múltiplos hospitais), além de propor soluções para desafios como generalização e interpretabilidade.  

**Metodologia**:  
- Realiza uma revisão crítica de técnicas de XAI aplicadas à saúde.  
- Apresenta dois estudos de caso:  
  - **Classificação de COVID-19 em tomografias (CT)**: Combina aprendizado fracamente supervisionado com módulos explicáveis (EDM, SIM, NCM) para lidar com dados multicêntricos e anotações em nível de paciente.  
  - **Segmentação de ventrículos cerebrais em hidrocefalia**: Utiliza redes U-Net modificadas com treinamento multimodal (CT e MRI) para lidar com variações na espessura de cortes.  

**Resultados**:  
- No estudo de COVID-19, o modelo proposto superou métodos existentes em AUC (95,53% em nível de paciente) e especificidade (87,25%).  
- Na segmentação, alcançou Dice scores de 0,9099 (MRI) e 0,8954 (CT), superando U-Net e U-Net++.  
- Visualizações como mapas de ativação (CAM) e explicações locais (LIME/SHAP) validaram a interpretabilidade.  

**Conclusões**: 
A XAI é crucial para aplicações médicas, especialmente em modelos complexos como redes neurais profundas. A fusão de dados multicêntricos e a integração de explicações intuitivas podem facilitar a adoção clínica de IA, mas requerem mais avanços em usabilidade e abstração semântica.  
***
### 2. **Metodologia Utilizada**  

- **Revisão Sistemática**: Classificou métodos de XAI em cinco categorias: redução de dimensionalidade, importância de features, mecanismos de atenção, destilação de conhecimento e modelos substitutos (surrogates).  
- **Estudos de Caso**:  
  - **Classificação de COVID-19**:  
    - **EDM (Explainable Diagnosis Module)**: Substituiu camadas totalmente conectadas por convoluções 1x1 para gerar mapas de ativação em tempo real.  
    - **SIM (Slice Integration Module)**: Modelagem baseada em *Multiple Instance Learning* (MIL) para agregar informações de cortes de CT em nível de paciente.  
    - **NCM (Noisy Correction Module)**: Correção de ruído em anotações usando distribuições de probabilidade.  
  - **Segmentação de Hidrocefalia**:  
    - U-Net com *encoder* ResNet-50 pré-treinado e *decoder* com convolução subpixel.  
    - Treinamento multimodal para alinhar distribuições de cortes finos e grossos.  
    - Explicações via análise de espaço latente (PCA) e correlação com métricas de desempenho.  
- **Ferramentas**: Grad-CAM, LIME, SHAP e T-SNE para visualizações explicativas.  

***
### 3. **Principais Contribuições**

- **Revisão Estruturada de XAI na Saúde**: Organizou métodos emergentes (atenção, surrogates) e aplicações clínicas, destacando lacunas como a necessidade de explicações em alto nível.  
- **Soluções Práticas para Desafios Clínicos**:  
  - Abordagem para dados multicêntricos com anotações fracas (COVID-19).  
  - Modelo de segmentação "agnóstico à espessura de cortes", reduzindo dependência de anotações detalhadas.  
- **Validação em Cenários Reais**: Demonstrou eficácia quantitativa e qualitativa em dois contextos clínicos distintos, reforçando a viabilidade de XAI.  
- **Discussão sobre Fusão de Dados**: Ressaltou a importância de integrar dados multimodais (imagens, EHRs) para melhorar robustez e generalização.  

***
### 4. **Limitações e Lacunas** 

- **Explicações Técnicas vs. Clínicas**: Métodos como LIME e SHAP geram explicações baseadas em *features* de baixo nível (pixels), sem vinculação a conceitos clínicos (ex.: regiões anatômicas).  
- **Dependência de Dados Anotados**: O estudo de COVID-19 requer anotações em nível de paciente, que podem ser inconsistentes entre centros.  
- **Viés em Dados Multicêntricos**: Não há discussão profunda sobre como mitigar viés inerente a protocolos de aquisição variados.  
- **Validação Limitada**: Os estudos de caso usaram dados retrospectivos; faltam testes prospectivos em ambientes clínicos reais.  
- **Complexidade Computacional**: Modelos como ResNet-50 e U-Net modificada demandam hardware especializado, limitando acessibilidade.  
- **Meta-Explicações**: Falta de métodos para agregar explicações locais em insights clínicos abstratos (ex.: correlação com sintomas).  
