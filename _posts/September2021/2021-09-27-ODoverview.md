---
layout: post
title: ๐ Object Detect Comp | Overview
date: 2021-09-27 07:44 +0900
#modified: 2021-07-30 18:49 +0900
description: ๊ฐ์ฒด ๊ฒ์ถ ๋ํ๋ฅผ ์ํ ๋ชจ๋ธ์ ๋ง๋๋ ๊ณผ์ 
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

* ์ด๋ฏธ์ง ์ ๊ฐ์ฒด ๊ตฌ๋ถ๊ณผ ๋ถ๋ฅ๋ฅผ ํจ
* ํ ์ด๋ฏธ์ง์์ ์ฌ๋ฌ ๊ฐ์ ๊ฐ์ฒด๊ฐ ์์ ์ ์์

### Real World Example

* ์์จ์ฃผํ
* OCR
* ์๋ฃ ๋๋ฉ์ธ (X-ray์์ ์์ฌ๋๋ ๋ณ ๊ฒ์ถ)
* CCTV๋ก ์ฌ๋ ํ๋ ๊ฒ์ถ

### History

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 2.44.09 PM.png">
<figcaption>Fig 2. Object detection history</figcaption>
</figure>

# Evaluation

### ์ฑ๋ฅ

##### mAP (mean average precision)

* ๊ฐ ํด๋์ค๋น AP์ ํ๊ท 
* ๊ณ์ฐํ๊ธฐ ์ํด ํ์ํ ๊ฐ๋
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

* ๋จผ์  Confidence level๋ก ์ ๋ ฌ์ ํ ๋ค์
* ๋์  TP์ ๋์  FP๋ฅผ ๊ตฌํด ๊ฐ ์ ๋ง๋ค์ Precision๊ณผ Recall ๊ฐ์ ๊ณ์ฐํ๋ค
* ๊ทธ๋ํ X-axis์ y-axis ๊ฐ๊ฐ์ Recall๊ณผ Precision ๊ฐ์ ์๋ ฅํ ๊ฒ์ด PR Curve

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.11.13 PM.png" width="500">
<figcaption>Fig 5. PR Curve</figcaption>
</figure>

##### AP (Average Precision)

<figure>
<img src="/assets/img/Screen Shot 2021-09-27 at 3.17.48 PM.png" width="500">
<figcaption>Fig 6. AP (Average Precision)</figcaption>
</figure>

* PR Curve์์ ์ ์ ๊ทธ์ด ์์ ๊ฐ์ ์๋ ๋ฉด์ ์ ๊ตฌํ๋ฉด ๊ทธ๊ฒ์ด AP๊ฐ ๋๋ค
* 0๊ณผ 1 ์ฌ์ด์ ๊ฐ์ ๊ฐ์ง๊ฒ ๋๋ค

##### mAP (Mean Average Precision)

$$mAP=\frac{1}{n}\sum^{k=n}_{k=1}AP_k$$

$$AP_k$$ = the AP of class k\
n = the number of classes

##### IOU (Intersection Over Union)

$$IOU=\frac{overlapping\:region}{combined\:region}$$

* bbox์ ์ ํ๋๋ฅผ ์ธก์ 
* ์์ธกํ bbox๊ฐ ground truth bbox์ ์ผ๋ง๋ ๊ฒน์ณ์ง๋๊ฐ
* percentage๋ฅผ ์ ํด์ ๊ทธ ๊ฐ๋ณด๋ค ๋๊ฒ ๋์ค๋ฉด ์ธ์ 
* mAP์ ํจ๊ป ๋ถ์ฌ๋๋ค (mAP50, mAP60...)

### ์๋

* FPS (Frames Per Second)
* FLOPs (Floating Point Operations)

# Library

* MMdetection
  * pytorch๊ธฐ๋ฐ์ธ object detection ์คํ์์ค
* Detectron2
  * Detectron2๋ ํ์ด์ค๋ถ AI ๋ฆฌ์์น์ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ก pytorch ๊ธฐ๋ฐ์ Object detection๊ณผ segmentation์ ์๊ณ ๋ฆฌ์ฆ์ ์ ๊ณต
* YOLOv5
  * COCO ๋ฐ์ดํฐ์์ผ๋ก ์ฌ์  ํ์ต๋ ๋ชจ๋ธ๋ก ์์ฒ ์๊ฐ์ ์ฐ๊ตฌ์ ๊ฐ๋ฐ์ ๊ฑธ์ณ ๋ฐ์ ๋ Object Detection ๋ชจ๋ธ
  * Colab, kaggle, Docker, AWS, Google Cloud Platform ๋ฑ ์์ ์คํ ์์ค๋ฅผ ์ ๊ณต
* EfficientDet
  * Google Research & Brain์์ ์ฐ๊ตฌํ ๋ชจ๋ธ๋ก EfficientNet์ ์์ฉํด ๋ง๋  Object Detection ๋ชจ๋ธ
  * Tensorflow๋ก ์ ๊ณต๋๋ EfficientDet์ ์ฌ์ฉํ  ์ ์์ผ๋ฉฐ, ๊นํ์ pytorch ๊ธฐ๋ฐ์ผ๋ก ๊ตฌํ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ญ์ ์กด์ฌ