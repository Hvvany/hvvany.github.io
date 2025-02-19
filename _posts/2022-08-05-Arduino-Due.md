---
layout: single
title: "[22.08.05] Arduino-Due "
---
# Arduino Due board 특징 정리

1. **아두이노 듀에보드 사진**

![듀에보드 사진](https://github.com/hvvany/hvvany.github.io/blob/master/_posts/2022-08-05-Arduino-Due.assets/%EB%93%80%EC%97%90%EB%B3%B4%EB%93%9C%20%EC%82%AC%EC%A7%84.png?raw=true)

2. **아두이노 듀에보드 특징**

   > 일단 클럭주파수가 84MHz이고 **내부적으로 3.3V를 사용** (보통 다른 아두이노 보드는 5V로 동작한다)하므로 라즈베리파이의 GPIO와 핀끼리 바로 연결할 수 있다는 장점도 있다. 또한 AVR 기반의 아두이노 보드와 달리 DAC도 내장하고 있으며 프로그램에서 **64bit double형도 다룰 수 있다**고 한다. 성능이 높은 만큼 가격은 다소 비싼 편이다. 동작 클럭이 84MHz이므로 단순히 비교하면 **우노보드보다 5배 이상 성능**이 높으며 디지털 핀수가 굉장히 많아졌고 PWM 개수도 우노보드보다 더 많으며 해상도도 12bit까지 지정할 수 있다. 그리고 모든 디지털핀에 인터럽트를 설정해 줄 수 있다는 것도 큰 장점이다. 우노의 경우 두 개의 외부 인터럽트만 사용할 수 있다.

3. **usb 연결 단자**

   > 두에보드에는 USB연결단자가 두 개가 있는데 기본적으로 DC잭에 가까운 마이크로USB포트와 PC를 연결하면 전원이 공급되며 프로그램을 업로드할 수 있는 환경이 된다. 이 경우 별도로 DC잭으로 전원을 공급할 필요는 없으나 필요할 경우 7V~12V를 연결해야 한다.

   > 한 가지 주의할 점은 기존 아두이노보드들은 5V로 구동되는데 비해서 이것은 **구동 전압이 3.3V**라는 것이다. **<u>입출력 핀에 5V신호를 인가하면 보드에 손상이 올 수도 있다</u>**고 하니 주의해야 한다.

4. **듀에보드 핀 맵**

![img](https://lh5.googleusercontent.com/IJRJ9HYOwsxdq-ns34LG6cFf_We87tYlv5foVD629sx5-y9Dp7jx-cWtKh5j8f04u2looeBblH0qF2KIGnEdxApl9HnSVsB6Tn2Ff4Oebb8QhEVZC9EGESdRNx3k0O6eyh6lTfM)

> 입출력 핀을 통한 실험으로 실질적으로 우노보드보다 1.6 배 정도 성능이 우수한 것으로 나온다.



