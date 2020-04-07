# 스파이더젠 시작하기


## 1. 다운로드 및 설치
### 1.1 Node.js 설치
[**Node.js**](https://nodejs.org/ko/)
### 1.2 SpiderGen 설치
[**스파이더젠**](https://www.spidergen.org:8454/)
## 2. 스파이더젠 실행 및 프로젝트 생성
스파이더젠 다운로드 후 압축을 풀고 폴더내의 SpiderGen3.exe를 실행한다.
### 2.1 프로젝트 생성

상단의 메뉴중에 File > New Project... 을 선택한다.

이는 Ctrl + Shift + N 으로도 가능하다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/NewProject.png?raw=true)
### 2.2 기본적인 사용법
* [**(구체적인 사용방법은 링크)**](https://wikidocs.net/22777)

## 3. 빌드 및 실행
F5

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/RunProject.png?raw=true)
### 3.1 시뮬레이터
### 3.2 네이티브
#### 3.2.1 Cordova 설치
Build > Cordova Started Fast > Create cordova project

해당 프로젝트에 Cordova 폴더가 생성됨. (위치 변경 불가능)
#### 3.2.2 안드로이드에서 실행
Select Platform > android > Add a platform

Build & Run
(이 과정은 굳이 거치지 않고 android studio를 열어서 사용해도 가능하다.)

1) android가 run될때 필요한 목록
ㄱ) javac(jdk 설치)
ㄴ) gradle 설치후에 환경변수 세팅해줘야 동작이 된다..
ㄷ) ㄱ,ㄴ이 설치되지 않은상태 였다면 스파이더젠을 재실행 해야 한다..
    (스파이더젠 백그라운드에서 도는 노드 서버의 재시작이 필요)

로컬 파일
file:///android_asset/www/index.html

```java
package com.spidergen.testprh;

import android.os.Build;
import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;

import org.apache.cordova.*;

public class MainActivity extends CordovaActivity
{
    private WebView webView = null;

    @Override
    public void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        init();

        // enable Cordova apps to be started in the background
        Bundle extras = getIntent().getExtras();
        if (extras != null && extras.getBoolean("cdvStartInBackground", false)) {
            moveTaskToBack(true);
        }

        this.webView = (WebView) this.appView.getView();
        WebSettings settings = webView.getSettings();
        if (Build.VERSION.SDK_INT > Build.VERSION_CODES.ICE_CREAM_SANDWICH)
            settings.setTextZoom(100);
        //meta 태그의 스케일을 위해 다음 두 코드는 반드시 필요한다.

        //웹뷰가 html viewport 메타 태그를 지원하게 한다.
        settings.setUseWideViewPort(true);
        //웹뷰가 html 컨텐츠가 웹뷰보다 클 경우 스크린 크기에 맞게 조정되도록 한다.
        settings.setLoadWithOverviewMode(true);

        loadUrl(launchUrl);
    }
}
```
### 4.2 플러그인
#### 4.2.1 사용법
#### 4.2.2 생성하기
## 5. iOS에서 실행
### 5.1 로컬 파일
### 5.2 플러그인
#### 5.2.1 사용법
#### 5.2.2 생성하기






<!--
## 1.3 Cordova 설치
* ### 설치
>   ```
>   $npm install -g cordova

* ### 폴더생성
>   ```
>   $npm create MyApp

* ### 플랫폼 생성
>   ```
>   $cd MyApp
>   $cordova platform add android
>   $cordova platform add ios


## 1.4 AndroidStudio 설치하기
[**안드로이드 스튜디오**](https://developer.android.com/studio?hl=ko)
-->