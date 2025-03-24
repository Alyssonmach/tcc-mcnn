# Principais Bases de Dados
***

* [CMRxRecon2024](https://pubs.rsna.org/doi/full/10.1148/ryai.240443): A Multimodality, Multiview k-Space Dataset Boosting..." publicado na Radiology: Artificial Intelligence descreve um dataset multimodal de ressonância magnética cardíaca (CMR). A base de dados inclui imagens adquiridas a partir de diferentes modalidades e perspectivas anatômicas, proporcionando um conjunto abrangente para reconstrução e análise de IA. O dataset tem potencial para melhorar a precisão de modelos de reconstrução de imagens médicas.

***

*[Multimodal Healthcare - GitHub](https://github.com/multimodal-healthcare/): disponibiliza diversos datasets e modelos voltados para aplicações médicas utilizando múltiplas modalidades de dados. Os principais repositórios incluem:

1. **ECG** - Contém modelos para análise de eletrocardiogramas (ECG), utilizando aprendizado profundo para a classificação de sinais cardíacos. Inclui scripts de treinamento baseados no dataset MIT-BIH [PhysioNet](https://www.physionet.org/) 【19】.

2. **MRI** - Foca no diagnóstico de doenças cardiovasculares por meio de imagens de ressonância magnética (MRI). O repositório contém 298 exames no formato DICOM (256x256x256) e técnicas para segmentação e análise automática【20】.

3. **EHR (Electronic Health Records)** - Desenvolve modelos para lidar com registros médicos eletrônicos, buscando estruturar e interpretar dados clínicos para suporte ao diagnóstico【21】.

4. **Genomics** - Implementa um modelo baseado em PyTorch para prever riscos cardíacos a partir de informações genômicas, incluindo integração de dados do **UK Biobank** para análise poligênica【23】.

5. **Fusion** - Explora a fusão de múltiplas modalidades de dados médicos (como ECG, MRI, EHR e Genômica) para melhorar a precisão dos diagnósticos através da combinação de diferentes fontes de informação【22】.

***

* [Human Heart Project](https://humanheart-project.creatis.insa-lyon.fr/databases.html) oferece diversos bancos de dados multimodais voltados para o estudo da imagem cardíaca. Entre os principais datasets disponíveis estão:

- **TED Database**: Sequências de ultrassom cardíaco 2D+t com anotações manuais.
- **ACDC Database**: Cine-MRI de 150 pacientes, categorizados em 5 classes cardíacas.
- **CETUS Database**: Sequências de ultrassom cardíaco 3D+t para segmentação endocárdica.
- **Multimodal Straus**: Combina cine-MRI, tagged-MRI e ultrassom 3D+t.

***

* [Multimodal Cardiography Learning](https://github.com/willparker123/multimodal-cardiography-learning): contém a implementação de um modelo Transformer para a classificação de doenças cardiovasculares usando dados sincronizados de eletrocardiograma (ECG) e fonocardiograma (PCG). O projeto combina dois conjuntos de dados independentes: **Ephnogram**, que contém apenas amostras normais de adultos saudáveis, e **Physionet (desafio PhysioNet/CinC 2016)**, que inclui tanto amostras normais quanto casos de doenças cardiovasculares.

O pipeline do projeto envolve:
- **Pré-processamento e limpeza de dados** (divisão em segmentos, filtragem e transformações como STFT e CWT).
- **Fusão dos conjuntos de dados** para criar um dataset multimodal combinado (MM-ECGPCG).
- **Treinamento de um modelo Transformer** que aprende a partir das representações combinadas de ECG e PCG.
- **Geração de espectrogramas** para visualizar padrões nos sinais cardíacos.

***

* O dataset [EPHNOGRAM](https://physionet.org/content/ephnogram/1.0.0/) do PhysioNet contém gravações simultâneas de eletrocardiograma (ECG) e fonocardiograma (PCG) de 24 adultos saudáveis (23 a 29 anos). Os dados foram coletados durante testes físicos (repouso, caminhada, corrida e ciclismo) para estudar a relação entre os sinais elétricos e mecânicos do coração. O conjunto inclui 69 gravações (30s ou 30min) e pode ser usado para pesquisa em análise multimodal de ECG e PCG.

