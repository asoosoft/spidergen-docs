# 스파이더젠 시작하기


## 1. 다운로드 및 설치
### 1.1 Node.js 다운로드 및 설치
[**Node.js**](https://nodejs.org/ko/)
### 1.2 SpiderGen 다운로드
[**스파이더젠**](https://www.spidergen.org:8454/)
## 2. 스파이더젠 실행 및 프로젝트 생성
스파이더젠 다운로드 후 압축을 풀고 폴더내의 SpiderGen3.exe 파일을 실행한다.
### 2.1 프로젝트 생성

상단의 메뉴중 File > New Project...(Ctrl + Shift + N)를 선택한다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/NewProject.png?raw=true)

이 후 Project Name, Location, Project Type을 원하는대로 수정하고 프로젝트를 생성한다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/NewProjectDlg.png?raw=true)
### 2.2 기본적인 사용 방법
프로젝트가 생성되면 아래와 같이 프로젝트 트리가 보일 것이다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/ProjectTree.png?raw=true)

MainView.lay를 열어보면 빈 페이지가 보인다.

우측 하단의 Component 에는 스파이더젠에서 사용할 수 있는 각종 컴포넌트들이 모여 있다.

만약 Component가 보이지 않는다면 상단 메뉴중 View > Component(Ctrl + 1)을 선택 하면 나타날 것이다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/Component.png?raw=true)

Label을 더블클릭 하거나 드래그하여 lay파일의 캔버스에 올려놓으면 새 라벨이 생성된다.

우측의 Attribute를 선택하면 라벨의 속성을 볼 수 있다.

만약 Attribute가 보이지 않는다면 마찬가지로 상단 메뉴중 View > Attribute(Ctrl + 6)를 선택하면 나타날 것이다.

속성중의 Data > Text 를 Hello World로 바꿔본다.

![Alt text](https://github.com/sgs0116/spidergen-docs/blob/master/startMobile/HelloWorld.png?raw=true)

캔버스의 라벨이 Hello World라고 변경되었는지 확인해보도록 하자.

이 후에는 빌드 및 실행하는 방법을 알아볼텐데, 더 여러가지로 만져보고 싶다면 아래의 링크를 참고하여 사용해볼 수 있다.

* 구체적인 사용방법은 [**이 곳**](https://wikidocs.net/22777)에 정리되어 있다.

* 각 컴포넌트의 사용방법은 [**이 곳**](http://manual.spidergen.org/)에 정리되어 있다.

## 3. 빌드 및 실행
만들어진 프로젝트를 실행하기 위해 상단의 메뉴중 Build > Run Project(F5)를 선택 한다.

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