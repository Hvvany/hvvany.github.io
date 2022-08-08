---
layout: single
title: "[22.08.07] Due problem solve"
---
# 아두이노 URM07센서와 듀에 보드 연결



지난 금요일에 졸업 프로젝트로 모여서 듀에 보드에 센서를 작동시켜 보려고 하였으나 제대로 작동되지 않았다.

각자 보드 하나씩 잡고 작동 되도록 만들어오기로 했는데 듀에 보드에 URM07를 연결하고 작동을 시키는 임무를 맡았다.

먼저 듀에 보드의 특징을 이해하기 위해 이전 블로그 내용으로 보드의 특징과 핀 맵을 공부했다.

URM07 공식 사이트에서 제공하는 코드에 잘 보니 TX1과 RX1에 연결을 하였는데 보드가 달랐다. 듀에 보드에 나는 TX0, RX0에 연결을 하였다가 안되었다. 그래서 TX1과 RX1에 새로 연결하니 잘 작동하였다.

![URM07](https://raw.githubusercontent.com/DFRobot/DFRobotMediaWikiImage/master/Image/URM07_Single_Control.png)



RX0과 TX0은 특별한 기능을 사용할때 사용하는 것 같다.

이제 납땜을 제대로 하여 성능 테스트를 진행해 봐야겠다.
