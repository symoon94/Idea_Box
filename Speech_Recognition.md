Speech Recognition
==================================

## < 선행 단계 >
#### - Convolutional Neural Network(CNN)와 Recurrent Neural Network(RNN)의 정확도를 직접 테스트 해보았습니다.

#### 1. CNN에서 MNIST로 학습시켜 정확도 약 98.2%를 얻었습니다.
[CNN 학습 정확도](https://github.com/symoon94/MachineLearning_Basic/blob/master/Convolutional_Neural_Network.ipynb)

#### 2. 자체 형성한 문자 데이터를 CNN model에 적용하여 보았습니다.
[코드1_matplotlib을 이용한 이미지 load](https://github.com/symoon94/MachineLearning_Basic/blob/master/CNN_test_plt_ver.ipynb)
<br />

[코드2_OpenCV를 이용한 이미지 load](https://github.com/symoon94/MachineLearning_Basic/blob/master/CNN_test_cv2.ipynb)
<br />

![OpenCV이용](https://github.com/symoon94/MachineLearning_Basic/blob/master/CNN_Result_with_my_own_data.png)
###### [그림 1]CNN 테스트 예시 - 7, 9, 2, 5 차례로 테스트하기 위해 쓴 손글씨, 그림판 손글씨, 필기노트에서 찍은 이미지, 음료수 캔 숫자 이미지)

#### 3. RNN에서 MNIST로 학습시켜 정확도 약 98.6%를 얻었습니다.
[RNN 학습 정확도](https://github.com/symoon94/MachineLearning_Basic/blob/master/Recurrent_Neural_Network.ipynb)

<br />
<br />

## < 기본 아이디어 >
![기본 모식도](https://github.com/symoon94/Image/blob/master/speech_recognition.png)
###### [그림 2]기본 아이디어 모식도

<br />
<br />

## < 아이디어 설명 >
#### 1. 기존에는 Hidden Markov Model(HMM), RNN 모델 등이 음성인식에 사용 되었습니다. 본 프로젝트는 CNN-RNN 모델을 이용합니다. 음성의 시작과 끝을 파악하여 CNN의 Image 분석 방법을 이용합니다. 주요 아이디어는 초성, 중성, 종성의 특징을 CNN으로 한 음절씩 찾아내고 음절과 음절을 RNN으로 단어로 인식한다는 것입니다.
![음성인식과 CNN-RNN](https://github.com/symoon94/Image/blob/master/CRNN.png)
###### [그림 3]음성인식과 CNN-RNN

#### 2. 각 음절의 분리 방법은 모음으로써 전후 음절을 분리합니다.

#### 3. 학습방법 
##### - CNN: 한 음절 씩 학습합니다.  (예) 가, 나, 다, 라 등
##### - RNN: 단어로 학습합니다.  (예) 고양이, 사람 등

<br />
<br />


###### _('기본 모식도', '음성인식과 CNN-RNN' 이미지 참고: Sharleen Lane의 '음성인식이론' ppt)_
