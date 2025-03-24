***
## Learning Multimodal Neural Network with Ranking Examples

#### 1. **Resumo do Artigo**  

**Objetivo:**  
Propor um modelo de rede neural multimodal (**CMRNN**) para melhorar a recuperação de informações entre modalidades distintas (ex.: texto e imagem), integrando técnicas de *learning to rank* e aprendizado de representações de alto nível. O objetivo é reduzir a lacuna de heterogeneidade entre modalidades e otimizar diretamente o desempenho de recuperação cruzada.  

**Metodologia:**  
- **Arquitetura CMRNN:** Utiliza redes neurais específicas para cada modalidade (texto e imagem) para mapear dados em um espaço latente comum.  
- **Função de ranqueamento:** Mede a similaridade via produto escalar entre os vetores latentes das modalidades.  
- **Função de perda listwise:** Calcula a divergência entre rankings previstos e reais usando entropia cruzada, retropropagando o erro para ajustar as redes.  
- **Pré-treinamento:** Autoencoders são usados para inicializar as redes específicas de cada modalidade.  

**Resultados:**  
- Superou métodos *state-of-the-art* (PAMIR, SSI, LSCMR) em **MAP** (*Mean Average Precision*) no dataset Wikipedia (0.2712 vs. 0.2520 para texto-query-imagem).  
- No dataset NUS-WIDE, obteve melhor desempenho apenas na direção texto-query-imagem (MAP de 0.3193 vs. 0.2163 do SSI), mas foi superado pelo PAMIR em imagem-query-texto (0.2319 vs. 0.2331).  

**Conclusões:**  
- A integração de redes neurais com perda de ranqueamento listwise permite aprender representações alinhadas entre modalidades, otimizando diretamente a tarefa de recuperação cruzada.  
- O modelo é eficaz em cenários com dados textuais ricos (ex.: Wikipedia), mas enfrenta desafios com textos curtos e ambíguos (ex.: NUS-WIDE).  

***
#### 2. **Metodologia Utilizada**  

- **Redes Neurais Modais:**  
  - **Texto:** Rede neural com camadas densas (ex.: 5000-50 unidades no Wikipedia).  
  - **Imagem:** Rede neural com camadas densas (ex.: 1000-50 unidades no Wikipedia).  
  - Saídas mapeadas para um espaço latente comum (\(K\)-dimensional).  
- **Função de Similaridade:**  
  - Produto escalar entre os vetores latentes do texto (\(f_u(q)\)) e da imagem (\(f_v(d)\)).  
- **Função de Perda Listwise:**  
  - Baseada em probabilidade "top one" (Eq. 2) e entropia cruzada (Eq. 3).  
  - Retropropagação adaptada para atualizar pesos das redes modais (Eqs. 4–6).  
- **Treinamento:**  
  - Mini-batches de 100 exemplos.  
  - Otimização com gradiente descendente e *momentum* (0.3).  
  - Pré-treinamento com autoencoders para inicialização.  

**Ferramentas e Dados:**  
- **Datasets:** Wikipedia (2.866 documentos) e NUS-WIDE (133.208 imagens).  
- **Métricas:** MAP@50 e MAP@all para avaliação.  

***
#### 3. **Principais Contribuições**  

- **Integração de redes neurais e *learning to rank*:**  
  - Combina aprendizado de representações profundas com otimização direta do ranking, eliminando a necessidade de *features* manuais.  
- **Aprendizado end-to-end:**  
  - A perda de ranqueamento é retropropagada para ajustar as redes modais, alinhando as representações latentes de texto e imagem.  
- **Eficiência em grandes volumes de dados:**  
  - Uso de mini-batches permite escalabilidade, superando métodos como LSCMR (que requerem *full-batch*).  
- **Resultados empíricos robustos:**  
  - Demonstra superioridade em datasets com textos descritivos (ex.: Wikipedia), validando a utilidade do modelo em cenários complexos.  

***
#### 4. **Limitações e Lacunas**  

- **Desempenho variável entre datasets:**  
  - No NUS-WIDE, a direção imagem-query-texto teve desempenho inferior ao PAMIR, possivelmente devido à brevidade e ambiguidade das tags textuais.  
- **Dependência de pré-processamento:**  
  - Uso de autoencoders para inicialização pode introduzir viés, limitando a generalização.  
- **Complexidade computacional:**  
  - Treinamento de redes neurais profundas exige recursos significativos, especialmente em datasets grandes como NUS-WIDE.  
- **Generalização para outras modalidades:**  
  - O modelo foi testado apenas em pares texto-imagem, não explorando áudio, vídeo ou outras combinações.  
- **Ruído em dados reais:**  
  - O uso de *clicks* ou tags como *judgments* pode introduzir ruído, afetando a qualidade do treinamento.  