---
layout: post
title:  "OS 디스크 스케쥴링 이해하기"
subtitle:   "OS 디스크 스케쥴링 이해하기"
categories: development
tags: os
comments: true
---

디스크 스케쥴링에 대해 작성한 글입니다

---

## 디스크 스케쥴링
- 대표적인 보조 기억장치 : 하드 디스크
- 실린더의 헤드를 움직여야 함
	- SSTF (Shortest-Seek-Time-First)
	- SCAN
		- 53 -> 98 -> 183 -> 37 ... 
		- No..
		
### SSTF Scheduling
- Seek Time이 최소화되는 것부터 처리
	- Seek Time : 디스크 헤더를 움직이는 시간 
- 문제점
		- Seek time이 많이 떨어진 프로세스는 계속 기다림.. 그러면서 외부에서 새로운 놈이 들어옴(그러나 Seek Time이 짧음) 그러면 기존 프로세스는... 안녕... 
	- 헤드가 디스크를 계속해서 앞뒤로 스캔
	- 스캔하는 방향에 따라 결과가 달라짐
	- 프로세스가 많으면 실린더에 대한 요청은 골고루 있다고 가정
	- Circular SCAN is necessary!
		- 최고 안쪽은 최고 바깥이랑 연결된 C-SCAN 
	- 스캔 알고리즘을 엘레베이터라고 부름(기존 그래프를 90도 rotate하면 엘레베이터처럼 보임) 

## Reference
- [양희재 교수님 운영체제 강의](http://kocw.net/home/search/kemView.do?kemId=978503)
- [introduction to Operating System](https://www.slideshare.net/LukaXavi/introduction-to-operating-system-10938506)




