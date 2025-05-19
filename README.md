
## Grupo MotoTrack

## integrantes:
    
    RM558317 - Cauã Sanches de Santana

    RM556511 - Angello Turano da Costa

    RM558576 - Leonardo Bianchi



# 🏍️ Rastreamento Inteligente de Motos com RFID e Visão Computacional

## 📌 Problema

Empresas que trabalham com locação de motos, como a Mottu, enfrentam dificuldades para localizar veículos em ambientes fechados como depósitos e pátios. Tecnologias tradicionais como GPS apresentam baixa ou nenhuma precisão nesses ambientes, comprometendo a logística e a segurança.

## 🎯 Solução Proposta

Desenvolvemos um sistema híbrido de rastreamento de motos utilizando **sensores RFID** e **visão computacional com IA** para oferecer:

- Localização precisa das motos 
- Automação do monitoramento de entradas e saídas no pátio
- Baixo custo de manutenção e escalabilidade

---

## 🧠 Frameworks, Bibliotecas e Algoritmos

### 🔧 Tecnologias Utilizadas

| Tecnologia       | Uso Principal                                   |
|------------------|--------------------------------------------------|
| **Python**       | Linguagem base para scripts e backend           |
| **Flask / FastAPI** | Criação de API REST para consulta e registro de localização |
| **OpenCV**       | Processamento de imagens da visão computacional |
| **YOLOv5**       | Detecção de motos via câmera                    |
| **PySerial**     | Comunicação com sensores RFID via Arduino       |
| **Pandas**       | Manipulação e análise de dados registrados      |

---

### 📈 Técnicas e Algoritmos

- **RFID Passivo e Ativo**  
  Leitores distribuídos pelo pátio detectam etiquetas nas motos e enviam informações via serial para o sistema central.

- **YOLOv5 (You Only Look Once)**  
  Algoritmo de detecção de objetos usado para identificar motos em tempo real em imagens/vídeos.

- **Sistema Híbrido**  
  A IA por imagem valida visualmente as posições fornecidas pelos leitores RFID, criando uma redundância inteligente.

---

## 🏗️ Arquitetura do Sistema

```plaintext
                    +-----------------------------+
                    |       Interface Web/API     |
                    |     (Flask ou FastAPI)      |
                    +-------------+---------------+
                                  |
               +------------------v-------------------+
               |          Controlador Central          |
               |       Processamento em Python         |
               +--------+----------------+-------------+
                        |                |
         +--------------v--+         +---v-----------------+
         | Leitor RFID       |       | Câmera com YOLOv5   |
         | (Arduino + Tag)   |       | (Visão Computacional)|
         +-------------------+       +----------------------+

                            ↓
                      Banco de Dados
