# Smart Factory - 모니터링 앱 (Android Client)

## 🌟 소개

**Smart Factory 모니터링 앱**은 사용자가 원격으로 스마트 팩토리의 센서 데이터를 실시간으로 확인하고, 센서별 알람을 설정하며, 다른 사용자와의 관계(팔로우)를 관리할 수 있는 안드로이드 애플리케이션입니다. 이 앱은 이전에 설명된 "SmartFactoryServer"의 클라이언트 역할을 수행합니다.

사용자는 자신의 센서 데이터를 모니터링하고, 특정 조건에 따라 알람을 설정하여 이상 상황 발생 시 푸시 알림을 받을 수 있습니다. 또한, 다른 사용자를 팔로우하여 해당 사용자의 센서 데이터를 열람하는 기능도 제공합니다.

## 🏅 주요 성과
<table align="center">
      <tr>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/61a08bdf-ebcb-4d5c-82b4-84b23467a586" width="400">
            </td>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/08b7f39e-1905-497b-a0a5-b4b10aea42be" width="400">
            </td>
      </tr>
      <tr>
            <td align="center">
                  AIoT 스마트 팩토리 시스템 연구를 위한 테스트베드 구축
            </td>
            <td align="center">
                  2022 한국정보기술학회 대학생 논문 경진대회 동상 수상
            </td>
      </tr>
</table>

## ✨ 주요 기능

* **사용자 인증:**
    * 서버를 통한 안전한 로그인 (`LoginActivity`).
    * (회원가입 기능은 `activity_register.xml` 레이아웃으로 존재하며, 구현을 가정합니다.)
* **실시간 센서 데이터 표시 (`MainActivity`):**
    * 로그인한 사용자의 등록된 센서 목록과 현재 값을 실시간으로 업데이트하여 보여줍니다 (`SensorValueAdapter`).
* **알람 설정 (`AlarmDialog`):**
    * 각 센서별로 최소/최대 임계값을 설정하여 알람 조건을 정의, 수정 또는 삭제할 수 있습니다.
    * 설정된 알람 조건은 서버에 저장됩니다.
* **팔로우십 관리 (`FollowershipSearchActivity`, Drawer):**
    * 다른 사용자 ID를 검색하고 팔로우를 요청할 수 있습니다.
    * 수신된 팔로우 요청을 수락하거나 거절할 수 있습니다.
    * 내가 팔로우하는 사용자 목록과 나를 팔로우하는 사용자 목록을 확인할 수 있습니다 (`UserItemAdapter`).
    * 팔로우 관계를 취소하거나 삭제할 수 있습니다.
* **타 사용자 모니터링 (`OtherUserActivity`):**
    * 내가 팔로우하고 있는 사용자의 센서 데이터를 실시간으로 확인할 수 있습니다.
* **푸시 알림 수신 (`PushService`):**
    * Firebase Cloud Messaging (FCM)을 통해 서버로부터 발송되는 알람 등의 푸시 알림을 수신합니다.
    * 로그인 시 FCM 토큰을 서버에 등록/갱신합니다.
* **내비게이션 드로어:**
    * 팔로우십 관리 화면으로 쉽게 이동하고, 현재 팔로우 중인 사용자 목록을 간편하게 확인할 수 있습니다.

## 📸 스크린샷

이 앱의 주요 화면들에 대한 스크린샷을 아래에 추가해주세요:
## 🏅 주요 성과
<table align="center">
      <tr>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/ff8c6e05-6e5c-4067-bb8f-2da0e0cdfe61" width="200">
            </td>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/230909b9-3af7-4191-92fd-9c3c97e7092e" width="200">
            </td>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/23af73f1-4ce1-4197-bccd-3c662c0156bc" width="200">
            </td>
      </tr>
      <tr>
            <td align="center">
                  로그인 화면 (`LoginActivity`)
            </td>
            <td align="center">
                  메인 화면 - 내 센서 목록 (`MainActivity`)
            </td>
            <td align="center">
                알람 설정 다이얼로그 (`AlarmDialog`)
            </td>
      </tr>
       <tr>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/4998eec8-6dfc-4ff6-8b1a-eabf276a16e2" width="200">
            </td>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/ea870b2a-92ef-4e8f-a851-b9756372f488" width="200">
            </td>
            <td align="center">
                  <image src="https://github.com/user-attachments/assets/6e824e9b-b08c-4f1a-b269-62ff99b2d903" width="200">
            </td>
      </tr>
      <tr>
            <td align="center">
                  내비게이션 드로어 (팔로우 목록 포함):
            </td>
            <td align="center">
                  팔로우십 관리 및 사용자 검색 화면 (`FollowershipSearchActivity`)
            </td>
            <td align="center">
                  타 계정 공장의 센서 데이터 화면 (`OtherUserActivity`)
            </td>
      </tr>
</table>

## ⚙️ 기술 스택

* **언어:** Java
* **플랫폼:** Android
* **네트워킹:** Retrofit2 (API 통신), Gson (JSON 파싱)
* **UI:** RecyclerView, DrawerLayout, Custom Dialogs
* **푸시 알림:** Firebase Cloud Messaging (FCM) Client
* **비동기 처리:** Android Threads, `ThreadPoolExecutor` (in `GetMyrelation`)
* **라이브러리:** AndroidX 라이브러리, Google Play Services (FCM용)

## 🚀 작동 방식 (주요 기능)

* **API 통신:**
    * `com.example.smartfactory.network.Callretrofit` 클래스를 통해 SmartFactoryServer와 모든 데이터 통신(로그인, 센서 데이터 조회, 알람 설정, 팔로우 관리 등)을 수행합니다.
* **실시간 데이터 업데이트:**
    * `MainActivity` 및 `OtherUserActivity`에서는 별도의 스레드를 사용하여 주기적으로 (0.5초 간격) 최신 센서 값을 서버로부터 가져와 UI를 갱신합니다.
* **사용자 관계 관리 (`GetMyrelation`):**
    * `GetMyrelation` 스레드는 현재 로그인한 사용자의 팔로우/팔로워 관계를 서버에서 조회합니다.
    * 조회된 데이터를 바탕으로 각 관계의 상태(`com.example.smartfactory.Activity.UserItemAdapter.Context` 값: "이동", "취소", "삭제", "요청")를 결정하고, `UserItemAdapter`가 적절한 UI(버튼 등)를 표시하도록 합니다.
    * 사용자 ID 조회를 위해 `ThreadPoolExecutor`를 사용하여 네트워크 요청을 병렬 처리합니다.
* **알람 설정:**
    * 사용자가 `SensorValueItem`의 '알람추가' 버튼을 누르면 `AlarmDialog`가 표시됩니다.
    * 사용자가 입력한 최소/최대 값은 `AlarmDTO` 객체로 변환되어 서버의 알람 관련 엔드포인트로 전송됩니다.
* **푸시 알림:**
    * `PushService` (FirebaseMessagingService)는 FCM으로부터 메시지를 수신합니다.
    * 새로운 FCM 토큰이 발급되면 서버로 전송하여 사용자의 푸시 토큰을 최신 상태로 유지합니다.

## 📦 프로젝트 구조

* **`com.example.smartfactory`**: 루트 패키지
    * **`Activity`**: UI 로직을 담당하는 액티비티 클래스
        * `mainActivity.MainActivity.java`
        * `LoginActivity.java`
        * `FollowershipSearchActivity.java`
        * `OtherUserActivity.java`
        * `RegisterActivity.java` (레이아웃만 제공됨)
        * **`PopUp` (sub-package)**: 커스텀 다이얼로그 관련 (`AlarmDialog.java`, `DialogListener.java`)
        * **`SensorValueAdapter` (sub-package)**: 센서 값 RecyclerView 어댑터 및 아이템 (`SensorValueAdapter.java`, `SensorValueItem.java`)
        * **`UserItemAdapter` (sub-package)**: 사용자 목록 RecyclerView 어댑터, 아이템 및 컨텍스트 정의 (`UserItemAdapter.java`, `UserItem.java`, `Context.java`)
    * `PushService.java`: FCM 메시지 처리를 위한 서비스.
    * **`network`**: 네트워크 통신 관련 클래스
        * `Callretrofit.java`: API 호출 메소드 집합.
        * `RetrofitAPI.java`: Retrofit 인터페이스 (API 엔드포인트 정의).
        * `RetrofitClient.java`: Retrofit 인스턴스 생성 및 설정.
        * `GetMyrelation.java`: 사용자 관계 데이터를 가져오고 처리하는 스레드.
        * `URL_holder.java` (가정): 서버 기본 URL을 정의하는 클래스 (별도 생성 필요).
        * **`DTO` (sub-package)**: 서버와 주고받는 데이터 전송 객체 (`AlarmDTO.java`, `FollowerShipDTO.java`, `SensorValue.java`).
        * **`VO` (sub-package)**: 주로 API 요청 시 사용되는 값 객체 (`FollowshipVO.java`, `LoginVO.java`, `Sensor.java`, `SignUpVO.java`).
    * **`res/layout`**: XML 레이아웃 파일
        * `activity_main.xml`, `activity_login.xml`, `activity_other_user.xml`, `activity_followership_search.xml`, `activity_register.xml`, `actvity_drawer.xml`, `popup_dailog.xml`, `sensor_value_item.xml`, `user_list_item.xml`.

## 🛠️ 설정 및 사전 준비 사항

1.  **Android Studio**: 최신 버전의 Android Studio를 권장합니다.
2.  **SmartFactoryServer**: 본 애플리케이션이 통신할 SmartFactoryServer 인스턴스가 실행 중이어야 합니다.
3.  **서버 URL 설정**:
    * `com.example.smartfactory.network` 패키지 내에 `URL_holder.java` 파일을 생성하고, SmartFactoryServer의 기본 URL을 지정해야 합니다.
        ```java
        // 예시: com/example/smartfactory/network/URL_holder.java
        package com.example.smartfactory.network;

        public class URL_holder {
            // SmartFactoryServer가 실행 중인 주소로 변경해야 합니다.
            private static final String URL = "http://YOUR_SERVER_IP_OR_DOMAIN:PORT/"; 
            public static String getURL() {
                return URL;
            }
        }
        ```
4.  **Firebase 프로젝트 연동 (FCM용)**:
    * Firebase 콘솔에서 Android 앱을 프로젝트에 추가합니다.
    * `google-services.json` 파일을 다운로드하여 Android 앱의 `app` 모듈 디렉토리 (`app/`)에 추가합니다.
    * 필요한 Firebase 라이브러리 의존성을 `build.gradle (Module :app)` 파일에 추가합니다.
