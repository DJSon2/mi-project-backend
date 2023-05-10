# 프로젝트 명 : Miracle Investment(MI, ERP 프로그램)
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/384581a7-1fb8-413c-8dc0-8c8090c3177e)


## 프로젝트 개요 
* ERP 공용 기능을 만들어 여러 회사에 배포하려는 취지로 개발
* 이전에 경험해본 Spring Boot와 React를 Rest API를 활용해 개발
* 개발 인원 : 5명

## 개발 환경
* 운영체재 : Window 10 64 bit
* DB : Oracle 18c
* API : Java Servlet 3.1
* 형상관리 : GitLab
* 언어 : Java Script, Java Open JDK 1.8.0, React 18.1.0, Java 11, CSS3
* 마크업 언어: HTML5

# 추가한 starter들
 * JDBC API
 * Oracle Driver
 * Spring Boot DevTools
 * Spring Web
 * Spring Security
 * Spring Data Jpa
 * pom.xml에 jwt 관련 라이브러리, modelmapper 및 파일 업로드 dependency 추가

## 개발 기간 : 2023.01.09 ~ 2023.01.31 
* 제안 요청, 착수 기간 :  01.06 ~ 01.09
* 업무 분석 및 요건 정의 기간 : 01.09 ~ 01.16
* 기획 및 설계 단계 : 01.12 ~ 01.19
* 개발 단계 : 01.14 ~ 01.29
* 테스트 단계 : 01.14 ~ 01.30
* 시연 발표 01.31  

## 프로젝트 전체 주요 기능 
* 사내 직원들만 사용 가능한 커뮤니티 게시판
* 회사 전체 공지사항 확인 가능한 공지사항 게시판
* 회원가입 당시 기재한 정보를 조회할 수 있는 마이페이지
* 직원의 정보를 수정할 수 있는 인사팀
* 로그인 시 사용 가능한 출/퇴 버튼을 통한 유동적인 근태 관리 가능
* 인사팀의 추가 근무 시간, 남은 연차 일 수를 포함한 직원들의 급여 관리 시스템

## 프로젝트 구조도(whimsical)
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/d132e02b-f289-4ed9-8810-148a69bbd559)

## 담당 역할 : 인사2팀(HrTeam2) 기여 100%
* 급여 관리 시스템(데이터 조회, 수정 및 추가 기능)
* 근태 관리 시스템(출퇴근, 누전 근무 시간확인)

## DB 구조(Baker Notation)
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/56078a2e-499a-44e7-8750-a873311285c9)



## Spring Boot MVC 패턴 설계 구조도
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/514d1c0a-7f90-4a25-8f84-560d64a73c8d)

## 담당 역할 적용 및 설계 기준
* 남은 연차 수당 적용 기준
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/be662cb4-4197-4c95-a932-248aceda658f)
* 추가 근무 수당 적용 기준
![image](https://github.com/DJSon2/mi-project-backend/assets/124123956/594dff83-83cb-4c93-b5d8-e6db6c7fb1e6)





# 주요 file
[급여, 근태 관련 file](https://github.com/DJSon2/mi-project-backend/tree/main/hrTeam2)



---
# 프로젝트 후기
## 프로젝트를 다룰 수 있고, 잘 이해할 수 있었던 기술
저는 이번 프로젝트를 진행하면서 __MVC 구조와 REST API에__ 대해 더욱 잘 이해할 수 있었던 것 같습니다. 프로그램 특성 상 새로운 기능을 추가하거나 기존 것을 수정할 일이 많은데, MVC 구조 특성 상 구조화하여 View 역할을 하는 React, 요청을 받고 최종 출력하는 Controller와 대부분의 로직을 처리하는 Service 파트 등 각자의 역할을 나눠서 유지보수가 쉽고 가독성을 좋게 만들어 주기 때문에 더욱 효과적이였던 것 같으며 또한 데이터를 주고 받는 방식을 캐시를 이용하고 서버 간 통신을 간편하고 일관성 있게 이루어지는 REST API 아키텍처 스타일로 하였기 때문에 서버 간 통신과 데이터 수정 작업이 많이 이루어지는 프로젝트 특성 상 더 알맞는 다는 것을 알게되었으며, 아키텍처 구조들에 더 잘 이해하게 되었다고 생각합니다.

## 프로젝트 구현 시 문제해결 경험
프로젝트 __DB 인서트 기능 개발 진행 상황에서 어려움을 느꼈던 상황이__ 있었는데, 당시에 로그를 찍어주며 인서트 메소드가 정상적으로 작동이 되며 FK값을 가지고 오는 것으로 보였는데 DB에는 NULL값으로 저장이 되는 상황이었습니다. 당시에 조급한 마음이 있기도 했지만 로그 상으로는 지정했던 메소드가 정상 작동하며, Postman으로 테스트 시에도 정상적으로 DB에 값이 저장이 됐기 때문에 그 이유를 찾기가 더 힘들었습니다. 결국 하나하나 다 로그를 찍어 찾아보자는 마음으로 넘어오는 값, DB에 저장되는 값들을 찍어보니 React 쪽에서는 원하는 값이 넘어오지만 DB 저장 시에 값이 들어가지 않는다는 것을 확인했습니다. 확인해보니 값을 받아줄 DTO파일에 FK값의 변수명이 아닌 PK값의 변수명으로 중복됐었습니다. __값을 받아줄 변수 명을 알맞게 바꿔주니__ 정상적으로 값을 DB에 저장을 하며 에러를 해결했던 상황도 있었습니다. 


## 협업을 통한 개선 경험
팀원간에 있었던 일 들 중 하나는 프로젝트 설계 당시 프로그램의 시스템이나 기능 등의 방향을 쉽게 정하지 못했습니다. 그 이유는 프로젝트 설계 당시 __ERP 프로그램__ 특성상 회사 내의 시스템을 잘 알고 있고 그 특성에 맞춰 프로그램을 설계 해야했기에 정확한 시스템을 파악, 이해했어야 했습니다. 하지만 팀원 대부분 회사  경험이 없거나 있더라도 ERP 프로그램을 안써봤기 때문에 잠깐의 자료 조사를 하고 논의를 했지만 대부분 확실치 않거나 조금씩 회사별로 시스템이 달라 결론이 나오진 않은 상태로 시간이 길어졌습니다. 저 또한 자세히 정확한 회사 시스템과 필요 기능이 무엇인지 잘 알지 못하는 상태였기 때문에 중재 역할로써 팀원분들에게 자료 조사를 충분히 할 수 있게 __1~2일 정도 시간을 천천히 갖고 조사를 하자고 제안을__ 했습니다. 그 결과 자료조사가 필요하지 않은 역할 담당, 팀 규칙 등 우선적으로 처리 가능한 일들을 처리하고 이후에 프로그램 기능 등을 논의를 했기 때문에 이전보다 정확한 자료와 생각을 가지고 기준을 정할 수 있었습니다. 이 때문에 다른 팀보다 설계 기간이 하루 정도 늦어지게 되었지만 그만큼 프로젝트 중간에 설계를 변경할 일이 없었기 때문에 오히려 더 수월하게 진행되었다고 생각합니다.

## 프로젝트를 통해 성장한 점
이 프로젝트를 진행하면서 마음이 좀 급해지는 경향이 있다는 것을 느꼈었습니다. 특히 이전 프로젝트를 진행할 때와는 다르게 프로젝트의 설계 과정에 시간이 많이 소비되어 비교적 개발하는 시간이 적었습니다. 이 때문인지 꼼꼼하게 체크를 하지 못해 기본적인 실수 등을 하면서 오류를 일어나 더 시간이 지체되는 경우가 있었습니다. 실제로 데이터 수정 기능 개발 과정 중에 Spring Boot에서 @Transactional 어노테이션을 누락해서 메서드를 작성했던 적이 있었습니다. 이 때문에 원하는 값이 나오지 않거나 에러가 나는 경우가 있었습니다. 이후 하나의 실행 과정에 같이 실행되어야 하는 메소드가 정상 기능을 못했다는 것을 알았습니다. 이처럼 기본적인 설정, 명령 같은 개념들을 망각하거나 놓쳐가지고 실제 기능 개발보다 시간이 많이 들어갔었으며, 에러들을 찾아내고 바로잡는데 더 오래걸리는 것을 깨달았습니다. 다음부터는 __일단 코드를 작성할려는 습관보다는__ 먼저 필요한 설정들이 무엇이 있고 어떤 식으로 개발하는 것이 효율적일지 __생각하면서 개발을 하는 습관이__  필요하다는 것을 습니다.




# front-end-repository(React) 
[front-end-repository](https://github.com/DJSon2/mi-repository-frontend)
