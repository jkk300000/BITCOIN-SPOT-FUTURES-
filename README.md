# 비트코인 선물, 현물 차익거래 전략(트레이딩 뷰) 현물: OKX, 선물: BINANCE BTCUSDT PERPETUAL FUTURES.
### 비트코인 선물, 현물 차익거래 전략(트레이딩 뷰) 현물: OKX, 선물: BINANCE BTCUSDT PERPETUAL FUTURES.

구글링 중 발견한 차익거래 논문을 기반으로 작성한 비트코인 현물, 선물 차익거래입니다. 항상 현물과 선물 간의 가격 차이가 발생한다는 점을 이용하여 거래하는 방법입니다. 

해당 논문에서 제안한 방법은 두 가지입니다.

  1. 현물 가격이 선물 가격보다 낮은 경우
  2. 현물 가격이 선물 가격보다 높은 경우
  

여기서 구현한 방법은 1 방식입니다. 2 방식의 경우에 현물을 매도하는 개념을 제시하는데, 파생 상품이 아닌 경우에 매도(숏) 포지션을 취하는것은 불가능하다 판단했기 때문입니다. 


### 구현 방법: 트레이딩 뷰를 사용하여 현물과 선물 전략을 각각 구현했으며, 각 전략의 수익 및 거래목록을 비교하여 실제 수익이 발생했는지 판단했습니다.
### 거래 방법: 현물 가격이 선물 가격보다 낮은 경우 현물 매수 및 선물 숏 포지션 -> 현물 가격이 선물 가격 보다 높아진 경우 현물 매도 및 선물 숏 포지션 청산

## 1. 현물 전략 오버뷰
   비트코인 가격이 항상 우상향 하는 관계로 현물의 가격은 상승했으며, 현물은 청산 위험이 없습니다.
   
![차익거래 현물 오버뷰](https://github.com/user-attachments/assets/8ed7146c-0ab8-4df6-aba3-06b60f1a5323)
 

## 2. 현물 전략 파인스크립트 코드
  논문에서 제시한 거래 전략 및 수익 계산 공식을 활용하여 수수료 및 거래 비용을 임의로 계산 후 이익이 발생하는지 여부를 고려했습니다.

![차익거래 현물 파인스크립트 코드](https://github.com/user-attachments/assets/fbb0d62c-9897-4437-a0a0-55ae472138ff)

## 3. 현물 전략 거래 목록
  선물 거래와 동시에 거래가 진행되었는지 확인하기 위해 거래 횟수 및 시간 등의 비교했습니다.

![차익거래 현물 거래목록](https://github.com/user-attachments/assets/14268108-351a-4ffa-b95c-8788b3b85593)


## 4. 선물 전략 오버뷰
  선물 거래의 특성 및 숏 포지션을 특성 때문에 항상 강제 청산의 위험이 있습니다. 레버리지는 1배로 계산했지만 USDT 페어의 경우 가격이 2배이상 급등하면 청산의 위험이 있습니다. 이러한 이유로 숏 포지션에는 증거금을 여유있게 준비해야합니다.

![차익거래 선물 오버뷰](https://github.com/user-attachments/assets/15b732b1-b508-43af-968d-250c8da58005)


## 5. 선물 전략 파인스크립트 코드
  현물 거래와 동시에 거래가 진행되었는지 확인하기 위해 거래 횟수 및 시간 등의 비교했습니다

![차익거래 선물 파인스크립트 코드](https://github.com/user-attachments/assets/3750f40e-421a-4ba5-a838-419ce7c34bb2)

## 6. 선물 전략 거래 목록
  현물 거래와 동시에 거래가 진행되었는지 확인하기 위해 거래 횟수 및 시간 등의 비교했습니다.

![차익거래 선물 거래목록](https://github.com/user-attachments/assets/6630aa1d-ce7b-44a2-8c76-61c40c4e0efe)




