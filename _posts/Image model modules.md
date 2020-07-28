Image model 향상을 위한 기법들

# Attention

# Squeeze and Excitation(SE)
 - Image Model에서 채널간의 Features 들의 특징을 참조하게 하여 모델을 향상시키는 기법
  ![SA](https://i.imgur.com/29l7bua.png)
- Squeeze
  - Global average pooling을 사용(shape: [N,C,1,1])하여 Channel-wise한 값들을 생성
  - output을 Local descrptors로써 사용
  ![squeeze](/assets/squeeze.PNG)
  *i, j:pixels,    H,W: height, width, ${Z_c}$ = output*
- Excitation
  - fully captrue channel-wise dependecies를 목표로 한다
  - 채널간에 nonlinear interaction과, non-mutually-exclusive relationship을 학습한다.
      ![excitations](/assets/excitations.PNG)
  $$\delta=ReLU$$
  - two fully-connected layers(FC)로 bottelneck을 만들어 dimension reduction을 r의 ratio로 수행
  - extension output과 channel-wise multiply
   $$\tilde X = [\tilde x_1, x_2, ..., x_C]$$ $$ \tilde x_c=F_{scale}(u_c, s_c)= s_cu_c$$
  ![SE-modules](/assets/SE-modules.PNG)
