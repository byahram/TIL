# Window 환경에서 Laravel 개발 환경 구축하기

---
<p align="center">
<img width="50%" src="../assets/img/laravel.png">
</p>

---

<br>

## 1. XAMPP 설치
<https://www.atechtown.com/xampp-install-guide-windows/>

### APM(Application Performance Management)
라라벨을 설치하기 전에 먼저 APM(Application Performance Management) 관리 툴이 설치되어야 한다. 
* APM 이란 운영 중인 시스템에 대한 가용성 확보, 다운타임 최소화 등을 통해 안정적인 시스템 운영을 위하여 부하량과 접속자 파악 및 장애진단 등을 목적으로 하는 성능 모니터링 도구를 말한다.
* 리소스 모니터링 & 엔드투엔드 모니터링 (End to End)

### XAMPP 설치
APM 관리 툴로 XAMPP가 있다. 

X(cross-platform), A(Apache Web Server), M(MariaDB), P(PHP), P(Perl)의 줄임말로 Apache Friends가 개발한 크로스 플랫폼 웹 서버 패키지 이다.

리눅스뿐만 아니라 윈도우, MacOS에서도 구동할 수 있다.

XAMPP를 이용하면 php, apache, mysql을 한번에 설치하고 관리하기 용이하므로 간단하게 개발 환경을 구축해보려 한다.

![missing](../assets/img/221203_1.png)

<https://www.apachefriends.org/index.html>

홈페이지에서 각 환경에 맞는 인스톨러를 다운로드 받고 다운로드를 받은 후 설치 프로그램을 클릭한다.

중간중간에 Question 창과 Warning 창이 열렸는데 큰 문제가 될 것 같아 보이지 않아 '예' 누르고 '확인' 누르고 넘어가도록 한다.

![missing](../assets/img/221203_2.png)

Welcome to the XAMPP Setup Wizard 창이 지난 후 필요한 컴포넌트를 선택하면 되는데 나는 우선 기본적인 Apache, MySQL Server 과 PHP Program Language를 선택하고 다음 스텝으로 넘어갔다.

![missing](../assets/img/221203_3.png)

![missing](../assets/img/221203_4.png)

다음 스텝으로 넘어가면 XAMPP를 설치할 폴더를 생성하고, 사용할 언어를 선택하고, 다음으로 넘어가면 Ready to Install이 뜨면서 설치가 시작된다.

![missing](../assets/img/221203_5.png)

![missing](../assets/img/221203_6.png)

얼마 걸리지 않아 설치 완료가 뜨고 설치가 된 XAMPP Control Panel을 열어보면 아까 선택하여 설치한 Apache, MySQL 서비스 컨트롤 및 로그창을 확인할 수 있다.

Start를 누르고 로그창을 확인한다.

![missing](../assets/img/221203_7.png)

그러면 localhost로 접속이 가능한 것을 볼 수 있다.

![missing](../assets/img/221203_8.png)

Apache Web Server 홈 디렉토리는 XAMPP를 기본값으로 설치했을 경우 C:\xampp\htdocs에서 확인이 가능하다.

<br>

## 2. Composer 설치
<https://getcomposer.org/>

라라벨을 설치하기 전에 먼저 APM(Application Performance Management) 관리 툴이 설치되어야 한다. 
* APM 이란 운영 중인 시스템에 대한 가용성 확보, 다운타임 최소화 등을 통해 안정적인 시스템 운영을 위하여 부하량과 접속자 파악 및 장애진단 등을 목적으로 하는 성능 모니터링 도구를 말한다.
* 리소스 모니터링 & 엔드투엔드 모니터링 (End to End)

![missing](../assets/img/221203_9.png)

![missing](../assets/img/221203_10.png)

다운로드 누르고 다음 스텝으로 넘어가서 getComposer의 Download 페이지를 보면 Windows 환경을 위한 설치 방법이 잘 설명되어 있는데 Installer을 사용하면 알아서 필요한 환경 변수 모두 설정해준다.

![missing](../assets/img/221203_11.png)

중간에 composer 저장할 곳을 선택하고 다음 스텝으로 넘어간다.

![missing](../assets/img/221203_13.png)

스텝1에서 다운받은 xampp/php/php.exe 경로를 선택해준다. 

![missing](../assets/img/221203_14.png)

![missing](../assets/img/221203_15.png)

중간에 proxy settings를 선택할 지는 optional이고 다음으로 넘어가면 마지막 단계로 Install을 클릭하면 끝난다.

![missing](../assets/img/221203_16.png)

Windows PowerShell에서 설치를 확인할 수 있다.

<br>

## 3. Laravel 설치
### 라라벨(Laravel) 설치하기
스텝2에서 설치했던 Composer를 사용해 Laravel Installer Download를 한다

```
$composer global require laravel/installer
```

![missing](../assets/img/221203_17.png)

![missing](../assets/img/221203_18.png)

```
$laravel new (project_name)
```

![missing](../assets/img/221203_19.png)

![missing](../assets/img/221203_20.png)

laravel 설치가 완료되면 laravel new 명령어를 통해 새로운 프로젝트를 생성한다.

프로젝트가 생성되면 프로젝트를 생성한 폴더에서 확인 할 수 있다.

![missing](../assets/img/221203_21.png)

vsCode로 확인해보니 라라벨 구동에 필요한 모든 파일과 디렉토리가 자동으로 생성되었다.

Laravel 설치를 끝내고 서버에서 구동시킬 준비가 완료되었다는 것이다.

```
$php artisan --version
```

![missing](../assets/img/221203_22.png)

Laravel Framework 버전과 함게 뜨면 성공!

artisan은 라라벨의 커맨드라인 툴이다.

### 라라벨(Laravel) 실행하기
```
$php artisan serve
```

![missing](../assets/img/221203_23.png)

위의 명령어로 라라벨을 실행하면 Server running on [http://127.0.0.1:8000] 

즉, http://127.0.0.1:8000 을 클릭해서 보면

![missing](../assets/img/221203_24.png)

![missing](../assets/img/221203_25.png)

드디어 라라벨 개발 환경 구축이 완료되었다.

<br>

## :zap: 참조
* <https://rninche01.tistory.com/entry/01-개발환경-구축>
* <https://starpia.tistory.com/13>
* <https://squareinven.tistory.com/49>

<br>
