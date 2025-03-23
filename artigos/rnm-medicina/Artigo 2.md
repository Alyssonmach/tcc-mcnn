***

## Multimodal Medical Imagen Fusion based on Deep Learnin Neural Network for Clinical Treatment Analysis

### 1. **Resumo do Artigo**  

**Objetivo**: 
Propor uma técnica de fusão de imagens médicas multimodais utilizando redes neurais convolucionais (CNN) baseadas em aprendizado profundo, visando integrar informações complementares de imagens como Tomografia Computadorizada (CT), Ressonância Magnética (MRI) e Tomografia por Emissão de Pósitrons (PET) para aprimorar diagnósticos clínicos.  

**Metodologia**:  
- Utilização de uma **rede siamesa** para gerar um mapa de pesos que integra informações de atividade de pixels de múltiplas imagens.  
- Decomposição das imagens em **pirâmides Laplacianas** para análise multiescala.  
- Aplicação de uma estratégia de fusão adaptativa baseada em similaridade local.  
- Comparação com métodos tradicionais (DWT, DCT, CVT, PCNN) usando métricas como Gradiente Médio (AG), Desvio Padrão (SD), Q^{AB/F}, Informação Mútua (MI) e Tempo de Processamento (PT).  

**Resultados**:  
- O método proposto (baseado em CNN) obteve desempenho superior em **todas as métricas** (ex.: AG = 0.0844 vs. 0.0729 do PCNN no Dataset 1) e menor tempo de processamento (2.094s vs. 2.253s do PCNN).  
- As imagens fusionadas apresentaram maior nitidez, preservação de bordas e detalhes anatômicos/funcionais, conforme demonstrado visualmente e quantitativamente.  

**Conclusões**:  
- A abordagem de aprendizado profundo supera técnicas tradicionais em qualidade visual e métricas objetivas.  
- A fusão multiescala e o mapeamento direto via CNN são eficazes para integrar informações multimodais, tornando-se promissores para aplicações clínicas.  

---

### 2. **Metodologia Utilizada**  

**Técnicas e Modelos**:  
- **Rede Siamesa**: Duas redes CNN idênticas processam pares de imagens (ex.: CT e MRI), gerando um **mapa de pesos** que integra informações de atividade de pixels.  
- **Pirâmides Laplacianas**: Decomposição multiescala das imagens para alinhamento com a percepção visual humana.  
- **Fusão Adaptativa**: Combinação de coeficientes decomposição usando métricas de energia local e similaridade (limiar *t = 0.6*).  
- **Pré-processamento**: Normalização de imagens para 256×256 pixels e uso de *patches* de 16×16 para treinamento.  

**Ferramentas e Validação**:  
- **Implementação**: MATLAB R2015b com framework Caffe para treinamento da CNN.  
- **Dataset**: 9 conjuntos de imagens (CT, MRI, PET) do *Harvard Medical School* e *Radiopaedia.org*.  
- **Métricas de Avaliação**:  
  - **AG (Gradiente Médio)**: Medida de nitidez.  
  - **SD (Desvio Padrão)**: Indica contraste.  
  - **$Q^{AB/F}$**: Mede preservação de informações estruturais.  
  - **MI (Informação Mútua)**: Quantifica sobreposição de informações entre imagens.  
  - **PT (Tempo de Processamento)**: Eficiência computacional.  

---

### 3. **Principais Contribuições**  

- **Integração Direta via CNN**: Mapeamento automático de atividades de pixels, eliminando a necessidade de regras manuais para fusão.  
- **Fusão Multiescala**: Uso de pirâmides Laplacianas para preservar detalhes em diferentes níveis de resolução.  
- **Superação de Métodos Tradicionais**: Demonstração empírica de que CNNs superam DWT, DCT e outras técnicas em qualidade e velocidade.  
- **Aplicabilidade Clínica Potencial**: Fusão de imagens estruturais (CT/MRI) e funcionais (PET) para diagnósticos mais precisos.  

---

### 4. **Limitações e Lacunas**  

- **Dependência de Dados de Treino**: A eficácia da CNN requer grandes volumes de imagens médicas rotuladas, que podem ser escassos.  
- **Complexidade Computacional**: Apesar do tempo de processamento ser menor que métodos tradicionais, a infraestrutura necessária (ex.: GPUs) pode limitar aplicações em tempo real.  
- **Validação Clínica Limitada**: Não há testes em ambientes clínicos reais ou com médicos para validar utilidade prática.  
- **Generalização**: O método foi testado apenas em CT, MRI e PET; não está claro se funciona bem com outras modalidades (ex.: ultrassom).  
- **Falta de Explicabilidade**: Decisões da CNN são "caixa-preta", o que pode dificultar a aceitação por profissionais da saúde.  




