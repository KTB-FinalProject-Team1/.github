# DEVITA: 개발자 맞춤 성장 미션 제공 서비스

## 팀원 및 역할

| <img width="122" alt="image" src="https://github.com/user-attachments/assets/c397adf8-767d-496d-b4d2-78be435704a1"> | <img width="122" alt="image" src="https://github.com/user-attachments/assets/3d885f38-52ad-44f5-b9ac-1bfa30c4b0f5"> | <img width="122" alt="image" src="https://github.com/user-attachments/assets/5af0ddb4-3cd0-4c71-a2f8-f7a7ff7c693e"> | <img width="122" alt="image" src="https://github.com/user-attachments/assets/8e5d9eeb-5049-42da-b6af-7b257db6f311"> | <img width="122" alt="image" src="https://github.com/user-attachments/assets/e78047d7-22d7-47a7-a34f-0eeb3283f05b">  | <img width="122" alt="image" src="https://github.com/user-attachments/assets/5f92b7ab-f887-4def-8266-e5c5c797c6f8"> |
|------------------------------------------------------|--------------------------------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [Jinho.Hong(홍진호)](https://github.com/mynameisjinhohong)                                            | [Ayaan.Park(박찬영)](https://github.com/chanyoungit)                                           | [Jully.Han(한주리)](https://github.com/Hanjuri)                                           | [Milo.Kim(김민제)](https://github.com/alswp006)                                                                                                                                               | [Winter.Park(박현혜)](https://github.com/hyeonhye126)                                                                                                                                            |[Dorothy.Kim(김도윤)](https://github.com/Do-yoon)                                               | 
| 팀장<br>Cloud                      | Cloud                                              | Front-end                                                                               | Back-end                                                                                                                                           | AI                                                                                                                                              | AI                                       |
## 💁‍♂️ Detail Role <a name = "role"></a>
+ [Jinho.Hong(홍진호)](https://github.com/mynameisjinhohong)
  - 팀장
  - 클라우드
  - 아키텍처 설계
  - 젠킨스를 활용한 CI/CD 구축
  - 테스트 서버와 배포 서버 분리
  - 개발 편의를 위한 디스코드 봇 제작
  
<Br>

+ [Ayaan.Park(박찬영)](https://github.com/chanyoungit) 
  - 기획자 
  - Back-end & DevOps
  - 로그인, 마이페이지, 찜, 매칭, 알림, 공지사항, 리워드, 결제 취소 배치 작업 구현
  - 전체적인 AWS 환경 구축
  - Jenkins CI/CD 구축
  - Redis 클러스터 및 모니터링 구축
  - 로그 모니터링용 ELK 구축
  - Swagger, REST docs 문서화

<Br>

+ [Jully.Han(한주리)](https://github.com/Hanjuri)
  - PM
  - Front-end
  - 모든 Front-end 구현

<Br>

+ [Milo.Kim(김민제)](https://github.com/alswp006)
  - PM
  - Front-end
  - 모든 Front-end 구현

<Br>

+ [Winter.Park(박현혜)](https://github.com/hyeonhye126)
  - PM
  - Front-end
  - 모든 Front-end 구현

<Br>

+ [Dorothy.Kim(김도윤)](https://github.com/Do-yoon) 
  - PM
  - Front-end
  - 모든 Front-end 구현

<Br>

 <br>

## Team Introduce
### 팀 이름
일취월장
### 팀 문화
- 매주 3번 회의
  - 이전 회의 이후로 진행된 사항 공유
  - 현재 팀 전체적으로 논의할 사항 논의
  - 다음 회의까지 각자 작업할 사항 결정
- 프로젝트 관리
  - 팀 디스코드 채널을 개설하여 정보 공유 및 소통
  - Jira를 활용하여 일정 및 스프린트 관리
- ETC
  - 지각비를 도입하여, 팀원들이 약속 시간에 늦지 않도록 관리

## Devita (develop + vitamin)
### 프로젝트 한줄 소개
개발자 맞춤 성장 미션 제공 서비스
### 프로젝트 목표
- 매일 비타민을 섭취하듯 좋은 개발 습관 형성
- 사용자 맞춤형 미션 추천
- To-do list를 통한
- 효율적이고 체계적인 일정 관리
- SNS를 통한 자신의 학습 성과 공유
=> 개발자의 업무 효율 향상, 지속적인 성장 지원
### 타 서비스 대비 차별점
<img width="1542" alt="image" src="https://github.com/user-attachments/assets/1108fb5b-073b-4976-9a7e-ce25fd845c45"><br>
### 📈 아키텍처  <a name = "structure"></a>

![devita drawio](https://github.com/user-attachments/assets/3ab94970-7ae4-47c3-9495-fb5c947754bf)

- 개발 서버와 배포 서버를 분리
- 초창기 웹으로 개발을 진행하다 여러 논의후 앱으로 전환
- 젠킨스를 활용한 CI/CD 구축
  - Git Flow 전략을 활용
    - Develop 브랜치에 머지시 테스트 서버에 작동
    - Main 브랜치에 머지시 배포 서버에 작동
- Route53을 활용한 도메인 설정
  - 도메인을 Nginx에 연결하여 모든 트래픽 Nginx가 관리
  - Nginx를 활용한 로드밸런싱 구축
  - 블루/그린 배포 전략을 활용한 무중단 배포 구축
- S3 버킷을 활용한 파일 관리
- VPC로 논리적으로 격리된 공간을 만들고 외부 접근 제한
  - VPC가 외부와 통신이 가능하도록 Internet Gateway 를 구성하고 라우팅 테이블에서 Public Subnet(10.0.1.0/24, 10.0.2.0/24)과 연결
  - NAT Gateway를 구성하여 나머지 Private Subnet 리소스가 인터넷으로 트래픽이 통할 수 있도록 연결

### 작업내용

- 클라우드
  - 개발 편의를 위한 디스코드 봇 개발
    - 무료 호스팅 서버에 디스코드 봇 프로그램 호스팅
    - 젠킨스 서버 실행,종료
    - 각 CI,CD 파이프라인 실행 가능
  - CI/CD 파이프라인 구축
    - Jenkins 활용
    - Git Flow 전략을 활용하여 테스트서버,배포 서버 분리
  - 아키텍처 설계 및 구축

- 프론트
- 백엔드
- AI

### 결과


