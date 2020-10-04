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
