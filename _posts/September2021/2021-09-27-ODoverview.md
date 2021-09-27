---
layout: post
title: 🔍 Object Detect Comp | Overview
date: 2021-09-27 07:44 +0900
#modified: 2021-07-30 18:49 +0900
description: 객체 검출 대회를 위한 모델을 만드는 과정
tag:
  - Boostcamp AI
  - P-stage
  - Object Detection Competition
# image: /cara-memperbarui-fork-repository/repo.png
usemathjax: true
---

# Object Detection

### Task

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 2.38.37 PM.png" width="300">
<figcaption>Fig 1. Object detection example</figcaption>
</figure>

* 이미지 속 객체 구분과 분류를 함
* 한 이미지안에 여러 개의 객체가 있을 수 있음

### Real World Example

* 자율주행
* OCR
* 의료 도메인 (X-ray에서 의심되는 병 검출)
* CCTV로 사람 행동 검출

### History

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 2.44.09 PM.png">
<figcaption>Fig 2. Object detection history</figcaption>
</figure>

# Evaluation

### 성능

##### mAP (mean average precision)

* 각 클래스당 AP의 평균
* 계산하기 위해 필요한 개념
    * Confusion matrix
    * Precision & Recall
    * PR curve
    * AP (Average Precision)
    * IOU (Intersection Over Union)

##### Confusion Matrix

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 2.50.34 PM.png">
<figcaption>Fig 3. Confusion matrix</figcaption>
</figure>

##### Precision

$$Precision=\frac{TP}{TP+FP}=\frac{TP}{All\:Detections}$$

##### Recall

$$Recall=\frac{TP}{TP+FN}=\frac{TP}{All\:Ground\:Truths}$$

##### PR Curve

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.01.42 PM.png">
<figcaption>Fig 4. Calculation table for PR Curve</figcaption>
</figure>

* 먼저 Confidence level로 정렬을 한 다음
* 누적 TP와 누적 FP를 구해 각 셀 마다의 Precision과 Recall 값을 계산한다
* 그래프 X-axis와 y-axis 각각에 Recall과 Precision 값을 입력한 것이 PR Curve

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.11.13 PM.png" width="500">
<figcaption>Fig 5. PR Curve</figcaption>
</figure>

##### AP (Average Precision)

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.17.48 PM.png" width="500">
<figcaption>Fig 6. AP (Average Precision)</figcaption>
</figure>

* PR Curve에서 선을 그어 위와 같은 아래 면적을 구하면 그것이 AP가 된다
* 0과 1 사이의 값을 가지게 된다

##### mAP (Mean Average Precision)

$$mAP=\frac{1}{n}\sum^{k=n}_{k=1}AP_k$$

$$AP_k$$ = the AP of class k\
n = the number of classes

##### IOU (Intersection Over Union)

$$IOU=\frac{overlapping\:region}{combined\:region}$$

* bbox의 정확도를 측정
* 예측한 bbox가 ground truth bbox와 얼마나 겹쳐지는가
* percentage를 정해서 그 값보다 높게 나오면 인정
* mAP와 함께 부여된다 (mAP50, mAP60...)

### 속도

* FPS (Frames Per Second)
* FLOPs (Floating Point Operations)

# Library

* MMdetection

* Detectron2
* YOLOv5
* EfficientDet