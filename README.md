# 👁️ Smart Vision Assist: Sensor Inteligente com Edge AI para Tecnologia Assistiva

> **Desafio de Projeto — Formação IoT Specialist (DIO)**  
> Aplicação de Visão Computacional e Edge AI transformando uma câmera em um sensor inteligente com feedback sonoro para auxílio a deficientes visuais.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-orange)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?logo=opencv)

---

## 📌 Sobre o Projeto

Em soluções modernas de **Internet das Coisas (IoT)** e **Cidades Inteligentes**, câmeras digitais atuam como sensores ópticos avançados (*Smart Sensors*). Em vez de depender exclusivamente de múltiplos sensores ultrassônicos ou infravermelhos tradicionais, uma única entrada visual combinada a modelos de **Edge AI** pode interpretar o contexto ao redor.

O **Smart Vision Assist** foi desenvolvido como uma tecnologia assistiva: ele captura imagens do ambiente, detecta obstáculos e objetos cotidianos (pessoas, cadeiras, mesas, veículos) utilizando o modelo **YOLOv8**, traduz as classes para o português e sintetiza alertas sonoros instantâneos via **Text-to-Speech (TTS)** para orientação de pessoas com deficiência visual.

---

## 🛠️ Arquitetura da Solução

O fluxo de dados segue a arquitetura de sensoriamento e atuação inteligente em IoT:

```
┌──────────────────┐      ┌────────────────────────┐      ┌───────────────────────┐      ┌──────────────────────┐
│  Entrada Visual  │ ───> │  Inferência (Edge AI)  │ ───> │  Lógica de Decisão    │ ───> │    Atuação Física    │
│ (Câmera / Frame) │      │     YOLOv8 (Nano)      │      │ (Filtro e Tradução)   │      │ (Áudio / Fala gTTS)  │
└──────────────────┘      └────────────────────────┘      └───────────────────────┘      └──────────────────────┘
```

1. **Captura:** O dispositivo lê os frames de entrada via OpenCV.
2. **Processamento (Edge AI):** O modelo YOLOv8 processa a imagem identificando objetos com alta precisão e baixa latência.
3. **Inteligência do Sensor:** O algoritmo filtra repetições de leitura, prioriza classes do cotidiano e gera uma mensagem contextual em português.
4. **Atuação:** O sintetizador de voz gera o alerta sonoro reproduzido diretamente no dispositivo de saída do usuário.

---

## 💻 Tecnologias Utilizadas

* **Linguagem:** Python 3
* **Visão Computacional & AI:** [Ultralytics YOLOv8](https://docs.ultralytics.com/) e [OpenCV](https://opencv.org/)
* **Sintetizador de Fala (TTS):** [gTTS (Google Text-to-Speech)](https://pypi.org/project/gTTS/)
* **Ambiente de Prototipagem:** Google Colab (com aceleração por GPU)

---

## 🚀 Como Executar o Projeto

Você pode reproduzir e testar o projeto de forma rápida e gratuita direto no seu navegador:

1. Acesse o **Google Colab**.
2. Abra o arquivo de notebook deste repositório (`Smart_Vision_Assist.ipynb`).
3. Execute as células em sequência:
   * **Instalação das dependências:** `!pip install ultralytics gTTS`
   * **Carregamento do modelo e funções de áudio.**
   * **Execução do sensor** com a imagem de teste ou foto da câmera.
4. O notebook exibirá a imagem anotada com as caixas delimitadoras e tocará o aviso sonoro correspondente.

---

## 📊 Exemplo de Saída

* **Imagem processada:**
  *(Dica: faça o upload do print do seu Colab com a imagem e a caixa de marcação e insira o link aqui)*
* **Log do Sensor:**
  ```text
  📢 [Sensor]: Atenção: identifiquei próximo a você: uma pessoa, um notebook.
  ```
* **Feedback de Áudio:** Arquivo `alerta.mp3` gerado e reproduzido em tempo real.

---

## 🔮 Próximos Passos e Evoluções Futuras

* [ ] Implementação de cálculo aproximado de distância com base no tamanho relativo da *Bounding Box*.
* [ ] Portabilidade para hardware embarcado dedicado (Raspberry Pi ou ESP32-CAM) com comunicação MQTT para telemetria em nuvem.
* [ ] Integração com feedback háptico (vibração) em cenários de ruído ambiente.

---

## 👨‍💻 Autor

Projeto desenvolvido por **[Jefferson Santos** como parte da Formação **IoT Specialist** da [DIO (Digital Innovation One)](https://dio.me).
