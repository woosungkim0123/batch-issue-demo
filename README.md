# Batch Warning

## 링크

<a href="https://github.com/spring-projects/spring-batch/issues/4519" target="_blank"><strong>Spring Batch Issue#4519</strong></a>

<br>

<a href="https://github.com/spring-projects/spring-batch/releases/tag/v5.1.1" target="_blank"><strong>Spring Batch v5.1.1 릴리즈 노트</strong></a>

5.2 버전에서 수정될 예정이고 현재 5.1.1 버전에서는 JobRegistrySmartInitializingSingleton을 사용하여 이 문제를 해결할 수 있는 대체 방법을 제공하는 것으로 확인되었습니다.

<br>

<a href="https://woosungkim0123.github.io/2023_12_17_boot3_2_batch_warn/" target="_blank"><strong>Spring Boot 3.2에서의 Batch 처리 시 BeanPostProcessorChecker 경고 (블로그 포스트)</strong></a>

## 문제

Spring Boot 3.2.0 버전에서 Batch를 사용할 때, 많은 경고 로그가 발생하는 것을 확인했습니다.

## 추측

문제는 Spring Boot 3.2.0에서 변경된 내부 빈 초기화 메커니즘이 원인일 것 같습니다. 배치, 데이터 소스, 트랜잭션 관련 빈들이 메인 클래스보다 먼저 초기화되고 있으며, 이로 인해 이들 빈들 간의 의존성 관리와 초기화 순서에 문제가 발생하고 있는 것 같습니다.
