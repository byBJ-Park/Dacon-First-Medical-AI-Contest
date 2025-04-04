# Dacon-First-Medical-AI-Contest
[![image](https://github.com/user-attachments/assets/d650005e-db27-45cf-9dda-9e1478aeaf24)](https://dacon.io/competitions/official/236382/overview/description)

Public score: 27/273(PCC: 0.54057)  
Private score: 90/273(PCC: 0.52843)  

![image](https://github.com/user-attachments/assets/032d1816-0a29-437e-9e8f-205ea0ca4edf)


*** 
### 1. albumentations 라이브러리를 이용한 Data Augmentation
 albumentations의 장점으로 기존의 torchvision이나 keras를 이용한 augmentation보다 빠른 속도를 지원하며, pytorch와 tensorflow와 같은 대중적인 framework를 지원하고 있다. 해당 라이브러리를 이용하여 데이터를 3배 수로 증가시켜서 훈련시켰다.
 
***
### 2. Model architecture
 데이터(train=(5593, 3469), valid=(1399, 3469))는 총 5593개의 row를 가지고 있어서, ViT를 사용하기 보다는 기존의 resnet을 사용이 더 좋은 결과를 불러올 것이라고 생각했다. torchvision에서 가장 성능 좋은 두 개의 모델 resnet152와 resnext101_32x8d을 사용해보고 최종적으로 resnext101_32x8d을 선택했다. 또한, feature extraction 뒷 단의 fully connected layer 또한 1 ~ 4 layer들을 모두 실험해본 결과 2 layer를 사용하는 방법이 가장 높은 성능을 가져왔다. 따라서 이번 모델은 resnext101_32x8d(feature extraction) + FFNN(2 layer)로 구성되어 있다. 
 
***
### 3. 느낀점
 먼저, 모델의 개수가 약 6000 정도로 적다 보니, ViT보다는 기존의 CNN 기반인 Resnet이 더 강력하다는 점을 배웠다. 여러 모델을 돌려보았지만, 가장 성능이 좋았던 resnext를 기반으로 실험을 진행하였다. 또한 feature extraction 뒷 단의 fully connected layer 층의 개수를 비교해보는 작업도 재밌었다. 대회에서 loss function을 구현하기 위한 정보를 조금 더 주었다면 더 좋은 모델을 만들 수 있을 것이라는 아쉬운 부분이 있었다.
 


