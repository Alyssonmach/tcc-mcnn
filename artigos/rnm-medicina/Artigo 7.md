***

## Multimodal medical image fusion algorithm in the era of big data

### 1. **Resumo do Artigo**  

**Objetivo:**  
Propor um algoritmo de fusão de imagens médicas multimodais (**BM-PCNN-NSST**) que combina a transformada shearlet não subamostrada (NSST) e uma rede neural pulse-coupled (PCNN) modulada por medidas de borda. O objetivo é integrar informações de diferentes modalidades (ex.: MRI, PET, SPECT) para melhorar a precisão do diagnóstico médico.  

**Metodologia:**  
- **Decomposição NSST**: Divide as imagens em sub-bandas de baixa frequência (informações estruturais) e alta frequência (detalhes finos).  
- **Fusão de Baixa Frequência**: Utiliza uma estratégia baseada em atributos de energia (EA) para combinar informações estruturais.  
- **Fusão de Alta Frequência**: Aplica um modelo PCNN modulado por gradientes morfológicos multiescala (MSMG) para preservar detalhes.  
- **Reconstrução NSST**: Combina as sub-bandas fusionadas para gerar a imagem final.  

**Resultados:**  
- **Qualitativos**: Imagens fusionadas preservam detalhes críticos sem artefatos de blocagem (Figs. 5–11).  
- **Quantitativos**: Superioridade em métricas como **entropia (EN)**, **desvio padrão (SD)** e **similaridade estrutural (SS)**. Por exemplo, para glioma (MRI-PET), o método proposto obteve **EN = 3,43** e **SS = 0,73**, superando outros 7 métodos (Tabelas 1–7).  
- **Eficiência**: Processamento rápido (parâmetros pré-definidos) e adaptável a múltiplas doenças.  

**Conclusões:**  
O BM-PCNN-NSST demonstra desempenho superior ao integrar estratégias específicas para diferentes escalas de frequência, sendo adequado para aplicações clínicas que exigem precisão e preservação de detalhes.  

***
### 2. **Metodologia Utilizada**  

- **Transformada Shearlet Não Subamostrada (NSST)**:  
  - Decomposição multiescala e multidirecional para capturar características estruturais e detalhes.  
  - Parâmetros: 4 níveis de decomposição e direções variáveis (16, 16, 8, 8).  
- **Estratégia de Fusão de Baixa Frequência (EA)**:  
  - Calcula atributos de energia baseados em média e mediana para ponderar informações estruturais.  
  - Equações: $( L_F(x,y) = \frac{E_A \cdot L_A + E_B \cdot L_B}{E_A + E_B})$.  
- **PCNN Modulado por MSMG para Alta Frequência**:  
  - Gradientes morfológicos multiescala (MSMG) ajustam a força de ligação (\(\beta\)) na PCNN.  
  - Ativação iterativa de neurônios para selecionar detalhes relevantes.  
- **Avaliação**:  
  - **Métricas**: Entropia (EN), desvio padrão (SD), informação mútua normalizada (NMI), similaridade estrutural (SS), fidelidade visual (VIF).  
  - **Conjunto de Dados**: 100+ pares de imagens de doenças como glioma, Alzheimer e carcinoma broncogênico.  

***
### 3. **Principais Contribuições**  

- **Integração de NSST e PCNN**: Combinação inédita de decomposição multiescala com redes neurais bioinspiradas para fusão de imagens.  
- **Estratégias Adaptativas**:  
  - Fusão de baixa frequência via EA mantém informações estruturais.  
  - Fusão de alta frequência via PCNN-MSMC preserva detalhes finos e bordas.  
- **Desempenho Superior**:  
  - **EN** e **SS** consistentemente mais altos que métodos como CNN, LLF-IOI e NSST-PAPCNN.  
  - Redução de artefatos (ex.: blocagem) em comparação com técnicas tradicionais.  
- **Aplicabilidade Clínica**: Validação em múltiplas patologias, incluindo casos complexos como encefalopatia hipertensiva.  

***
### 4. **Limitações e Lacunas** 

- **Dependência de Parâmetros Pré-Definidos**:  
  - O desempenho ótimo exige ajuste manual de $(\alpha = 4) e (t = 3)$ (Apêndice), o que pode limitar a generalização.  
- **Registro Perfeito das Imagens**:  
  - Requer pares de imagens perfeitamente alinhados, o que é difícil em ambientes clínicos reais.  
- **Falta de Dados Longitudinalis**:  
  - Não aborda a fusão de séries temporais (ex.: evolução da pressão intraocular em glaucoma).  
- **Interpretabilidade Limitada**:  
  - Embora Grad-CAM seja mencionado, a correlação entre regiões destacadas e critérios clínicos não foi explorada.  
- **Conjunto de Dados Restrito**:  
  - Validação apenas no *Whole Brain Atlas*; falta diversidade em populações e equipamentos médicos.  