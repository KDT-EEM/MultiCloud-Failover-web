<div align="center">
  
# AWS와 NHN Cloud를 이용한 멀티클라우드 재해복구시스템
</div>

> ‼️이 프로젝트는 [NHN 클라우드를 활용한 IaaS 티켓팅 웹사이트](https://github.com/KDT-EEM/TickettingWeb/edit/main/README.md#5-클라우드-구축-과정)에서 클라우드 구조를 멀티 클라우드로 재구축한 프로젝트입니다.‼️

<div align="center">
  
## KT클라우드와 NHN Cloud로 완성하는 클라우드 엔지니어 양성 3차 프로젝트 
## 🦁KDT 1팀🐯


<h1>📚STACKS</h1>

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)

![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)
![Grafana](https://img.shields.io/badge/grafana-%23F46800.svg?style=for-the-badge&logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=Prometheus&logoColor=white)

![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)

![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

</div>
# 👨‍💻팀원 구성

| 김영권     | 이태민    | 강석진   | 양현수    | 주상민   |
|--------------|--------------|--------------|--------------|--------------|
| <img src="https://avatars.githubusercontent.com/u/169283479?v=4" width="150" height="150"/> | <img src="https://avatars.githubusercontent.com/u/105273042?v=4" width="150" height="150"/> | <img src="https://avatars.githubusercontent.com/u/105378841?v=4" width="150" height="150"/> | <img src="https://avatars.githubusercontent.com/u/110795226?v=4" width="150" height="150"/> | <img src="https://avatars.githubusercontent.com/u/158993111?v=4" width="150" height="150"/> |
| [@visionn7111](https://github.com/visionn7111) | [@taebong113](https://github.com/taebong113) | [@goodniceboy](https://github.com/goodniceboy) | [@Dkdneidi](https://github.com/Dkdneidi) | [@sangmin310](https://github.com/sangmin310) |

# 🤸역할분담
**김영권(보안)** : AWS 아키텍처 구성 및 구축, AWS WAF 구축, NHN Cloud ACL 관리, 로그인 페이지 구현, DVWA를 이용한 보안 테스트

**이태민(클라우드)** : AWS 인프라 설계 및 구축, 자동화, 문제 해결, 모니터링을 통한 고가용성 및 확장성 구현

**강석진(백엔드)** : NHN 아키텍처 설계 및 구축, Docker & Kubernetes 활용한 서버 구축 및 배포, NHN RDS, VPN 구축 및 연동, AWS,NHN RDS 동기화, failover 시스템 구현

**양현수(서버)** : NHN 아키텍처 구축, Docker & Kubernetes 활용한 Web 배포, NKS 오토스케일링 구축, CICD(Jenkins)파이프라인 구축, 모니터링(prometheus, Grafana)

**주상민(서버)** : 클라우드 아키텍처 구성 및 구축, 웹 페이지 구현, 데이터 베이스 구축

## 1. 프로젝트 소개
AWS 클라우드와 NHN 클라우드를 활용한 멀티 클라우드 티켓팅 웹 서비스

## 2. 개발배경 및 목적
티켓팅 웹 서비스의 경우 대형 이벤트나 인기 있는 콘서트의 티켓 판매 시 한번에 많은 사용자가 접속하게 되므로 서비스의 안정성과 확장성이 매우 중요합니다. 기존 단일 클라우드 환경에서 이러한 상황이 발생하게 되면 서비스 중단이나 성능 저하가 발생할 수 있습니다.
이러한 문제를 해결하기 위한 방법 중 하나는 멀티 클라우드를 활용하는 것입니다. 멀티 클라우드를 활용하게 되면 하나의 클라우드에서 장애가 발생하더라도 다른 클라우드로 서비스를 자동으로 전환하여 지속적인 서비스 제공이 가능해집니다. 따라서 저희는 티켓팅 웹 서비스의 안정성과 신뢰성을 높이기 위해 AWS와 NHN 클라우드를 함께 활용하여 멀티 클라우드 전략을 선택하게 되었습니다.

먼저 프로젝트의 첫 번째 목적으로는 NHN 클라우드에서 장애가 발생했을 경우, AWS 클라우드 서비스로 자동 전환되어 사용자가 중단 없이 티켓팅 서비스를 이용할 수 있도록 하는 재해 복구 시스템을 구축하는 것입니다. 또한 두 번째 목적으로 AWS 클라우드의 웹 서버와 RDS 인프라를 통해 애플리케이션과 데이터베이스 간 안정적인 연결을 유지하고, Route 53을 이용한 도메인 설정을 하고 헬스 체크를 통해 서비스 가용성을 모니터링하는 것입니다. 마지막으로 Docker와 K8s를 활용하여 웹 서버 및 WAS를 구축함으로써 높은 유연성과 확장성을 제공하고 이를 통해 급증하는 트래픽을 효과적으로 처리하고, CI/CD 파이프라인을 구축하여 애플리케이션의 즉각적인 배포와 지속적인 통합을 제공하는 것입니다. 
따라서 저희는 위의 목적을 바탕으로 AWS와 NHN 클라우드를 활용한 안정적 티켓팅 웹 서비스의 구축을 진행하였습니다.

## 3. 시스템 구성 및 아키텍처
![KakaoTalk_Photo_2024-09-16-01-46-31](https://github.com/user-attachments/assets/3e5461a7-692d-43bb-a21c-a081ccfc5d79)


## 4. 프로젝트 주요 기능 및 구조도
<details>
<summary>주요 기능 설명</summary>
<div markdown="1">       

### AWS - VPN
- 고객 게이트웨이 IP 주소는 `133.186.151.102`(NHN측 VPN 서버)  
  이를 통해 VPN 연결이 이루어짐.
- 해당 VPN은 두 개의 터널로 구성되어 있으며 각 터널은 up 상태를 유지.

### AWS – Application Load Balancer
- 로드밸런서는 웹 서버와 보안 테스트 서버를 관리하는 두 개의 대상 그룹을 설정.
- 평상시에는 웹 서버 대상 그룹에 있는 `web1`과 `web2`로 트래픽 전달.
- 특정 보안 테스트를 위해 도메인 뒤에 `/DVWA` 경로를 사용하면 보안 테스트 서버 DVWA로 트래픽 전달.
- 이렇게 설정하여 평상시에는 웹 서버로 로드밸런싱하고, 보안 테스트 필요시 보안 테스트 서버에만 로드밸런싱 가능.

### AWS – Load Balancer 매핑 정보
- 다중 가용 영역 구성 → 해당 로드 밸런서는 다중 가용 영역에 걸쳐 설정.
- a, c 가용 영역에 각각 서브넷이 매핑되어 있어, 트래픽의 가용성과 내결함성을 보장.
- 각 서브넷은 로드 밸런서가 트래픽을 분산시키는 데 사용.

### AWS – Load Balancer Target Group 설정
- 타겟 그룹 이름: `project-target-group`
- 로드 밸런서: `project-elb`
- 트래픽 포트: `HTTP(80)`
- 대상 유형: `EC2 인스턴스`

### AWS – Load Balancer 대상 인스턴스 상태
- 총 인스턴스 수: 2개
- `webserver1`: ap-northeast-2a 가용 영역
- `webserver2`: ap-northeast-2c 가용 영역
- 상태: 모든 인스턴스 정상(Healthy)

### AWS – Load Balancer 주요 특징
- **고가용성**: 두 개 이상의 가용 영역에 배포된 인스턴스들에 트래픽을 분산.
- **상태 확인**: 로드 밸런서는 정상 인스턴스로만 트래픽을 분산.

### AWS – Auto Scaling
- Auto Scaling은 트래픽에 따라 서버 인스턴스 수를 자동으로 조절.  
  트래픽이 증가하면 인스턴스를 추가로 생성하고, 감소하면 불필요한 인스턴스 종료 → 서비스의 안정성을 유지하고 비용을 절감.
- 원하는 용량이 2개로 설정되어 있으므로, 현재 Healthy 상태의 두 인스턴스가 정상적으로 작동하고 있는 것은 예상된 상황.
- 최대 용량이 3개이므로, 추가적인 인스턴스를 생성할 수 있는 상황이지만 현재 Healthy 상태의 인스턴스는 2개로 유지 → 이는 오토스케일링 그룹이 정상적으로 설정된 대로 동작하고 있다는 것을 의미.
- Unhealthy 상태의 인스턴스가 Terminating 중이므로, 이 인스턴스가 종료되면 원하는 용량인 2개를 유지.

### AWS – RDS
- 엔드포인트로 인스턴스에서 접속.
- 프리티어 – 다중 AZ 배포 X.
- 외부에서 접근 X.

### AWS – EC2 Web Server Instance
- `webserver1`, `webserver2` 두 개의 인스턴스 존재.
- `webserver1`은 Ubuntu, `webserver2`는 Apache.
- 로드밸런싱을 통해 웹 트래픽 부하 분산.

### AWS – EC2 Web 보안 테스트 서버
- DVWA는 보안 연구자와 개발자들이 웹 애플리케이션의 보안 취약점을 학습하고 실습할 수 있도록 설계된 오픈 소스 애플리케이션.
- 웹 방화벽 기능이 정상적으로 작동하는지 확인 가능.
- SQL Injection, XSS 등 테스트 가능.

### AWS – WAF 구조
- AWS WAF를 로드밸런서와 연동 후 ACL을 사용해 보안 규칙을 추가하여 특정 트래픽 제어가 가능.
- AWS가 제공하는 규칙 또는 직접 설정한 규칙을 통해 자유롭게 웹 보안 기능을 추가/제거 가능.
- CloudWatch와 통합되어 있어 실시간으로 로그를 분석하고 경고를 설정할 수 있음. 이를 통해 보안 이벤트를 빠르게 인지하고 대응할 수 있음.

### AWS – WAF 규칙(AWS에서 제공하는 규칙)
- `AWSManagedRulesAdminProtectionRuleSet`: 관리자 페이지와 관련된 취약점을 보호하고 악성 접근을 차단.
- `AWSManagedRulesCommonRuleSet`: 일반적인 웹 공격을 방어. (예를 들어, XSS, CSRF 방어)
- `AWSManagedRulesLinuxRuleSet`: Linux 기반 서버에서 자주 발생하는 공격 패턴을 차단.
- `AWSManagedRulesPHPRuleSet`: PHP 애플리케이션에 특화된 공격 (예를 들어 코드 인젝션을 방어).
- `AWSManagedRulesSQLiRuleSet`: SQL 인젝션 공격을 방어.

### AWS – WAF 규칙(직접 만든 규칙)
- ACL을 이용하여 한국을 제외한 해외 IP를 차단.
- 특정 국가의 IP를 차단함으로써 서버에 대한 위험을 줄일 수 있음.
- 서버에 도달하는 트래픽을 줄여 서버 자원을 효율적으로 사용 가능.

### AWS - DVWA에서의 WAF 보안 테스트 - XSS
- 웹 페이지의 쿠키 값을 출력하는 XSS 스크립트 공격:  
  `<script>alert(document.cookie);</script>`
- 방화벽이 없을 때는 쿠키값이 그대로 출력됨.
- 방화벽이 있을 때는 클라이언트 요청을 차단하고 403 에러 발생.

### AWS - DVWA에서의 WAF 보안 테스트 - SQL Injection
- SQL 인젝션 공격 (`' OR '1'='1`)을 통해 모든 userID의 정보를 열람.  
  시연 영상은 별도 파일 첨부 예정.

### NHN - NKS 구축
- Kubeconfig 파일 → NKS에 있는 정보를 kubectl에 접근 가능하게 함.
- NCR 저장을 위한 Image 저장:  
  docker tag my-php-app:latest ${998a85e2-kr1-registry.container.nhncloud.com/nhn-ncr }/my-php-app:1.0  
  docker push 998a85e2-kr1-registry.container.nhncloud.com/nhn-ncr/my-php-app:1.0

### NHN – 게이트웨이
- NAT 게이트웨이와 인터넷 게이트웨이 설정.

### NHN - CI/CD 구축
#### CI
- Webhook 활용.
- Pipeline 코드 작성.

#### CD
- Deployment.yaml 파일과 Hpa.yaml 파일 작성.
- 부하 → CPU 확인 → Auto Scaling → CPU 확인.  
  command: ["ab", "-n", "100000", "-c", "100", "http://133.186.209.216/"]  
  Apache Benchmark 도구를 사용하여 http://133.186.209.216/ URL에 대해 부하 테스트를 수행.
  - `-n 100000`: 총 100,000개의 요청.
  - `-c 100`: 100개의 동시 연결 사용.

### NHN - RDS for mySQL
- RDS는 데이터베이스 패치 관리, 백업, 복구 등을 자동으로 수행.
- 자동 스케일링을 통해 마스터 인스턴스에 장애가 있을 시 예비 마스터가 마스터 역할 수행.

### NHN - RDS for mySQL 백업
- RDS 백업 설정을 통해 주기적으로 백업 실행 가능.
- 로그를 통해 백업이 정상적으로 실행되었는지 확인 가능.

### NHN - RDS for mySQL 모니터링
- NHN RDS에서 지원하는 모니터링 기능을 통해 RDS의 트래픽 변화량 확인 가능.

### NHN - Block Storage
- NKS로 인스턴스를 생성하여 하나의 인스턴스 당 한 개의 블록 스토리지가 자동으로 생성.
- 블록 스토리지는 여러 개의 인스턴스에서 동시에 연결하여 사용할 수 있으며, 연결이 해제된 블록 스토리지는 다른 인스턴스에 연결하여 사용 가능.
- 스냅샷을 이용해 특정 시점의 블록 스토리지 상태를 저장 및 복구 가능.


</div>
</details>

## 5.결과 영상

[3차 프로젝트 결과](https://www.youtube.com/watch?v=RK5H21K5i-w)
[![3차프로젝트 결과](https://img.youtube.com/vi/RK5H21K5i-w/0.jpg)](https://www.youtube.com/watch?v=RK5H21K5i-w)






