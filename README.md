  #-분류의 문제에서,컴파일에 사용할 loss 함수 선택 방법과 코드
  #-loss함수 선택방법이 있다 예를 들어 10개의 클래스를 분류할 수 있는 분류기를 훈련시키는 경우에는 손실함수로 sparse_categorical_crossentropy를
  #-사용할수 있습니다.
  #- 모델은 실제 라벨과 가장 가까운 값이 예측되도록 훈련되어집니다. 이떄 그 가까운 정도를 측정하기 위해 사용되는 것이 손실 함수(loss function)입니다.
  만약 이진 분류기를 훈련하려면binary crossentropy를 사용하면 됩니다(class가 두개인 분류,T/F,양/음)등 2개의 클래스를 분류할 수 있는 분류기를 의미합니다.
  categorical crossentropy는 분류해야할 클래스가 3개 이상인 경우 멀티클래스 분류에 사용됩니다. 라벨이 [0,0,1,0,0],[1,0,0,0,0],[0,0,0,1,0]과 같이 one-hot 형태로 제공될때 사용됩니다.
  sparse categorical crossentropy 역시 이 함수 또한 멀티클래스 분류에 사용되는 손실함수. 이름에 sparse 하나가 추가 되었다. 이 함수가 사용되는 경우는 바로 라벨이 0,1,2,3,4
  와 같이 정수의 형태로 제공될 때입니다
예시-model.compile(optimizer='Adam',loss='categorical_crossentropy',metrics=['accuracy'])
#- 러닝커브 함수 코드와 트레이닝 어큐러시,벨리데이션 어큐러시를 통한 오버피팅 설명
#-러닝커브를 쓰는 함수는 다음과 같다.
