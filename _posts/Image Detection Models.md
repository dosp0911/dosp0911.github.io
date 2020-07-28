# R-CNN
- #### 논문 요약
 - ROI을 Selective Search Algorithm 사용
 - Region Proposals을 pre-trained 된 CNN 모델을 사용하여 feature map 추출
 - 피처맵을 Linear SVM을 사용하여 Classification

# Fast R-CNN
- #### 논문 요약
 - Selective Search Algorithm 사용
 - Feature map을 추출 후 ROI를 찾아서 R-CNN에 비해 연산량을 줄임
 - Classification과 location regression이 FC에 의해 구성

 ![Fast-RCNN](/assets/Fast-RCNN.PNG)

# Faster R_CNN
- #### 논문 요약
 - ROI를 CNN을 사용하여 속도와 정확성을 높(RPN:A Region Proposal Network)
 - End To End 트레이닝 가능

# Mask R_CNN
- #### 논문 요약
 - Faster-RCNN을 확장한것으로 Segmentation branch를 ROI에 대해 parallel하게 추가
 - Faster-RCNN은 pixel-to-pixel alignment에 맞춰 디자인 된 것이 아니므로 RoiPool이라는 alignment를 fix하는 operation이 적용
 - Resent50/ResentXt/FPN(Feature Pyramid Network) backbone
 - Classification, location regression, Mask segementation 3개의 output 생성
