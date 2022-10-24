# 전자정부 표준프레임워크 4.0.0 기반 개발 시작하기(Getting Started)

## 개요

본 가이드는 전자정부 표준프레임워크 기반의 단순한 응용프로그램(HelloWorld)를 직접 실습해 봄으로써 빠른 시간 내에 전자정부 프레임워크의 기본 기능을 파악하기 위하여 제공한다. 본 가이드의 사용자는 java 및 spring framework에 대한 기본적인 지식이 있다는 것을 가정하였다.

아래의 3가지 단계에 따라 순서대로 따라하기 방식으로 진행된다.

    1.개발환경 설치 : 실습을 위한 개발환경을 구축한다.
    2.프로젝트 생성 : 제공한 샘플 프로젝트를 이용하여 HelloWorld 응용 어플리케이션을 생성하고 실행해 본다.
    3.자세히 들여다 보기 : 생성/실행한 프로젝트의 내부 소스코드를 학습하여 전자정부 표준 프레임워크 기반의 응용 어플리케이션 구현의 원리를 이해한다.

전자정부 표준 프레임워크 기반의 Hello World 응용 프로그램 개발 및 실행을 위한 구현도구의 환경정보는 다음과 같다.

| 항목 |          설명           | 비고             |
| :--: | :---------------------: | :--------------- |
|  OS  |   Windows 10, 7 이상    |                  |
| IDE  | Eclipse 4.19.0(2021-06) | JDK 11 이상 필요 |

- (2.7 이상) JavaEE(J2EE) 5 혹은 JDK1.5 이상의 환경 (단, 개발환경 2.7 이상에서는 JDK 1.6 이상 필요)
- (3.0 이상) JavaEE(J2EE) 6 혹은 JDK1.6 이상의 환경
- (3.5 이상) JavaEE(J2EE) 7 혹은 JDK1.7 이상의 환경 (단, 개발환경 3.5.1 부터 JDK8 적용 가능)
- (3.6 이상) JavaEE(J2EE) 7 혹은 JDK1.7 이상의 환경
- (3.7 이상) JavaEE(J2EE) 8 혹은 JDK1.8 이상의 환경
- (3.8 이상) JavaEE(J2EE) 8 혹은 JDK1.8 이상의 환경
- (3.9 이상) JavaEE(J2EE) 8 혹은 JDK1.8 이상의 환경
- (3.10 이상) JavaEE(J2EE) 8 혹은 JDK1.8 이상의 환경
- (4.0 이상) JavaEE(J2EE) 8 혹은 JDK1.8 이상의 환경 (단, 개발환경 4.0.0 부터 JDK11 이상 필요)
  - Servlet 3.1 사용
  - Servlet 2.5는 공통 컴포넌트 커스터마이징(Servlet 2.5 Downgrade) 참고

## Step 1. 개발환경 설치

전자정부 표준프레임워크에서 제공하는 구현도구(implementation tool) 및 HelloWorld 응용 어플리케이션을 위한 종속라이브러리를 이용하여 실습에 필요한 개발환경을 설치한다.

### 개발환경설치

먼저 eclipse 기반의 전자정부표준 프레임워크의 [|구현도구(implementation tool) 설치](https://naver.com)를 참조하여 설치한다.

### 플러그인 업데이트

설치한 구현도구의 플러그인이 최신 모듈을 사용할 수 있도록 [구현도구(implementation tool) 플러그인 업데이트](https://naver.com)를 참조하여 업데이트를 수행한다.

### Maven 환경설정

시작하기 개발환경은 실제 프로젝트 수행환경과 달리 Nexus를 이용하지 않고, 종속 라이브러리를 Maven 로컬 파일저장소에 수동으로 복사하여 개발환경을 구축한다.
Maven의 로컬 파일 저장소를 설정하기 위하여 제공한 [maven repostiory 4.0](https://naver.com) 파일을 임의의 디렉토리에 압축 해제하여 설치한다.

#### 종속라이브러리 설치순서

    * Maven 설정파일 및 종속라이브러리를 포함한 [maven repostiory 4.0](https://naver.com) 를 다운로드 한다.

- 다운로드 받은 파일은 임의의 디렉토리에서 압축해제한다.(압축해제한 디렉토리는 **_[MavenRepository 설치디렉토리]_** 로 명명한다.)
- 텍스트 에디터를 이용하여 **_[MavenRepository 설치디렉토리]_**/settings.xml 파일의 localRepository 항목의 값을 다음과 같이 수정한다.

```
<settings>
    ...
    <localRepository> [MavenRepository 설치디렉토리]/repository </localRepository>
    ...
</settings>
```
