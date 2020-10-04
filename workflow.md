
# Git Workflow Description

## 가정
새로 프로젝트를 수주하여 웹 프로그램을 개발하려고 한다.
협업 & 버전 관리 도구로는 git을 사용하기로 했으며, Gitflow Workflow를 이용해 버전을 관리하기로 하였다.
팀원은 총 5명이며, 역할은 PM 1명, Developer 4명으로 나누어져 있고, 팀원마다 관여하는 Branch를 기준으로 다시 역할을 세부적으로 나누었다.


## 팀 업무 분담 & 담당 브랜치

- PM(류관우) : Master, Release Branch 담당
- Feature Merge Devloper(김형규) : Develop Branch 담당
- Feature Developer(이민주, 황한혁) : Feature Branch 담당
- Bug Fixer(김건하) : Hotfix Branch 담당


## 개발 정책

>- 개발, 변경사항은 PM의 리뷰-테스트 통과 후 커밋을 찍고 밀어넣는다.

### 로컬-개발서버-테스트서버-운영서버 전략

>>- 로컬,개발서버는 Develop Branch를 기준으로 빌드-배포한다.
>>- 테스트-운영서버는 Master Branch를 기준으로 빌드-배포한다.

### Branch 이용 관리전략

>>- 프로젝트에 참여중인 개발자들은 Develop branch를 기준으로 업무를 진행한다.
>>- Master branch는 Project Manger,PM 이 관리한다.
>>- 사전에 협의되지 않은 내용은 Master Branch에 반영하지 않는다.

### Branch 이름 표기

>>- Master Branch는 Semantic Versioning을 사용한다.
>>- Develop Branch는 Master Branch를 따라 ‘develop-1.2.1.132’ 와 같이 표현한다. 뒤쪽의 버전은 각각 ‘Major Version . Minor Version . Patches . 빌드수’ 를 의미한다. 
>>- Feature Branch는 Version 뒤에 개발한 기능 혹은 Issue를 명시한다. (e.g. 1.2.1.132-AR인식기능-2)
>>- Release Branch또한 Mater Branch를 따른다.
>>- Hotfix Branch는 branch해서 나온 Master Branch의 Version을 명시한다. (e.g. hotfix-1.2.1-1   =>  master-1.2.1 에서 나온 branch)

## 시나리오

### 프로토타입 제작
프로토타입 제작을 시작한다. 기획된 홈페이지의 기본적인 구조를 Html화 해서 Master Branch에 게시하였고, 이후 각자 독립된 3가지의 기능을 만들어서 Develop Branch에 Merge 한 후 게시하였다

### 베타 버전 제작
프로토타입 제작 이후 제작 승인을 받아 베타 버전을 개발한다. 기존에 있었던 Develop Branch에서 기능 1가지를 추가하려고 하는데, Branch를 추가한 후 기능이 예상보다 복잡하여 Feature Developer가 서로 상의를 가졌다. 제시된 해결 방법은 해당 기능을 세부적으로 나누어 Feature Branch에서 파생된 Feature1 Branch와 Feature1 Branch에서 파생된 Feature2 Branch를 만든 뒤 Feature2, Feature1, Feature 순으로 Merge하기로 하였다.
그러나 개발 도중 Feature1 Branch에서 개발하던 기능이 Feature Branch에서도 중복으로 개발되어 Feature1 Branch는 삭제하고, Feature2 Branch만 Feature Branch와 Merge 하기로 하였다.

### 릴리즈
베타 버전이 순조롭게 개발되어 몇 가지 기능 개발 후 릴리즈를 진행한다. 2가지의 간단한 기능을 추가한 이후 릴리즈를 위해 v1.0 Release Branch를 생성하였으나, 내부 QA 중 개발한 기능에 심각한 결함이 발견되어 릴리즈 전 긴급 Hotfix에 나섰다. 다행히 버그를 수정하여 v.1.1 Release Branch를 기준으로 서비스를 개시하였다.

### 릴리즈 이후 사후 관리
그렇게 순조롭게 서비스를 진행하던 도중, 시간이 지나 Patch를 할 부분이 생겼고, 개발자들은 독립된 기능 2개와 그 중 한 기능에 종속된 기능 1개를 개발하여 Patch를 진행하였다. 불행하게도 패치 직후 서비스에서 결함이 발견되었고, Hotfix를 진행하여 버그를 수정해 다시 서비스를 진행하였다.
