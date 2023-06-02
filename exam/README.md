마지막 수업, 총 정리

# 9. Unsupervised Learning (Clustering, K-means)
Supervised : Labeled data
## Unsupervised 
labeled data를 어떻게 활용할 지
Clustering 예시 - 뉴스 기사, 지역성, wafer..

비슷한 그룹 어떻게 찾을 지
Distance matric 여러개
Clustering(3)-Centroid, Density, Distribution

## How many Cluster?
depends on data, (loss, cluster)

## K-means Algorithm
- 말로 설명-> Find the nearest centroid!
Loss function : L = S(S(a(차이^2)))
## Pros & Cons
쉽고, scalability(병렬화) 좋고, convergence 봊아
K 찾기 어렵, output 영향 주는 요소 많음, 지


# 10. Regularization
## 목적 : Generalization 잘 하는 방법 (NO! Overfitting)
## Expected MSE = Vaariance(내리기) + Bias (높이기)
= 산발적인 것 보단, 몰려도 치우쳐있는 것이 낫다.

w3, w4 최소로 줄일 것 (계수를 크게 잡음)

## Ridge Regression (L2-Regression)
MSE 풀다가 항 6개 A~F-> Loss escape 생김새 O -> 항상 0 보다 작은 값 = "타원"
MSE : 중앙
MSE with constraint : 타원 끝점 (constraint 원과 겹치는)

closed form 이 있지만 의미가 XX 너무 큼

## Lasso Regression (L1-Regression)
절댓값 라그랑쥬-듀얼

Circle 대신 square.
t가 충분히 작다면, parameter = 0 => 모델의 크기를 줄일 수 있다. (자주 사용)

cf. Weight Decay : 쭉쭉 눌러주는 느낌으로 (모델 사이즈 줄임)

# 11. Deep Learning(1)

## Deep Learning

## Perceptron
Sum(Input*Weight) + bias = Output

### Activation Function
add non-linear function (=activation function)

## Multiple layer Perceptron
여러개를 쌓자, hidden layer 여러개 -> 더 복잡한 pattern 구분 가능
### how many layers?
layer : fitting

## Backpropagation (중요, 좋음)
### Optimal Solution을 무조건 찾는다. 
### 제대로 된 용어 쓰세요.

Error 계산해서 뒤로 감.
output layer에서 -> hidden layer에서 (재사용되는 w, error가 뒤에서부터 흘러오는 느낌으로.)


# 12. Deep Learning(2)

## Deep Neural Network
## cost function (매우 많이 사용!)
### -> ANN model -()> Logit -> SoftMax -(Crossentrophy)> Label (0과 1로만)

## Training
### Algorithm (approximate하자~)
GD -> 어디에서 시작하는 지에 따라 global minima 찾기가 어렵.

### GD----mini-batch-----SGD
(origin) (2~3근사) (하나만,nosie up)

extract a mini-batch size m (m만큼의 사이즈가 줄어듬. 행렬곱 생각)

## Hiper parameter
W, E, m, n
W : Initial parameter (random is recommended)
E : Epoch (보통은 Training loss curve)
m : Batch size -> batch : cost (starts from 32)
n : learning rate -> scaling , noise scale 
------
mini-batch (3차원 모형들, 작을수록 iteration 증가)
learning rate 꼭 수정해보시고..; (0.1 for mini-batch, 0.0001 for Adam)

## Inference


# 13. Deep Learning(3)
## CNN
filter가 scanning 하면서 부분부분을 확인
압축된 정보를 얻어냄
끝에서 Fully connected 정보 get
### Padding and Striding -> 실제 작동 방식 -> Output 사이즈, 계산 방법.
Conv-Pooling-(...)Conv-Pooling->output

Resnet : 인기가 아주 많음. 거의 딥러닝의 정석
CV에서 큰 진보
## RNN
Language modeling -> 여기까지(시계열)~이후의 값은?(예측)
문제 : 한두개 빼고는 거의 허수임. 
### 해결법 : 재사용하자 ! Recurrent Neural Network
hidden이 흘러가고, 재사용한다. -> 각 step마다 output과 label을 계산한다. -> 이전의 output을 다음단계의 input으로 사용하자.

문제 : 잘 까먹음 (이전의 것)
### 해결 : 복습하자! Long-Short Term Memory (LSTM)
### 구조 기억하세요.!
image.png
sigma : 기억할 지 안 할 지.
-> 내 것 계산하고
-> 합치고
-> 결과 
image.png

## Advanced Training Strategies
각 input이 줄고 있으면, mini-batch 올 때마다 normalization 해준다. (읽어보세요)




## Ensenble

## Bagging
각 각 학 습 (같은 모델들 여러개로)
## Boosting
누 적 학 습
## Stacking
Bagging & Meta Learner(추가모델)
(다른 모델들 여러개) & Logistic Regression (등)




# 마지막 말
깊게 알길. 면접때 티가 남.   bn bn ㅠㅠ6논문과 학위
프백데 343


11. Back propagation 용어, 식
12. Softmax
13.Padding
Long-Short Term Memory (LSTM)