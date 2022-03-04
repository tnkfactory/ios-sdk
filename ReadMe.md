# 아래의 SDK 는 더 이상 사용되지 않습니다.
# 신규 SDK 를 사용하시기 바랍니다.

# Tnkfactory SDK

TnkAd SDK는 Tnk의 광고 네트워크 상에서 광고앱 이나 매체앱을 개발하기 위하여 제공되는 통합된 SDK이며 아래의 기능들을 사용하실 수 있습니다.

* 전면광고(Interstitial Ad)
* 네이티브 광고(Native Ad)
* 비디오 광고(Video Ad)

## iOS

### iOS Guide

[iOS 가이드 문서](./iOS_Guide.md)

### Update Notice

* 2020.07.07 
  * v4.21 업데이트
    *  오퍼월 처음 띄우는 시점에 개인정보 수집 동의 창 띄우도록 기능 추가
* 2019.12.30
  * v4.20 업데이트
    * 오퍼월 UI Autolayout 으로 재구현
    * 내부 기능 개선
* 2019.11.28
  * v4.19 업데이트
    * 보상형 광고리스트(오퍼월) 기능 추가
      * Header 영역 커스터마이징 기능 추가 : [TnkSession sharedInstance].adListSectionHeaderView = UIView 지정
      * Modal 로 띄울 경우 닫기버튼에 이미지 설정 기능 추가 : [TnkSession sharedInstance].headerCloseButtonImage = UIImage 지정
* 2019.11.19
  * v4.18 업데이트
    * iOS13, iPhone11 지원
    * COPPA, GDPR 설정 기능 추가
    * 4.18b : iOS13에서 NavigationBar 높이 계산오류가 있어서 work-round 처리
* 2018.05.14
  * v4.16 업데이트
    * 전면광고 프레임 신규디자인 추가
    * NativeAd 에 소재 2 종류 추가 : AD_STYLE_BANNER_LANDSCAPE (720 x 100) , AD_STYLE_BANNER_LANDSCAPE (720 x 200)
* 2018.01.26
  * 4.15 업데이트
    * 보상형광고리스트용 UIView 제공
    * 보상형광고리스트 타이틀 영역에 이용문의 버튼 추가하는 기능
    * 보상형 광고리스트 하단의 Footer 영역 숨기는 기능 추가
* 2017.06.16
  * 4.14 업데이트
    * 2-button 전면 프레임의 라벨 지정 기능 및 닫기 버튼 위치 지정 기능 추가
* 2016.10.19
  * 4.13 업데이트
    * 전면광고 화면에서 (X) 버튼이 눌리지 않는 경우가 있어 수정함.
* 2016.09.22
  * 4.12 업데이트
    * TnkNativeAdManager 기능 추가 (한번에 여러건의 NativeAdItem 을 조회)
    * NativeAd 내부 기능 개선
    * 전면 2-버튼 프레임 모두 지원하도록 기능 추가
    * iOS10 지원, XCode v8.0으로 빌드.
* [Release Notes 더보기](./iOS_Release_Notes.md)

