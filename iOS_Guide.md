# Tnkfactory SDK

## 목차

1. [SDK 설정하기](#1-sdk-설정하기)

   * [라이브러리 다운로드](#라이브러리-다운로드)
   * [라이브러리 등록](#라이브러리-등록) 
   * [Tnk 객체 초기화](#tnk-객체-초기화)
     * [초기화 API를 호출하는 방법](#초기화-api를-호출하는-방법)
     * [info.plist 파일에 APP_ID를 설정하는 방법](#infoplist-파일에-app_id를-설정하는-방법)
   * [App Transport Security 설정](#app-transport-security-설정)

## 1. SDK 설정하기

### 라이브러리 다운로드

**[][SDK Download v4.21](http://cdn1.tnkfactory.com/tnk/sdk/tnkad_sdk_ios_v4.21.zip)]**

### 라이브러리 등록

TnkAd SDK를 사용하기 위해서는 다운 받으신 Tnk SDK내에 들어있는 

- libtnksdk.a 파일과 tnksdk.h 파일을 XCode 프로젝트에 추가하셔야합니다.
- 그리고 TnkAd SDK에서 필요로하는 다음의 라이브러리 들을 같이 XCode 프로젝트에 추가해주시기 바랍니다.

| 라이브러리                    | 용도                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| libtnksdk.a                   | TnkAd SDK 라이브러리                                         |
| libz.tbd                      | 압축라이브러리 (TnkAd SDK가 서버통신시 사용함)               |
| MediaPlayer.framework         | 동영상 광고 표시를 위하여 사용됨                             |
| AdSupport.framework           | IdfA 값 획득을 위하여 사용됨 (반드시 Optional 모드로 추가해야 한다.) |
| SystemConfiguration.framework | Wifi 연결상태를 확인하기 위하여 사용됨                       |

**중요) 앱스토어 정책상 앱 보상형광고가 노출되는 경우 검수가 되지 않습니다.** 
**보상형 매체로 사용하시는 경우에는 앱 광고가 노출되지 않도록 앱스토어 검수전에 매체 설정이 필요하므로 사전에 저희쪽에 문의해주시면 안내해드리겠습니다.**

![Guide_01](./img/Guide_01.jpg)

### Tnk 객체 초기화

TnkAd SDK 사용전에 반드시 TnkSession 객체를 초기화해야 합니다. TnkSession 초기화는 2가지 방법을 제공합니다. 아래 2가지 방법 중 하나를 선택하시어 진행하시면 됩니다.

#### 초기화 API를 호출하는 방법

Application Delegate 내의 applicationDidFinishLaunchingWithOption 메소드 내에 아래와 같이 초기화 로직을 넣어주십시요.

 **\* APP_ID 값은 Tnk 사이트에서 앱 등록하면 발급받으실 수 있습니다. 이 값을 아래 초기화 로직의 your-application-id-from-tnk-site 부분에 넣어주셔야합니다.**

```objective-c
#import "tnksdk.h"

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    // Tnk 초기화
    [TnkSession initInstance:@"your-application-id-from-tnk-site"];

    // ...
}
```

#### info.plist 파일에 APP_ID를 설정하는 방법

Xcode 프로젝트의 info.plist 파일을 찾아서 아래와 같이 "tnkad_app_id" 항목을 추가하고 APP_ID 값을 설정합니다. 이곳에 설정해두면 TnkSession 객체가 처음 사용되는 시점에 자동으로 초기화 됩니다.

 **\* APP_ID 값은 Tnk 사이트에서 앱 등록하면 발급받으실 수 있습니다. 이 값을 아래 화면과 같이 Value 항목에 설정합니다.**

![Guide_02](./img/Guide_02.jpg)

### App Transport Security 설정

SDK v4.05 부터는 모든 통신이 HTTPS 로 이루어지므로 아래의 ATS 관련 설정을 하실 필요가 없습니다.
다만 SDK v4.04 이하 버전의 경우에는 iOS9 에서 SDK 가 올바르게 동작하기 위해서 아래의 내용을 앱의 plist 파일에 반드시 설정해주어야 합니다.

NSAppTransportSecurity 를 키로 Dictionary 값 NSExceptionDomains 을 등록하여 하위에 tnkfactory.com 을 설정합니다. 자세한 내용은 아래의 예시를 참고하세요.

#### iOS9 APP Transport Security 설정하기

```xml
<key>NSAppTransportSecurity</key>
<dict>
<key>NSExceptionDomains</key>
<dict>
<key>tnkfactory.com</key>
<dict>
<key>NSIncludesSubdomains</key>
<true/>
<key>NSExceptionRequiresForwardSecrecy</key>
<false/>
<key>NSExceptionAllowsInsecureHTTPLoads</key>
<true/>
</dict>
 </dict>
</dict>
```

![Guide_03](./img/Guide_03.png)

## 2. Interstitial Ad







## 3. Native Ad







## 4. Video Ad







## 5. Analytics Report

