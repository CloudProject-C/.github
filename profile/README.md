# 🍽️ CampEat — 대학생을 위한 캠퍼스 기반 맛집 추천 서비스
<img width="1919" height="1079" alt="KakaoTalk_Photo_2025-12-18-00-55-21" src="https://github.com/user-attachments/assets/0ac646e5-81bb-4a35-9431-6e0b75ee0375" />

CampEat은 **대학생 전용 맛집 추천 플랫폼**으로,  
학교 이메일 인증을 기반으로 **신뢰도 높은 리뷰 생태계**를 구축하고  
사용자 취향 기반 **개인화 추천 알고리즘**을 통해  
"오늘 뭐 먹지?" 고민을 빠르게 해결합니다.

---

## 🚀 Features
<img width="1919" height="1079" alt="KakaoTalk_Photo_2025-12-18-00-55-29" src="https://github.com/user-attachments/assets/1f19dd3c-6dd9-43a7-8729-5fb73fbc473a" />

### 🔐 1. 학교 인증 기반 사용자 신뢰도 확보
- 대학 이메일(@ac.kr) 인증을 통한 가입
- 인증된 학생만 리뷰 작성 가능
- GPS 기반 500m 제약 → 허위 리뷰 방지

### 🎯 2. 개인화 추천 알고리즘
- 온보딩에서 선호 음식 카테고리 선택
- 음식점 벡터와 사용자 벡터의 코사인 유사도 계산
- 퍼센트 기반 선호도 표시 (예: 86%)

### 🗺️ 3. 지도 기반 탐색
- 네이버 지도 API 연동
- 위치 기반 주변 맛집 탐색
- 거리 계산 및 정렬(가까운순, 최신순, 인기순)

### 📝 4. 리뷰 & 이미지 업로드
- 텍스트 + 사진 5장까지 등록 가능 (S3 저장)
- 좋아요 기능 제공
- 최신순/좋아요순 정렬

### 🔧 5. 안정적 AWS 기반 인프라
- EC2 + Spring Boot + Nginx
- RDS(MySQL) Private Subnet 구성
- S3 이미지 저장
- CloudWatch + Athena 기반 로그 분석
- GitHub Actions 기반 CI/CD

---

## 🏗️ Architecture
<img width="762" height="732" alt="cpc최종아키텍쳐campeat" src="https://github.com/user-attachments/assets/6c2c6d5c-df0b-458a-87fa-558efe3fc666" />


### 주요 구성 요소
- **EC2 Auto Scaling Group** — 서버 확장성 확보  
- **Application Load Balancer** — 트래픽 분배, SSL 종료  
- **Private RDS** — 안전한 DB 운영  
- **S3** — 리뷰 이미지 저장  
- **CloudWatch / Athena** — 로그 수집 및 지표 분석  
- **CI/CD 파이프라인** — GitHub Actions → EC2 자동 배포

---

## 🖥️ Tech Stack

### Frontend
- Flutter (Dart)
- Provider / Bloc 관리
- Naver Map SDK

### Backend
- Spring Boot (Java)
- Spring Security + JWT
- JPA(Hibernate)
- AWS SDK (S3, SES 등)

### Infra
- AWS EC2, RDS, S3, CloudWatch, IAM, VPC
- GitHub Actions (CI/CD)
- Docker, Nginx
