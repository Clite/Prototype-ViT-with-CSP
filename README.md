# Prototype_ViT_with_CSP (CSPNet 방식을 접목한 ViT)
(KR)

CSPNet의 아이디어인 절반의 feature만을 Conv layer로,
나머지 절반을 이후 concat하는 방식을 Vision Transformer(ViT)의 Attention layer에 적용한 모델

본 모델은 CIFAR-10 데이터셋 및 6개의 Encoder를 사용합니다.

* ver1과 ver2의 차이점
  * ver1 : feature map의 수를 기준으로 나눔
  * ver2 : patch size를 기준으로 나눔
* Spec 비교 (업로드 파일 기준)
  * 정확도는 ±1.5%p, 추론 시간은 ±2ms 정도의 차이가 발생할 수 있습니다

|모델|정확도|연산량|파라미터 수|추론 시간(patch size = 100)|
|:------:|:------:|:---:|:---:|:---------:|
|ViT|78.46%|616.86M|9.75M|45.17ms|
|CSP+ViT|79.09%|514.95M|6.6M|37.52ms|
|CSP ver2|77.8%|463.3M|5.81M|36.02ms|

Pre-trained model의 경우, 용량 문제로 CSPNet을 적용한 두 가지 모델만 압축 파일로 제공합니다.
***
(EN)

Sending only half of the feature to the conv layer, according to CSPNet idea,
concatting the other half to the Attention layer of Vision Transformer(ViT) model

This model uses the CIFAR-10 dataset and 6-encoders.

* Comparison between ver1 and ver2
  * ver1 : Apply chunk() to feature map dimension
  * ver2 : Apply chunk() to patch size dimension
* Spec comparison (Based on upload file)
  * Accuracy may vary by ±1.5%p and inference time may vary by ±2ms

|Model|Accuracy|FLOPS|# of parameters|Inference time(patch size = 100)|
|:------:|:------:|:---:|:---:|:---------:|
|ViT|78.46%|616.86M|9.75M|45.17ms|
|CSP+ViT|79.09%|514.95M|6.6M|37.52ms|
|CSP ver2|77.8%|463.3M|5.81M|36.02ms|

Due to capacity issues, pre-trained model is uploaded by zip file only two CSPNet-applied models.
***
## Index
* **Package install & Library import**
* **Sub-design**
  * Multi-Head Self-Attention layer
* **Hyperparameter & Dataset**
* **Vanilla ViT**
  * Encoder
  * ViT(Vision Transformer)
  * Setting
  * Train & Test
* **ViT+CSP**
  * Encoder
  * ViT+CSP
  * Setting
  * Train & Test
* **ViT+CSP version 2**
  * MHA ver2
  * Encoder
  * ViT+CSP version2 
  * Setting
  * Train & Test
* **Spec comparison**
  * Accuracy
  * FLOPS & Parameters
  * Inference time
* **Model save & load (colab only)**
