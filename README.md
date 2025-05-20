
## Grupo MotoTrack

## integrantes:
    
    RM558317 - Cauã Sanches de Santana

    RM556511 - Angello Turano da Costa

    RM558576 - Leonardo Bianchi

🚀 Projeto MotoTrack: Visão Computacional para Gestão de Frotas
📌 Tema
O tema deste projeto é “Visão Computacional para Gestão de Frotas de Motos”, com foco na empresa fictícia MotoTrack, especializada na locação e manutenção de motocicletas para serviços de entrega.

❗ Problema
A MotoTrack possui diversos pátios de armazenamento de motos em diferentes regiões da cidade. Atualmente, a gestão da frota é feita de forma manual, o que gera alguns desafios:

Falta de controle automatizado sobre a localização, estado e modelo das motos;

Erros humanos durante a verificação de condições das motos (checklist);

Tempo elevado na realização de auditorias nos pátios;

Risco de inconsistências entre o cadastro digital e a realidade física das motos.

💡 Alternativas de Solução
Sistema baseado em planilhas e QR Code: baixo custo, mas ainda dependente de operação humana.

RFID com sensores físicos: eficiente, porém exige infraestrutura física cara.

Visão Computacional com Inteligência Artificial (IA): alternativa escalável e automatizada para identificação de motos e análise da frota — solução escolhida neste projeto.

🛠️ Bibliotecas e Frameworks Python Utilizados
Biblioteca	Uso Principal
pandas	Manipulação de dados tabulares (criação, leitura e tratamento de dataset).
scikit-learn	Pré-processamento dos dados e particionamento em treino/teste.
xgboost	Algoritmo de aprendizado de máquina para classificação precisa dos modelos de moto.
matplotlib + seaborn	Visualização de resultados e geração da matriz de confusão.
opencv-python	(Futuramente) integração com imagens reais das motos para análise visual.

🧠 Arquitetura de IA
Algoritmo Escolhido: XGBoost Classifier
O XGBoost (Extreme Gradient Boosting) é um dos algoritmos de aprendizado supervisionado mais eficazes para tarefas de classificação multiclasse, como no nosso caso (identificar o modelo da moto com base em informações do pátio e condição da moto).

Motivos da Escolha:
Alta performance em datasets estruturados;

Robusto contra overfitting;

Otimizações internas que aumentam a velocidade e precisão.

Implementação:
Pré-processamento:

LabelEncoder para transformar atributos categóricos (condição, pátio, modelo) em numéricos.

Separação do dataset em X (features) e y (target).

Divisão entre train (70%) e test (30%).

Treinamento do Modelo:

Modelo treinado com parâmetros otimizados (max_depth, n_estimators, learning_rate).

Avaliação:

Métrica de acurácia e matriz de confusão para avaliação do desempenho do modelo.

📊 Base de Dados
A base de dados foi simulada com lógica realista baseada nos padrões de operação da empresa:

5.000 registros gerados, cada um representando uma moto com:

Número de identificação (Bluetooth ID)

Modelo da moto (Mottu Sport, Mottu E, Mottu Pop)

Condição da moto (Nova, Usada, Manutenção)

Localização (Unidade Belém, Tatuapé, Santo Amaro, etc.)

O arquivo final do dataset é salvo como:
📁 motos_dataset.csv

📷 Próximos Passos
Implementar integração com vídeos/imagens reais utilizando OpenCV e YOLOv5 para detecção visual das motos no pátio.

Automatizar identificação de placas ou QR codes para controle de entrada/saída das motos.

Implementar dashboard em Flask para visualização dos dados em tempo real.

📁 Estrutura do Projeto
bash
Copiar
Editar
MotoTrack/
│
├── motos_dataset.csv                # Base de dados simulada
├── gerar_dataset.py                # Script para criação do dataset
├── treino_modelo.py                # Script com treino do XGBoost
├── avaliacao_modelo.py             # Script da matriz de confusão
├── README.md                       # Este arquivo
└── imagens/                        # Logos e gráficos gerados