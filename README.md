# 🧠 NeuroScan AI

**Aplicativo móvel para detecção de tumores cerebrais em imagens de Ressonância Magnética utilizando Deep Learning**

Projeto acadêmico de Inteligência Artificial focado em **diagnóstico assistido por IA**, com execução real em **dispositivos móveis Android**, integrado a um **backend de inferência em nuvem**.

---

## 📋 Sobre o Projeto

O **NeuroScan AI** é uma solução completa que permite a um usuário (médico ou estudante) enviar uma imagem de Ressonância Magnética (RM) de um cérebro por meio de um aplicativo Android e receber, em poucos segundos, a **classificação automática**:

* **Normal**
* **Tumor**

Juntamente com:

* **Probabilidade (confiança da IA)**

O sistema utiliza uma arquitetura **MobileNetV2 via Transfer Learning**, otimizada para dispositivos móveis, porém executada em produção através de um **backend FastAPI**, garantindo maior desempenho, escalabilidade e compatibilidade.

---

## 🧠 Arquitetura da Solução

O sistema é dividido em três camadas:

```
[ App Android (MIT App Inventor) ]
                |
                |  (imagem via HTTP POST - multipart/form-data)
                |
        [ FastAPI + ngrok ]
                |
                |  (TensorFlow / Keras)
                |
        [ Modelo IA (.keras / .tflite) ]
```

Fluxo real de funcionamento:

1. O usuário seleciona uma imagem no celular.
2. O app envia a imagem via **POST multipart/form-data** para o backend FastAPI.
3. O backend processa a imagem, executa o modelo de IA.
4. O servidor retorna um JSON:

```json
{
  "status": "ok",
  "class": "Tumor",
  "confidence": 0.87
}
```

5. O aplicativo exibe o resultado e a confiança na tela.

---

## 🚀 Tecnologias Utilizadas

### 🔹 Inteligência Artificial

* **Python**
* **TensorFlow**
* **Keras**
* **MobileNetV2 (Transfer Learning)**
* **TensorFlow Lite (.tflite)**
* **Aumento de dados**
* **Pesos de classe (balanceamento)**

### 🔹 Backend

* **FastAPI**
* **Uvicorn**
* **Python**
* **ngrok (túnel público para API no Google Colab)**

### 🔹 Mobile

* **MIT App Inventor**
* Comunicação HTTP via `Web.PostFile`
* Processamento de JSON (`JsonTextDecodeWithDictionaries`)

---

## 📊 Resultados do Treinamento

O modelo foi treinado com um dataset científico de Ressonância Magnética:

| Métrica                  | Valor      |
| ------------------------ | ---------- |
| **Precisão (validação)** | **96,52%** |
| **Loss**                 | **0,1299** |
| **Tamanho do modelo**    | **~9 MB**  |

Modelo otimizado para execução em ambiente móvel e backend.

---

## 📊 Resultados em Testes Controlados

O modelo foi testado com **20 imagens reais**:

| Classe | Quantidade |
| ------ | ---------- |
| Tumor  | 10         |
| Normal | 10         |

| Resultado         | Valor   |
| ----------------- | ------- |
| **Acertos**       | 18      |
| **Erros**         | 2       |
| **Precisão real** | **90%** |

> O modelo mostrou boa capacidade de generalização, sendo adequado como **ferramenta de apoio ao diagnóstico**.

---

## 📱 Aplicativo Mobile

O aplicativo Android permite:

* Selecionar imagem da galeria
* Enviar para o servidor
* Receber:

  * Classe (Tumor ou Normal)
  * Confiança da IA
* Exibir os resultados na interface

A comunicação ocorre via:

```
Web1.PostFile → FastAPI → JSON → App Inventor
```

---

## 📂 Estrutura do Repositório

### 📁 CÓDIGO

* `Detecção_do_Tumor_Cerebral.ipynb`
  Treinamento completo, balanceamento, validação e conversão para `.tflite`

* `Teste_do_Modelo.ipynb`
  Script para validação do modelo com novas imagens

* `api.py` (FastAPI)
  Backend que recebe imagens, executa o modelo e retorna JSON

---

### 📁 MODELOS DE IA

* `modelo_tumor_final.keras`
  Modelo completo para testes científicos

* `modelo_tumor_final.tflite`
  Modelo otimizado para dispositivos móveis

---

## 💾 Conjunto de Dados

As imagens não estão no repositório devido ao tamanho.

Fonte:
[https://www.kaggle.com/code/eslammohamed100/brain-tumor-classification-mri/input](https://www.kaggle.com/code/eslammohamed100/brain-tumor-classification-mri/input)

| Conjunto    | Tumor | Normal |
| ----------- | ----- | ------ |
| Treinamento | 2.475 | 395    |
| Teste       | 289   | 105    |

---

## 👥 Autores

* **Bruno Rodrigues** – Desenvolvedor Mobile, Backend e Integração IA
* **Felipe Gabriel** – Documentação e Pesquisa
* **Jonas Rodrigues** – Treinamento e Modelagem da IA

---

## ⚖️ Aviso Legal

Este projeto foi desenvolvido **exclusivamente para fins acadêmicos e de pesquisa**.
Ele **não substitui** diagnóstico médico profissional, laudos radiológicos ou decisões clínicas.

---

Se quiser, posso agora:

* Ajustar para inglês
* Criar versão mais curta para apresentação
* Criar README técnico para banca ou professor
