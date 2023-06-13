#
## CPU Scheduling
#

### CPU Scheduling이란

> 프로세스가 생성되어 실행될 때 필요한 시스템의 여러 자원을 해당 프로세스에게 할당하는 작업

### CPU Scheduling 목적

> 공정한 스케줄링, 처리량의 극대화, 응답시간 최소하

> 균형있는 자원 사용, 실행의 무한 연기 배제, 반환시간 예측가능

### 기준 및 종류

1. CPU Scheduling의 기준
- CPU 이용률(Utilization): CPU를 이용한 수치의 백분율

- Throughput: 단위시간당 완료된 프로세스의 수

- Response Time: 작업 요청 후 응답이 오는 데 걸리는 시간

- Waiting Time: 대기 큐에서의 대기시간

2. CPU Scheduling의 종류

* 개념
    1. 선점(Preemptive)
        >P1이 CPU점유, P2가 CPU점유가능
    2. 비선점(Non-Preemptive)
        >P1이 CPU점유,
        P2는 대기

* 장점
    1. 선점(Preemptive)
        >빠른 응답, 시분할 시스템에 적합
    2. 비선점(Non-Preemptive)
        >응답시간 예상 가능, 공정한 처리

* 단점
    1. 선점(Preemptive)
        >오버헤드 발생 (Context Switching)
    2. 비선점(Non-Preemptive)
        >짧은 작업도 긴 대기 발생

### CPU Scheduling 알고리즘 종류

1. 선점(Preemptive) 알고리즘
    * Round Robin

    * SRT

    * MLQ(Multi Level Queue)

    * MLFBQ(Multi Level Feed Back Queue)

2. 비선점(Non-Preemptive) 알고리즘
    * FCFS
    
    * SJF

    * Priority

    * Deadline

    * HRN
    
