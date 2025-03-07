# InsightFace Track of ICCV21-MFR

The Masked Face Recognition Challenge & Workshop(MFR) will be held in conjunction with the International Conference on Computer Vision (ICCV) 2021. 

[Workshop-Homepage](https://ibug.doc.ic.ac.uk/resources/masked-face-recognition-challenge-workshop-iccv-21/). There're InsightFace track here and Webface260M track(with larger training set) in this workshop.

## Testsets for insightface track

In this challenge, we will evaluate the accuracy of following testsets:

  * Accuracy between masked and non-masked faces.
  * Accuracy among children(2~16 years old).
  * Accuracy of globalised multi-racial benchmarks.

We ensure that there's no overlap between these testsets and public available training datasets, as they are not collected from online celebrities.

### Testset Statistics

Test datasets mainly comes from [IFRT](https://github.com/deepinsight/insightface/tree/master/challenges/IFRT).

#### Mask set

Mask testset contains 6,964 identities, 6,964 masked images and 13,928 non-masked images. There are totally 13,928 positive pairs and 96,983,824 negative pairs.

#### Children set

Children testset contains 14,344 identities and 157,280 images. There are totally 1,773,428 positive pairs and 24,735,067,692 negative pairs.

#### Multi-racial set

The globalised multi-racial testset contains 242,143 identities and 1,624,305 images.

| Race-Set     | Identities  | Images        |  Positive Pairs   | Negative Pairs        |
| -------      | ----------  | -----------   |  -----------      | -----------           |
| African      | 43,874      | 298,010       |  870,091          | 88,808,791,999        |
| Caucasian    | 103,293     | 697,245       |  2,024,609        | 486,147,868,171       |
| Indian       | 35,086      | 237,080       |  688,259          | 56,206,001,061        |
| Asian        | 59,890      | 391,970       |  1,106,078        | 153,638,982,852       |
| **ALL**      | **242,143** | **1,624,305** |  **4,689,037**    | **2,638,360,419,683** |

<details>
  <summary>Click to check the sample images(here we manually blur it to protect privacy) </summary>
  <img src="https://github.com/nttstar/insightface-resources/blob/master/images/ifrtsample_blur.jpg" alt="ifrtsample" width="640">
</details>

## Evaluation Metric

For ``Mask`` set, TAR is measured on mask-to-nonmask 1:1 protocal, with FAR less than 0.0001(e-4).

For ``Children`` set, TAR is measured on all-to-all 1:1 protocal, with FAR less than 0.0001(e-4).

For other sets, TAR is measured on all-to-all 1:1 protocal, with FAR less than 0.000001(e-6).

Similar to FRVT, participants are finally ordered in terms of lowest mean rank across two datasets: **Rank@Mask** and **Rank@All**.


## Baselines


| Backbone   | Dataset    | Method     | Mask   | Children | African | Caucasian | South Asian | East Asian | All    | size(mb) | infer(ms) | link |
|------------|------------|------------|--------|----------|---------|-----------|-------------|------------|--------|----------|-----------|-----------|
| R100  | Casia  | ArcFace  | 26.623 | 30.359   | 39.666  | 53.933    | 47.807      | 21.572     | 42.735 | 248.904  | 7.073     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUJpk8zC61HVN7Kg?e=zE9JDd) |
| R100  | MS1MV2  | ArcFace  | 65.767 | 60.496   | 79.117  | 87.176    | 85.501      | 55.807     | 80.725 | 248.904  | 7.028     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUTlYEHJCHg3UYM-?e=ihxMpS) |
| R18  | MS1MV3  | ArcFace | 47.853 | 41.047   | 62.613  | 75.125    | 70.213      | 43.859     | 68.326 | 91.658   | 1.856     | [download](https://1drv.ms/u/s!AswpsDO2toNKrTxlT6w1Jo02yzSh?e=KDhFAA) |
| R34  | MS1MV3  | ArcFace | 58.723 | 55.834   | 71.644  | 83.291    | 80.084      | 53.712     | 77.365 | 130.245  | 3.054     | [download](https://1drv.ms/u/s!AswpsDO2toNKrT2O5pgyVtwnjeMq?e=16S8LI) |
| R50  | MS1MV3  | ArcFace | 63.850 | 60.457   | 75.488  | 86.115    | 84.305      | 57.352     | 80.533 | 166.305  | 4.262     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUUWd5i3a5OlFpM_?e=ExBDBN) |
| R100 | MS1MV3 | ArcFace | 69.091 | 66.864   | 81.083  | 89.040    | 88.082      | 62.193     | 84.312 | 248.590  | 7.031     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUPwyqWvNXUlNd3P?e=pTLw9A) |
| R18   | Glint360K   | ArcFace | 53.317 | 48.113   | 68.230  | 80.575    | 75.852      | 47.831     | 72.074 | 91.658   | 2.013     | [download](https://1drv.ms/u/s!AswpsDO2toNKrT5ey4lCqFzlpzDd?e=VWP28J) |
| R34   | Glint360K   | ArcFace | 65.106 | 65.454   | 79.907  | 88.620    | 86.815      | 60.604     | 83.015 | 130.245  | 3.044     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUBcgGkiuUS11Hsd?e=ISGDnP) |
| R50   | Glint360K   | ArcFace | 70.233 | 69.952   | 85.272  | 91.617    | 90.541      | 66.813     | 87.077 | 166.305  | 4.340     | [download](https://1drv.ms/u/s!AswpsDO2toNKrT8jbvHxjqCY0d08?e=igfdrd) |
| R100  | Glint360K  | ArcFace | 75.567 | 75.202   | 89.488  | 94.285    | 93.434      | 72.528     | 90.659 | 248.590  | 7.038     | [download](https://1drv.ms/u/s!AswpsDO2toNKrUFgLEIj-mnkb51b?e=vWqy2q) |
| -       | *Private*     | <div style="width: 50pt">insightface-000 of frvt  | 97.760 | 93.358   | 98.850  | 99.372    | 99.058      | 87.694     | 97.481 | -  | -    |   -  |


(MS1M-V2 means MS1M-ArcFace, MS1M-V3 means MS1M-RetinaFace).

Inference time was evaluated on Tesla V100 GPU, using onnxruntime-gpu==1.6.


## Rules

1. We have two sub-tracks, determined by the size of training dataset and inference time limitation.
  * Sub-Track A: Use MS1M-V3 as training set, download: [ref-link](https://github.com/deepinsight/insightface/tree/master/challenges/iccv19-lfr)
  * Sub-Track B: Use Glint360K as training set, download: [ref-link](https://github.com/deepinsight/insightface/tree/master/recognition/partial_fc)
2. Training set and testing set are both aligned to 112x112, re-alignment is prohibited.
3. Mask data-augmentation is allowed, such as [this](https://github.com/deepinsight/insightface/tree/master/recognition/tools). The applied mask augmentation tool should be reproducible. 
4. External dataset and pretrained models are both prohibited.
5. Participants submit onnx model, then get scores by our online evaluation. Test images are invisible.
6. Matching score is measured by cosine similarity.
7. Model size must <= 1GB.
8. For Track A: feature length must <= 512, and the inference time must <= 10ms on Tesla V100 GPU.
9. For Track B: feature length must <= 1024, and the inference time must <= 20ms on Tesla V100 GPU.
10. The input shape of submission model should equal to 3x112x112 (RGB order).
11. Online evaluation server uses onnxruntime-gpu==1.6, cuda==10.2, cudnn==8.0.5.
12. Any float-16 model weights is prohibited, as it will lead to incorrect model size estimiation.

## Tutorial 

1. ArcFace-PyTorch (with Partial-FC), [link](https://github.com/deepinsight/insightface/tree/master/recognition/arcface_torch)
2. OneFlow, [link](https://github.com/deepinsight/insightface/tree/master/recognition/oneflow_face)
3. MXNet, [link](https://github.com/deepinsight/insightface/tree/master/recognition/ArcFace)

## Submission Guide

1. Participants must package the onnx model for submission using ``zip xxx.zip model.onnx`` or ``tar czf xxx.tar.gz model.onnx``.
2. Each participant can submit three times a day at most.
3. Please sign-up with the real organization name. You can hide the organization name in our system if you like.
4. You can decide which submission to be displayed on the leaderboard by clicking 'Set Public' button.

Server link coming soon.

## Sponsors

**[DeepGlint](http://www.deepglint.com/)**

**[OneFlow-Inc](https://www.oneflow.org)**

[More]

## Bonus Share

|           | Sub-Track A | Sub-Track B |
| --------- | ------- | ------- |
| 1st place | 30%     | 30%     |
| 2nd place | 15%     | 15%     |
| 3rd place | 5%      | 5%      |

