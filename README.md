# URL 처리가 가능한 InAppBrowser  
이 플러그인은 URL처리가 가능한 루틴을 추가하기 위해 [org.apache.cordova.inappbrowser](https://github.com/apache/cordova-plugin-inappbrowser)를 fork한 버전입니다. 기존 InAppBrowser가 제공하는 기능은 그대로 유지하도록 구성하였기 때문에 이 플러그인에서 추가된 기능을 제외하고는 InAppBrowser의 공식문서를 참고하시기 바랍니다.  

## 안드로이드 변경사항
`InAppBrowser.java`에서 inAppBrowser에 설정되는 `InAppBrowserClient`대신, `shouldOverrideUrlLoading`를 override한 `InAppBrowserUrlSchemeClient`를 사용합니다.  

URL을 처리하는 handler는 별도의 플러그인에서 로드될 수 있도록 ClassLoader방식으로 구현되어있으며 클래스 명은 config.xml에 선언된 `IamportURLSchemeHandler`를 사용합니다.  

### 예시
[iamport-ionic-inicis](https://github.com/iamport/iamport-ionic-inicis)플러그인  
Hander를 구현해 처리하려는 다른 cordova plugin에서 아래의 설정을 추가하도록 합니다.  

```xml  
<preference name="IamportURLSchemeHandler" value="kr.iamport.ionic_inicis.InicisUrlSchemeHandler"/>
```

## iOS 변경사항  
진행사항 아직 없음(검토 중)  