***
## Explain Images with Multimodal Recurrent Neural Networks

### 1. **Resumo do Artigo**  

**Objetivo**: 
Desenvolver um modelo de Rede Neural Recorrente Multimodal (m-RNN) para gerar descrições textuais de imagens e realizar tarefas de recuperação (imagem↔texto). O estudo visa superar as limitações de métodos baseados em recuperação, que não conseguem descrever combinações inéditas de objetos e cenas em novas imagens.  

**Metodologia**:  
- **Arquitetura**: Combina uma RNN para modelagem de linguagem (com camadas de *embedding* e recorrentes) com uma CNN para extração de características visuais (AlexNet).  
- **Treinamento**: Utiliza função de custo baseada em *perplexidade* para maximizar a probabilidade de gerar sentenças dadas as imagens, com retropropagação através do tempo (BPTT).  
- **Aplicações**: Geração de sentenças, recuperação de imagens por texto e vice-versa.  

**Resultados**:  
- **Geração de Texto**: Superou métodos anteriores em *perplexidade* (6.92 vs. 21.8 no IAPR TC-12) e BLEU (B-1: 0.395 vs. 0.373).  
- **Recuperação**: Alcançou R@1 de 20.9% (imagem→texto) e 13.2% (texto→imagem) no IAPR TC-12, superando métodos como *DeViSE* e *DeepFE*.  
- **Datasets**: Validado em IAPR TC-12, Flickr8K e Flickr30K, com desempenho consistente.  

**Conclusões**: 
O modelo m-RNN é eficaz para gerar descrições contextualizadas e recuperar informações multimodais. Sua arquitetura permite integração com recursos visuais mais complexos (ex: detecção de objetos), sugerindo potencial para melhorias futuras.  

***
### 2. **Metodologia Utilizada**  

- **Modelo m-RNN**:  
  - **Sub-rede de Linguagem**: Duas camadas de *embedding* (128 dimensões) + camada recorrente (ReLU, 256 dimensões).  
  - **Sub-rede Visual**: CNN pré-treinada (AlexNet) para extrair características da sétima camada (*decaf features*).  
  - **Camada Multimodal**: Combina características de texto e imagem (512 dimensões) usando função de ativação *tanh escalonada*.  
- **Treinamento**:  
  - Função de custo baseada em *perplexidade* (Equação 6), com regularização L2.  
  - Retropropagação em todas as camadas, exceto na CNN (fixa devido ao tamanho reduzido dos *datasets*).  
- **Tarefas**:  
  - **Geração de Sentenças**: Amostragem da distribuição de probabilidade da camada *softmax*.  
  - **Recuperação**: *Perplexidade* normalizada como métrica de afinidade imagem-texto.  

***
### 3. **Principais Contribuições**  

- **Arquitetura Inovadora**: Primeiro trabalho a integrar RNN e CNN em um modelo multimodal profundo, permitindo modelagem contextual de sequências textuais e fusão com características visuais.  
- **Desempenho Superior**:  
  - **Geração**: Redução de 68% na *perplexidade* em relação ao estado da arte no IAPR TC-12.  
  - **Recuperação**: Aumento de ~10% no R@1 em comparação a métodos como *DeepFE-rcnn* no Flickr8K.  
- **Flexibilidade**: O modelo é adaptável a diferentes recursos visuais (ex: características baseadas em detecção de objetos).  
- **Aplicabilidade**: Demonstrou eficácia em três *datasets* distintos, validando sua generalização.  

***
### 4. **Limitações e Lacunas**  

- **Recursos Visuais Fixos**: A CNN (AlexNet) não foi ajustada durante o treinamento devido ao tamanho limitado dos *datasets*, possivelmente subutilizando informações visuais.  
- **Métricas de Avaliação**:  
  - Uso de BLEU, que penaliza variações linguísticas válidas não presentes nas sentenças de referência.  
  - Falta de métricas semânticas (ex: *CIDEr* ou *SPICE*) para avaliar a relevância do conteúdo gerado.  
- **Comparações Limitadas**: Para geração de texto no Flickr8K/Flickr30K, apenas o modelo base (RNN sem imagem) foi usado como comparação, sem dados públicos de métodos anteriores.  
- **Escalabilidade**: O treinamento em *datasets* maiores (ex: COCO) não foi explorado, limitando a validação de robustez.  
- **Viés em Recuperação**: A normalização da *perplexidade* para recuperação de texto assume distribuição uniforme de imagens, o que pode não refletir cenários reais.  
