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
<img src="/assets/img/Screen Shot 2021-09-27 at 3.11.13 PM.png">
<figcaption>Fig 5. PR Curve</figcaption>
</figure>

##### AP (Average Precision)

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.17.48 PM.png">
<figcaption>Fig 6. AP (Average Precision)</figcaption>
</figure>

