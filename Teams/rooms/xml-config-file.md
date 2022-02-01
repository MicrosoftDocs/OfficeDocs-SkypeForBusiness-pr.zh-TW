---
title: 遠端系統管理Microsoft Teams 會議室裝置設定
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: 遠端系統管理裝置所使用的預設Microsoft Teams 會議室，包括使用自訂主題和建立主設定檔案。
ms.openlocfilehash: fdece0fb7ed554e229a5eef557e1bd2cbf8e4711
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299018"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML Microsoft Teams 會議室遠端系統管理主機設定

本文將討論遠端系統管理裝置所使用的預設Microsoft Teams 會議室設定，包括適用自訂主題。 本文討論如何建立主設定檔案，並連結至如何根據需要將它們放在 Teams 會議室。
  
您可以更新主 XML 檔案Teams 會議室將複本傳送至遠端裝置，Teams 會議室設定。 
  
## <a name="create-an-xml-configuration-file"></a>建立 XML 設定檔

任何文字編輯器都可以用來建立設定檔案。 **XML 元素** 資料表會說明此範例中顯示的元素，SkypeSettings.xml (組) 檔案名。
  
```XML
<SkypeSettings>
  <AutoScreenShare>1</AutoScreenShare>
  <HideMeetingName>1</HideMeetingName>
  <AutoExitMeetingEnabled>true</AutoExitMeetingEnabled>
  <AudioRenderDefaultDeviceVolume>70</AudioRenderDefaultDeviceVolume>
  <AudioRenderCommunicationDeviceVolume>30</AudioRenderCommunicationDeviceVolume>
  <UserAccount>
    <SkypeSignInAddress>username@microsoft.com</SkypeSignInAddress>
    <ExchangeAddress>username@microsoft.com</ExchangeAddress>
    <DomainUsername>domain\username</DomainUsername>
    <Password>Password!</Password>
    <ConfigureDomain>domain1, domain2</ConfigureDomain>
    <ModernAuthEnabled>true</ModernAuthEnabled>
  </UserAccount>
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
  <SfbMeetingEnabled>true</SfbMeetingEnabled>
  <IsTeamsDefaultClient>true</IsTeamsDefaultClient>
  <WebExMeetingsEnabled>true</WebExMeetingsEnabled>
  <ZoomMeetingsEnabled>true</ZoomMeetingsEnabled>
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@microsoft.com</CustomDisplayEmailForThirdPartyMeetings>
  <BluetoothAdvertisementEnabled>false</BluetoothAdvertisementEnabled>
  <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
  <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
  <DualScreenMode>0</DualScreenMode>
  <DuplicateIngestDefault>true</DuplicateIngestDefault>
  <DisableTeamsAudioSharing>true</DisableTeamsAudioSharing>
  <FrontRowEnabled>true</FrontRowEnabled>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <SendLogs>
    <EmailAddressForLogsAndFeedback>username@microsoft.com</EmailAddressForLogsAndFeedback>
    <SendLogsAndFeedback>True</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
    <MicrophoneForCommunication>Device1</MicrophoneForCommunication>
    <SpeakerForCommunication>DeviceX</SpeakerForCommunication>
    <DefaultSpeaker>DeviceX</DefaultSpeaker>
    <ContentCameraId>Camera1</ContentCameraId>
    <ContentCameraEnhancement>true</ContentCameraEnhancement>
    <ContentCameraInverted>false</ContentCameraInverted>
  </Devices>
  <Theming>
       <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>file name</CustomThemeImageUrl>
       <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
       </CustomThemeColor>
  </Theming>
  <CoordinatedMeetings enabled="true">
    <TrustedAccounts>username1@microsoft.com,username2@contoso.com</TrustedAccounts>
    <Settings>
      <Audio default="true" enabled="true"/>
      <Video default="true" enabled="true"/>
      <Whiteboard default="true" enabled="true"/>
    </Settings>
  </CoordinatedMeetings>
</SkypeSettings>
```

如果變數值的類型錯誤、元素順序不齊、元素未取消取消集合，或找到另一個錯誤，XML 檔案會 *不正確地形成*。 處理格式錯誤的 XML 檔案時，會採用錯誤發生點前所找到的設定，然後忽略檔案的其餘部分。 XML 中任何未知的元素會被忽略。 如果省略參數，該參數在裝置上會維持不變。 如果參數值無效，其先前值會維持不變。
  
**XML 元素**

| 元素                                     | 類型                        | 水準          | 使用                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<SkypeSettings\>                           | 所有元素的容器。 |                | 必填。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<AutoScreenShare\>                         | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，則啟用自動螢幕畫面共用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<HideMeetingName\>                         | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，會議名稱會隱藏。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<UserAccount\>                             | 容器                   | 第一&#x2776; | 用於認證參數的容器。 登錄位址、Exchange位址或電子郵件地址通常相同，例如 RainierConf <span></span> @contoso.com。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SkypeSignInAddress\>                      | 字串&#x2777;             |                | 主機 SfB 或裝置帳戶Teams名稱。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ExchangeAddress\>                         | 字串&#x2778;            |                | 主機的登錄名稱Exchange裝置帳戶。 如果省略 ExchangeAddress，SkypeSignInAddress 將不會自動重複使用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<DomainUsername\>                          | 字串&#x2777;            |                | 主機裝置網域和使用者名稱，例如西雅圖\RanierConf。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<Password\>                                | 字串&#x2778;            |                | 密碼參數與裝置帳戶商務用 Skype密碼相同。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ConfigureDomain\>                         | 字串&#x2777;            |                | 您可以列出數個網域，以逗號分隔。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<ModernAuthEnabled>                        | 布林值&#x2777;            |                | 預設為停用。 <br/> <br/>當設為 true 時，Microsoft Teams 會議室應用程式只會使用新式驗證來連接資源，而且不會回到基本驗證。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<TeamsMeetingsEnabled\>                    | 布林值&#x2777;            | 第一&#x2776; | 預設為停用。 <br/> <br/> 如果兩者同時處於停用狀態 \<SkypeMeetingsEnabled\> \<TeamsMeetingsEnabled\> ，XML 檔案會被視為格式不正確，但同時啟用這兩個設定是可接受的。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| \<SfbMeetingEnabled\>                       | 布林值&#x2778;            | 第一&#x2776; | 預設為停用。
| \<IsTeamsDefaultClient>                     | 布林值&#x2777;            | 第一&#x2776; | 預設為啟用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<WebExMeetingsEnabled\>                    | 布林值&#x2777;            | 第一&#x2776; | 預設為停用。 <br/> <br/> 如果為 True，請為 Cisco Webex 會議啟用直接來賓加入體驗。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| \<ZoomMeetingsEnabled\>                     | 布林值&#x2777;            | 第一&#x2776; | 預設為停用。 <br/> <br/> 如果為 True，則啟用縮放會議的直接來賓加入體驗。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<UseCustomInfoForThirdPartyMeetings\>      | 布林值&#x2777;            | 第一&#x2776; | 預設為停用，並使用會議室帳戶資訊加入協力廠商會議。 <br/> <br/> 如果此值設為 true，您必須指定 \<CustomDisplayNameForThirdPartyMeetings\> 兩者， \<CustomDisplayEmailForThirdPartyMeetings\> 必須指定 。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<CustomDisplayNameForThirdPartyMeetings\>  | 字串&#x2778;            | 第一&#x2776; | 指定用來加入協力廠商會議的來賓名稱。 協力廠商服務會以他們的體驗顯示這些資料，並可能儲存在其服務中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CustomDisplayEmailForThirdPartyMeetings\> | 字串&#x2778;            | 第一&#x2776; | 指定用來加入協力廠商會議的來賓電子郵件。 協力廠商服務會以他們的體驗顯示這些資料，並可能儲存在其服務中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BluetoothAdvertisementEnabled>            | 布林值&#x2777;            | 第一&#x2776; | 預設為啟用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<AutoAcceptProximateMeetingInvitations>    | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，系統會自動接受鄰近型會議。 預設為停用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<AutoExitMeetingEnabled>                   | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，如果裝置是會議的最後一位參與者，則裝置會自動離開會議。  預設為停用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<DualScreenMode\>                          | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，則啟用雙螢幕模式。 否則裝置會使用單一螢幕模式。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DuplicateIngestDefault\>                  | 布林值&#x2777;            | 第一&#x2776; | 如果為 True，當會議結束後，內容會以雙螢幕模式顯示在兩個畫面上。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DisableTeamsAudioSharing\>                | 布林值&#x2777;            | 第一&#x2776; | 設為 true 以停用會議參與者的 HDMI 音訊Teams共用。 預設值為 False。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<FrontRowEnabled>                          | 布林值&#x2777;            | 第一&#x2776; | 預設為啟用。 如果為 False，會停用前列。
| \<DefaultFoRExperience>                     | 布林值&#x2777;            | 第一&#x2776; | 根據預設，圖庫視圖。 將 1 從圖庫視圖變更為前排的預設版面配置。
| \<CortanaWakewordEnabled\>                  | 布林值&#x2777;            | 第一&#x2776; | 設為 true 以啟用Cortana「嗨Cortana」。 除非您的國家/地區支援 Cortana服務，而且您連接的音訊周邊支援Cortana。 預設值為 False。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<SendLogs\>                                | 容器                   | 第一&#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<EmailAddressForLogsAndFeedback\>          | 字串&#x2778;            |                | 設定當出現「提供意見回饋」視窗時，記錄可以寄到的選擇性電子郵件地址。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<SendLogsAndFeedback\>                     | 布林值&#x2777;            |                | 如果為 True，記錄會寄給系統管理員。如果為 false，系統只會將意見 (系統記錄) 。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<Devices\>                                 | 容器                   | 第一&#x2776; | 子項目中已連接的音訊裝置名稱與 Device Manager App 中列出的值相同。 此組配置可以包含目前不存在於系統上的裝置，例如目前未連接到主機的 A/V 裝置。 系統將會針對各個裝置保留此組組。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<MicrophoneForCommunication\>              | 字串&#x2778;            |                | 設定在會議中使用的麥克風作為錄製裝置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SpeakerForCommunication\>                 | 字串&#x2778;            |                | 要作為會議演講者的裝置。 此設定用來設定通話中使用的喇叭裝置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<DefaultSpeaker\>                          | 字串&#x2778;            |                | 用來從 HDMI 輸入來源播放音訊的裝置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<ContentCameraId>                          | 字串&#x2778;            |                | 定義會議室中已配置的攝影機實例路徑，以共用會議中的類比白板內容。 請參閱 [尋找內容相機 USB 實例路徑](#locate-the-content-camera-usb-instance-path)。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<ContentCameraInverted>                    | 布林值&#x2777;            |                | 指定內容攝影機是否由上而下安裝。 對於支援自動旋轉的內容攝影機，請指定 False。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<ContentCameraEnhancement>                 | 布林值&#x2777;            |                | 當設為 true (預設) 時，內容相機影像會以數位方式增強：偵測白板邊緣並選取適當的縮放、加強筆墨線條，以及讓在白板上書寫的人保持透明。  <br><br> 如果您打算傳送原始視音訊給會議參與者，讓會議參與者使用筆繪製白板，而是使用相機來顯示自黏便箋、海報或其他媒體，則設為 False。                                                                                                                                                                                                                                                                                                                                                                                             |
| \<Theming\>                                 | 容器                   | 第一&#x2776; | 您可以與 XML 檔案一起使用的功能之一是貴組織的自訂主題。 您可以指定主題名稱、背景影像和色彩。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<ThemeName\>                               | 字串&#x2778;            |                | 用來識別用戶端上的主題。 主題名稱選項為預設、其中一個提供的預設主題或自訂。 <br/>  自訂主題名稱一直使用名稱 *自訂*。 用戶端 UI 可以在主機上設定為預設或其中一個預設，但自訂主題的使用必須由系統管理員遠端設定。 <br/>  預設定的主題包括： <br/>  預設 <br/>  藍色波 <br/>  數位森林 <br/>  Dreamcatcher <br/>  利卡德 <br/>  圖元完美 <br/>  路線 圖 <br/>  日落 <br/>  若要停用目前的主題，請使用主題名稱的 「無主題」。                                                                                                                                                                                                                                                                               |
| \<CustomThemeImageUrl\>                     | 字串&#x2778;            |                | 自訂主題為必填專案，否則為選擇性。 僅輸入檔案名。   有關自訂主題圖像的資訊，請參閱自訂 [主題影像](xml-config-file.md#Themes) 一節。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<CustomThemeColor\>                        | 容器                   |                | \<RedComponent\>和 值的 \<GreenComponent\> \<BlueComponent\> 容器。 這些值為必填專案，但不會影響主題色彩。 請指定 0-255 之間的任何值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<RedComponent\>                            | 位元組 (0-255)                 |                | 代表紅色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<GreenComponent\>                          | 位元組 (0-255)                 |                | 代表綠色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BlueComponent\>                           | 位元組 (0-255)                 |                | 代表藍色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CoordinatedMeetings\>                     | 布林值&#x2777;            | 第一&#x2776; | 用於協調會議之組組元素的容器。 此元素有一個屬性：<ul><li><b>啟用</b>判斷Teams是否已配置為與其他裝置參與協調會議。</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<TrustedAccounts\>                         | String                      |                | 這是每個 Teams 會議室裝置或 Surface Hub 裝置應接受會議加入邀請，或應寄到哪些會議加入邀請的 UPN 逗號分隔清單。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<Settings\>                                | 容器                   |                | 用於協調會議之組調音訊和視音訊組組元素的容器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<Audio\>                                   | 布林值&#x2777;            |                | 控制裝置上的音訊Teams 會議室。 此元素具有兩個屬性：<br><ul><li><b>預設</b> 決定會議開始時，麥克風會位於哪個裝置上。 只有一 (裝置Teams 會議室裝置) `true` `false` 可以設定此欄位，而其他裝置必須設定此欄位以避免音訊回音和意見回應。</li><li><b>啟用</b> 決定會議參與者是否可以開啟或關閉麥克風。 設定為 **音訊** `false` `false` 預設值的裝置應設定此設定，讓參與者不會不小心開啟麥克風，並造成音訊回音或意見回應。<p>如果 **音訊預設值** 設定為 `true` ，則啟用 **音訊** 的設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。</li></ul>                        |
| \<Video\>                                   | 布林值&#x2777;            |                | 控制裝置上的視Teams 會議室組。 此元素具有兩個屬性：<br><ul><li><b>預設</b> 決定會議開始時相機會使用哪個裝置。 為了獲得最佳體驗，我們建議您只將Teams 會議室設定 `true` 為 ，而所有其他裝置都設為 `false` 。</li><li><b>啟用</b> 決定會議參與者是否可以開啟或關閉相機。 您可以在活動 `true` 參與者想要共用不同視 (，例如參與者使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將其設定為 `false` 。<p> 如果 **視音訊預設值** 設為 `true` ，則啟用 **視** 音訊的設定會被忽略，參與者可以開啟或關閉相機。</li></ul> |
| \<Whiteboard\>                              | 布林值&#x2777;            |                | 控制裝置上的白板Teams 會議室。 此元素具有兩個屬性：<br><ul><li><b>預設</b> 決定會議開始時白板會位於哪個裝置上。 為了獲得最佳體驗， `false` 建議您將Teams 會議室設定為，且在白板上Surface Hub。</li><li><b>啟用</b> 決定會議參與者是否可以開啟或關閉白板。 如果您不希望參與者在裝置上開啟或關閉白板，請將其設定為 `false` 。<p> 如果 **Whiteboard 預設** 設定為 `true` ，系統會忽略啟用 **Whiteboard** 的設定，參與者可以開啟或關閉白板。</li></ul>                                                                                                                                                   |

&#x2776;所有第一層元素都是選擇性的。 如果省略第一層元素，其所有子參數在裝置上維持不變。
  
&#x2777;布林值標號可以是：true、false、0 或 1。 將布林值或數值留白，會使 XML 格式錯誤，並防止變更設定。
  
&#x2778;如果字串參數存在且為空白，而 empty 為有效值，則參數會清除在裝置上。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 設定檔管理主控台設定

啟動時，Microsoft Teams 會議室主機找到名為 SkypeSettings.xml `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 的 XML 檔案，它會使用 XML 檔案所指示的設定設定，然後刪除 XML 檔案。
  
根據企業Microsoft Teams 會議室裝置數，以及您選擇如何管理這些裝置來設定，有幾種方法可以放置 XML 設定檔。 將檔案推送到主機後，請重新開機以處理組組變更。 XML 設定檔在成功處理之後會刪除。 以下將討論Microsoft Teams 會議室裝置的建議管理方法：
  
- [為使用者群組原則Microsoft Teams 會議室](rooms-operations.md#GroupPolicy)
- [使用 PowerShell 和](rooms-operations.md#RemotePS)[設定檔案專案的遠端系統管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

您可以隨意使用任何您喜歡的方法，只要能使用它來傳輸檔案，並觸發主機裝置上的重新開機。 檔案必須可讀取、可寫入，而且裝置的本地使用者帳戶必須能夠刪除。 最好是由該使用者擁有，並擁有授予該使用者的完整許可權。 如果檔案許可權未正確設定，軟體可能無法套用設定，可能無法在成功處理時刪除檔案，甚至可能會當機。
  
## <a name="supported-meeting-modes-app-version-49"></a>支援的會議模式 App 版本 4.9

**商務用 Skype (預設) Microsoft Teams**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>     |   真         |
| \<SfbMeetingEnabled>        |   真         |
| \<IsTeamsDefaultClient>     |   假        |

**商務用 Skype Microsoft Teams (預設)**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   真         |
| \<SfbMeetingEnabled>        |   真         |
| \<IsTeamsDefaultClient>     |   真        |

**僅商務用 Skype**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   假         |
| \<SfbMeetingEnabled>        |   真         |
| \<IsTeamsDefaultClient>     |   假        |

**Microsoft Teams只**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   真         |
| \<SfbMeetingEnabled>        |   假         |
| \<IsTeamsDefaultClient>     |   真        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>支援的會議模式 App 版本 4.8 或更新版本

**商務用 Skype (預設) Microsoft Teams**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   真         |
|  \<IsTeamsDefaultClient>     |   假        |

**商務用 Skype Microsoft Teams (預設)**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   真         |
|  \<IsTeamsDefaultClient>     |   真         |

**僅商務用 Skype**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   假         |
|  \<IsTeamsDefaultClient>     |   假         |

## <a name="custom-theme-images"></a>自訂主題影像

<a name="Themes"> </a>

自訂主題圖像檔案必須放在資料夾中 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 在變數中輸入檔案名和副檔名 \<CustomThemeImageUrl\> 。
  
影像檔案應精確為 3840X1080 圖元，且必須是下列其中一種檔案格式：jpg、jpeg、png 和 bmp。 如果貴組織想要自訂影像，圖形設計師可以使用自訂 [主題 Photoshop 範本](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含其他詳細資料，說明各種使用者介面元素相對於主題影像的其餘部分，以及主機和顯示器上顯示的區域。
  
XML 設定檔必須在裝置啟動時更新，以識別主題影像。 處理並刪除新的 XML 檔案後，主題圖形檔案會從目錄中刪除。

## <a name="locate-the-content-camera-usb-instance-path"></a>找出內容相機 USB 實例路徑

若要尋找實例路徑：

1. 請前往Windows主控台上的Microsoft Teams 會議室設定。
2. 輸入系統管理員密碼。
3. 從命令提示符輸入 `devmgmt.msc` 以啟動 Device Manager。
4. 在 **Device Manager** 中，查看影像 **裝置節點** 並找出內容攝影機。
5. 以滑鼠右鍵按一下相機，然後開啟 **[屬性**。
6. Select the **Details** tab, and locate the **Device instance path** property in the drop-down.
7. 顯示的值是在 XML 設定檔中設定之裝置實例路徑。 在 XML 中指定路徑時，請將 (& 和 (&) 取代 `&amp;` 為 。

## <a name="set-front-row-as-the-default-layout"></a>將前列設為預設版面配置

如果您沒有在 XML 設定中設定會議室的預設顯示版面配置，預設版面配置會設定為圖庫。 若要將前列視為預設版面配置，請新增 ```<DefaultFoRExperience>1</DefaultFoRExperience>``` 到 XML 設定檔。

在調整期間，使用者可以使用版面配置選擇器，從預設顯示版面配置切換。

## <a name="turn-off-front-row"></a>關閉前列

預設會啟用前列。 如果您不希望讓使用者在特定聊天室使用前排，請關閉前列。 若要這麼做，請新增 ```<FrontRowEnabled>false</FrontRowEnabled>``` 到 XML 設定檔。

## <a name="see-also"></a>另請參閱

[內容相機](content-camera.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[設定檔案專案](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
