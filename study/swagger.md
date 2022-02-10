# Swagger

## Swagger 란?
### Open Api Specification (OAS) 를 위한 framework 입니다.
### Api endpoints 를 명세하기 위한 서버 사이드 툴로 사용될 수 있습니다. 

## Swagger 를 사용하는 방법? 백엔드 api 서버를 spring boot 로 가정합니다.
## 1. Spring boot integration
 - build.gradle dependencies 에 implementation 'org.springdoc:springdoc-openapi-ui:1.5.7' 를 추가합니다.
 - @Controller 에 설계된 api methods 에 @Operation, @Tag, 등의 어노테이션으로 명세를 작성합니다.
 - 서버를 실행한 후 ...domain:port/swagger-ui/index.html?configUrl=/v3/api-docs/swagger-config#/ 로 접속하여 명세를 확인할 수 있습니다.

### 이 방법의 장점?
 - 명세 작성을 자동화하고 명세가 api server 에 bind 되었기 때문에 서버 코드만 신경쓰면 명세 버전을 관리할 필요가 없습니다.
 - swagger-ui 를 통한 테스팅의 경우 mock data 를 사용하지 않고 실제 서버에 테스트할 수 있습니다. 
 - 별도의 버전 컨트롤이 필요하지 않습니다. 

### 이 방법의 단점?
 - api 서버에 bind 되었기 때문에 서버가 local 일 경우 문서 배포에 어려움이 있습니다 (문서는 mock data 를 포함합니다). 하나의 해결 방법으로는 서버를 cloud 에 배포하여 문서의 배포를 자동으로 수행하는 것입니다.
 - 소스 코드에 추가적인 어노테이션이 필요합니다. 다만 codegen 을 통해 mitigate 할 수 있습니다.


## 2. Swagger-hub 사용
 - Swagger-hub 에 접속하여 새로운 api 문서를 생성하고, yaml 파일 작업을 통해 명세를 작성합니다.
 - 작성 후 publish, sync 를 클릭한 후 배포합니다.
 - stub 서버를 추가로 배포할 수 있습니다.

### 이 방법의 장점?
 - api 명세 문서가 서버에 bind 되지 않습니다. 서버를 local 에 띄워도 문서를 배포할 수 있습니다.
 - stub 서버를 배포할 수 있습니다. Local 개발 환경에서 stub 서버를 다운받아, 복잡한 설정 없이 개발용 api 서버를 띄울 수 있습니다.

### 이 방법의 단점?
 - 명세 작성이 추가적으로 필요합니다. yaml 을 자동으로 생성하지 않습니다.
 - 별도의 버전 컨트롤이 필요합니다. 이는 소스 코드(예를 들어, 깃허브 버전 관리)와는 별개입니다



### 개인적인 의견으로는 개발 규모가 작은 경우는 전자의 방법이 더 편할 것 같습니다. 개발 초기 단계에서 전자의 방법으로 진행하다가, gradle dependency 와 어노테이션을 걷어내고 swagger-hub 로 migrate 하는 방법도 괜찮을 것 같습니다.
