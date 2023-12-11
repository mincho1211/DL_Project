# 딥러닝 프로젝트

## Introduction
1. 문제 분석
   * 제조업체들은 제품의 품질과 신뢰성을 유지 및 안전성 확보를 위해 부품의 불량을 신속하게 탐지해야 함
   * 그러나 정상과 비정상 부품의 이미지를 대량으로 수집하고 라벨링하는 것은 현실적으로 어려움
   * 대부분의 제조 업체는 수작업 감별을 진행
   * 적은 양의 데이터로도 효과적인 학습이 가능한 ‘Few-shot learning’ 기반의 모델이 필요
3. 프로젝트 주제
   * Few-shot Learning 기반 이상탐지 모델 구현
4. 프로젝트 목표
   * ﻿거리 기반 학습에 해당하는 Siamese Network 모델과 최적화 학습에 해당하는 MAML 모델을 구축하여 두 모델의 성능을 비교
   * ﻿2-way K-shot learning에 대해 K값에 따른 성능을 비교

## Dataset
* ﻿실제 제조업체에서 사용되고 있는 PCB 부품 이미지
* ﻿MVTec Anomaly Detection(이상 탐지) 공개 데이터셋

## Model
1. MAML(Model-Agnostic Meta-Learning)
   * ﻿여러 task에 대해서 적합한(broadly suitable for many tasks) 모델을 학습하면 세부 task 에 적용할 때 fine-tuning 과정이 빠를 것이라는 아이디어에 기반한 모델
2. 샴 네트워크(Siamese Network)
   * ﻿샴 쌍둥이에서 착안된 네트워크로, 동일한 weight을 공유하는 twin networks로 이루어짐
   * 한 쌍의 입력을 받아 각각의 특징을 추출하여 두 이미지 간의 유사도를 계산하고, 유사도를 이용하여 클래스를 분류

## Results
﻿* Query set에 대한 예측 정확도를 평가 지표로 사용
* ﻿MAML 모델이 SiameseNet 모델에 비해 더 우수한 성능
* MVTec 데이터셋의 경우 정상과 이상 이미지 간의 차이가 미세하여, SiameseNet 모델의 정확도가 매우 낮음
* MAML 모델은 MVTec 데이터셋에 대해서도 비교적 우수한 성능을 보임
﻿* K(Shot 개수)가 증가할수록 대체로 정확도가 향상됨
