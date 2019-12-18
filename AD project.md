# AD project

- 요구사항 수집, 분석
- 소프트웨어 구조 설계
- 구현 상세설계
- 코딩
- 단위 테스트
- 시스템 통합
- 통합 테스트

**요구사항 분석**

1. bet를 누르면 게임이 실행되어야한다
2. bet 조합이 난수 발생적이어야한다
3. bet 누른다음 stake 는 비워진다
4. 각 슬롯은 0~9의 숫자를 가진다
5. 숫자가 특정 조합일때 stake에 일정 배수를 곱한만큼 money에 더한다
6. Reward 조합
    1. 슬롯의 숫자 2개가 일치할 경우 money = money + stake x2
    2. 슬롯의 숫자 3개가 일치할 경우 money = money + stake x3
    3. 슬롯의 숫자가 777일 경우 money = money + stake x5
    4. 슬롯의 숫자가 모두 다른 경우 money = money - stake
7. money는 시작할 때 1000이다
8. stake는 1이상의 값이어야 한다
9. stake ≤ money 일 때만 실행된다. 
10. bet은 5회까지 가능하다
11. Left trials 가 0이되거나 money 가 0이되면은 게임 오버다
12. Left trials 에서는 게임 기회가 몇 회 남았는지 보여 준다
13. New game 버튼을 통해 새 게임을 시작할 수 있다

**인터페이스 요구사항**

1. 윈도우 타이틀 바 : ADProject Slotmachine
2. 타이틀레이블 : Slot Game!
3. 그리드 레이아웃 : 슬롯 3칸
4. money 레이블
5. Left trials
6. status

**사용자 인터페이스** 

1. stake 레이블
2. Bet 버튼
3. New Game 버튼

**비기능적 요구사항**

이 소프트웨어의 구현에는 Python과 PyQt5를 이용한다.

## 소프트웨어 구조 설계

### slotgame.py

**SlotGame**

사용자 인터페이스의 대부분 위젯을 포함하는  UI component

**mainWindow**

위 위젯들과 상태 표시줄(status bar)을 포함하는 메인 윈도우

[slotgame](https://www.notion.so/aeee3399a1c944d58683219725144607)

### slot.py

게임의 핵심 로직 구현이 아닌걸