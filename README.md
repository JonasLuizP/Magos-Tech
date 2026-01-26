# 🧠 NeuroScan AI - Aplicativo móvel para detecção de tumores cerebrais utilizando redes neurais convolucionais.

Projeto acadêmico de Inteligência Artificial para auxílio no diagnóstico radiológico utilizando Deep Learning em dispositivos móveis.

## 📋 Sobre o Projeto:

Este projeto visa desenvolver uma solução capaz de identificar a presença de tumores cerebrais em imagens de Ressonância Magnética (RM).

O diferencial da solução é o uso da arquitetura MobileNetV2 via Transfer Learning, permitindo que o modelo seja leve o suficiente para funcionar em dispositivos móveis (Android/iOS), auxiliando médicos na obtenção de diagnósticos mais precisos e rápidos.

## 🚀 Tecnologias Utilizadas:

Linguagem: Python (Google Colab)

Framework de IA: TensorFlow & Keras

Modelo Base: MobileNetV2 (Transfer Learning)

Otimização: TensorFlow Lite (.tflite)

Técnicas: Data Augmentation, Class Weights (para balanceamento de dados).

## 📊 Resultados Alcançados No Treinamento:

O modelo foi treinado com um dataset de RMs cerebrais e obteve os seguintes resultados na validação:

Acurácia: 96.52%

Loss (Perda): 0.1299

Tamanho do Modelo: ~9 MB (Otimizado para Mobile)

## 📊 Resultados Alcançados No Teste:

O modelo foi submetido a um teste contendo 20 imagens, 10 com tumor e 10 sem tumor. Obtivendo os seguintes resultados:

Acurácia real: 90%

Acertos: 18

Erros: 2

Conclusão: O modelo é válido para auxiliar um médico.

## 📂 Estrutura dos Arquivos:

- CÓDIGO:
|
| Detecção_do_Tumor_Cerebral.ipynb: Código completo de treinamento, balanceamento e conversão.
| Teste_do_Modelo.ipynb: Código para testar o modelo com novas imagens.

- MODELOS IA:
|
| modelo_tumor_final.keras: Modelo final compatível com sistemas computacionais, para a realização de testes.
| modelo_tumor_final.tflite: Modelo final convertido para dispositivos móveis, pronto para ser integrado ao App.

## 💾 Dataset

Devido ao tamanho dos arquivos, as imagens utilizadas para treinamento não estão neste repositório.
O dataset original pode ser encontrado em:

Fonte: [https://www.kaggle.com/code/eslammohamed100/brain-tumor-classification-mri/input]

Estrutura: 
- Treinamento:
  2475 imagens de Tumor (dividida em tipos) e 395 imagens Normais.
  
- Teste:
  289 imagens de Tumor (dividida em tipos) e 105 imagens Normais.

## 👥 Autores

Bruno Rodrigues - Pesquisador e desenvolvedor mobile.

Felipe Gabriel - Pesquisador e documentação.

Jonas Rodrigues - Pesquisador e desenvolvedor IA

Este projeto foi desenvolvido para fins acadêmicos e não substitui o diagnóstico médico profissional.
