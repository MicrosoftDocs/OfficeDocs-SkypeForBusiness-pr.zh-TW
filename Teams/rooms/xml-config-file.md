---
title: 遠端系統管理Microsoft Teams 會議室裝置設定
ms.author: czawideh
author: cazawideh
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
description: 遠端系統管理Microsoft Teams 會議室裝置使用的預設設定，包括套用自訂主題和建立主設定檔案。
ms.openlocfilehash: c363dce55df4d9bdcf125492c2ca92b3b20feba7
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125458"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 組態檔遠端系統管理Microsoft Teams 會議室主機設定

本文討論遠端系統管理Microsoft Teams 會議室裝置使用的預設設定，包括套用自訂主題。 討論如何建立主設定檔案，以及如何視需要將它們放在Teams 會議室的討論連結。
  
您可以藉由更新主 XML 檔案並將複本傳送到遠端Teams 會議室裝置，來變更Teams 會議室的預設設定。 
  
## <a name="create-an-xml-configuration-file"></a>建立 XML 組態檔

任何文字編輯器都可以用來建立設定檔案。 **[XML 元素**] 表格說明此範例中顯示的元素SkypeSettings.xml (組態檔) 所需的檔案名。
  
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
  <EnablePublicPreview>false</EnablePublicPreview>
  <NoiseSuppressionDefault>0</NoiseSuppressionDefault>
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
  <EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting> 
  <MainFoRDisplay> 
      <MainFoRDisplayResolution>1920,1080</MainFoRDisplayResolution> 
      <MainFoRDisplayScaling>100</MainFoRDisplayScaling> 
  </MainFoRDisplay> 
  <ExtendedFoRDisplay> 
      <ExtendedFoRDisplayResolution>1920,1080</ExtendedFoRDisplayResolution> 
      <ExtendedFoRDisplayScaling>100</ExtendedFoRDisplayScaling> 
  </ExtendedFoRDisplay>  
</SkypeSettings>
```

如果變數值的類型錯誤、元素順序出錯、元素未被隱藏，或發現另一個錯誤，XML 檔案會 *形成錯誤*。 處理形成不良的 XML 檔案時，會套用到錯誤發生點的設定，然後忽略檔案的其餘部分。 XML 中的任何未知元素都會被忽略。 如果省略參數，則會在裝置上維持不變。 如果參數值無效，則其先前的值會保持不變。
  
**XML 元素**

| 元素                                     | 類型                        | 水準          | 使用                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<SkypeSettings\>                           | 所有元素的容器。 |                | 必填。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<AutoScreenShare\>                         | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，會啟用自動螢幕共用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<HideMeetingName\>                         | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，則會隱藏會議名稱。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<UserAccount\>                             | 容器                   | 第一個&#x2776; | 認證參數的容器。 登入位址、Exchange位址或電子郵件地址通常相同，例如 RainierConf <span></span> @contoso.com。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SkypeSignInAddress\>                      | 字串&#x2777;             |                | 主機 SfB 或Teams裝置帳戶的登入名稱。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ExchangeAddress\>                         | 字串&#x2778;            |                | 主機Exchange裝置帳戶的登入名稱。 如果省略 ExchangeAddress，SkypeSignInAddress 將不會自動重複使用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<DomainUsername\>                          | 字串&#x2777;            |                | 主機裝置的網域和使用者名稱，例如西雅圖\RanierConf。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<Password\>                                | 字串&#x2778;            |                | 密碼參數與商務用 Skype裝置帳戶登入時使用的密碼相同。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ConfigureDomain\>                         | 字串&#x2777;            |                | 您可以列出數個網域，並以逗號分隔。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<ModernAuthEnabled>                        | 布林值&#x2777;            |                | 預設停用。 <br/> <br/>設為 True 時，Microsoft Teams 會議室應用程式只會使用新式驗證來連線至資源，而不會回復到基本驗證。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<TeamsMeetingsEnabled\>                    | 布林值&#x2777;            | 第一個&#x2776; | 預設停用。 <br/> <br/> 如果同時 \<SkypeMeetingsEnabled\> 停用和 \<TeamsMeetingsEnabled\> 停用，XML 檔案會被視為無法形成，但同時啟用這兩個設定是可以接受的。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| \<SfbMeetingEnabled\>                       | 布林值&#x2778;            | 第一個&#x2776; | 預設停用。
| \<IsTeamsDefaultClient>                     | 布林值&#x2777;            | 第一個&#x2776; | 預設啟用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<WebExMeetingsEnabled\>                    | 布林值&#x2777;            | 第一個&#x2776; | 預設停用。 <br/> <br/> 如果為 True，可為 Cisco Webex 會議啟用直接來賓加入體驗。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| \<ZoomMeetingsEnabled\>                     | 布林值&#x2777;            | 第一個&#x2776; | 預設停用。 <br/> <br/> 如果為 True，則啟用縮放會議的直接來賓加入體驗。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<UseCustomInfoForThirdPartyMeetings\>      | 布林值&#x2777;            | 第一個&#x2776; | 預設停用，並使用會議室帳戶資訊加入協力廠商會議。 <br/> <br/> 如果此值設為 True，您必須同時 \<CustomDisplayNameForThirdPartyMeetings\> 指定 ， \<CustomDisplayEmailForThirdPartyMeetings\> 必須加以指定。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<CustomDisplayNameForThirdPartyMeetings\>  | 字串&#x2778;            | 第一個&#x2776; | 指定用來加入協力廠商會議的來賓名稱。 協力廠商服務會在他們的體驗中顯示此資料，且可能會儲存在其服務中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CustomDisplayEmailForThirdPartyMeetings\> | 字串&#x2778;            | 第一個&#x2776; | 指定用來加入協力廠商會議的來賓電子郵件。 協力廠商服務會在他們的體驗中顯示此資料，且可能會儲存在其服務中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BluetoothAdvertisementEnabled>            | 布林值&#x2777;            | 第一個&#x2776; | 預設啟用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<AutoAcceptProximateMeetingInvitations>    | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，會自動接受鄰近式會議。 預設停用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<AutoExitMeetingEnabled>                   | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，如果裝置是會議中最後一個剩餘的參與者，裝置會自動離開會議。  預設停用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<DualScreenMode\>                          | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，則會啟用雙螢幕模式。 否則裝置會使用單螢幕模式。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DuplicateIngestDefault\>                  | 布林值&#x2777;            | 第一個&#x2776; | 如果為 True，內容會在離開會議時以雙螢幕模式顯示在兩個螢幕上。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DisableTeamsAudioSharing\>                | 布林值&#x2777;            | 第一個&#x2776; | 設為 True 以停用會議參與者在 Teams 會議中的 HDMI 音訊共用。 預設值為 False。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<FrontRowEnabled>                          | 布林值&#x2777;            | 第一個&#x2776; | 預設啟用。 如果為 false，則會停用前列。
| \<DefaultFoRExperience>                     | 布林值&#x2777;            | 第一個&#x2776; | 根據預設，圖庫檢視。 [放置 1] 可將預設版面配置從 [圖庫檢視] 變更為 [前列]。
| \<EnablePublicPreview\>                     | 布林值&#x2777;            | 第一個&#x2776; | 預設停用。 如果為 True，則會啟用公開預覽，且使用者可以在啟用的Teams 會議室存取公開預覽中的功能。 如需詳細資訊，請參閱[在 Windows 上公開預覽Microsoft Teams 會議室](../public-preview-doc-updates.md#public-preview-for-microsoft-teams-rooms-on-windows)。 |
| \<NoiseSuppressionDefault\>                 | 布林值&#x2777;            | 第一個&#x2776; | 預設啟用。 將 0 設為停用。 停用不會影響桌面設定，此設定僅適用于Teams會議室帳戶。
| \<CortanaWakewordEnabled\>                  | 布林值&#x2777;            | 第一個&#x2776; | 設為 True 以啟用Cortana喚醒「嗨 Cortana」一詞。 除非您所在的國家或地區支援Cortana服務，且連接的音訊周邊支援Cortana，否則此設定不會有任何作用。 預設值為 False。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<SendLogs\>                                | 容器                   | 第一個&#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<EmailAddressForLogsAndFeedback\>          | 字串&#x2778;            |                | 設定在出現 [提供意見反應] 視窗時，可以傳送記錄檔的選擇性電子郵件地址。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<SendLogsAndFeedback\>                     | 布林值&#x2777;            |                | 如果為 True，記錄會傳送給系統管理員。如果為 false，系統只會傳送意見反應給系統管理員 (，而不會傳) 記錄。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<Devices\>                                 | 容器                   | 第一個&#x2776; | 子項目中連線的音訊裝置名稱與裝置管理員應用程式中列出的值相同。 此設定可能包含目前不存在於系統上的裝置，例如 A/V 裝置目前未連線到主機。 系統會保留個別裝置的設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<MicrophoneForCommunication\>              | 字串&#x2778;            |                | 設定會議中用來做為錄製裝置的麥克風。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SpeakerForCommunication\>                 | 字串&#x2778;            |                | 用來做為會議演講者的裝置。 此設定是用來設定通話中使用的喇叭裝置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<DefaultSpeaker\>                          | 字串&#x2778;            |                | 用來從 HDMI 內充來源播放音訊的裝置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<ContentCameraId>                          | 字串&#x2778;            |                | 定義在會議室中設定的相機實例路徑，以便在會議中共用類比白板內容。 請參閱 [尋找內容相機 USB 實例路徑](#locate-the-content-camera-usb-instance-path)。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<ContentCameraInverted>                    | 布林值&#x2777;            |                | 指定內容相機是否已上下顛倒安裝。 對於支援自動旋轉的內容攝影機，請指定 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<ContentCameraEnhancement>                 | 布林值&#x2777;            |                | 設定為 True (預設) 時，會以數位方式增強內容相機影像：偵測到白板邊緣，並選取適當的縮放、增強筆跡線條，並將在白板上書寫的人變成透明。  <br><br> 如果您打算傳送原始視訊摘要給會議參與者，讓會議參與者在空間中不要使用手寫筆繪製白板，而相機則會用來顯示自黏便箋、海報或其他媒體。                                                                                                                                                                                                                                                                                                                                                                                             |
| \<Theming\>                                 | 容器                   | 第一個&#x2776; | 其中一個可套用 XML 檔案的功能是貴組織的自訂主題。 您可以指定主題名稱、背景影像和色彩。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<ThemeName\>                               | 字串&#x2778;            |                | 用來識別用戶端上的主題。 [主題名稱] 選項為 [預設]、其中一個提供的預設主題或 [自訂]。 <br/>  自訂主題名稱一律使用名稱 *[自訂]*。 用戶端 UI 可以在主機上設定為預設值或其中一個預設值，但系統管理員必須遠端設定自訂主題的使用。 <br/>  預設主題包括： <br/>  預設 <br/>  藍光波 <br/>  數位森林 <br/>  Dreamcatcher <br/>  青瓜 <br/>  Pixel Perfect <br/>  路線 圖 <br/>  日落 <br/>  若要停用目前的主題，請針對 ThemeName 使用「無主題」。                                                                                                                                                                                                                                                                               |
| \<CustomThemeImageUrl\>                     | 字串&#x2778;            |                | 自訂主題是必要的，否則為選用。 僅輸入檔案名。   For more information on the custom theme image, see the [Custom Theme Images](xml-config-file.md#Themes) section.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<CustomThemeColor\>                        | 容器                   |                | Container for the \<RedComponent\> ， \<GreenComponent\> ， and \<BlueComponent\> values. 這些值是必要的，但不會影響主題色彩。 請指定 0-255 之間的任何值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<RedComponent\>                            | 位元組 (0-255)                 |                | 代表紅色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<GreenComponent\>                          | 位元組 (0-255)                 |                | 代表綠色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BlueComponent\>                           | 位元組 (0-255)                 |                | 代表藍色元件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CoordinatedMeetings\>                     | 布林值&#x2777;            | 第一個&#x2776; | 協調會議之組態元素的容器。 此元素有一個屬性：<ul><li><b>啟用</b>判斷是否Teams設定為與其他裝置參與協調會議。</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<TrustedAccounts\>                         | String                      |                | 這是每個Teams會議室裝置的逗號分隔 UPN 清單，或裝置應接受會議加入邀請的Surface Hub，或應該傳送會議加入邀請給哪一個會議加入要求。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<Settings\>                                | 容器                   |                | 協調會議之設定音訊和視訊組態元素的容器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<Audio\>                                   | 布林值&#x2777;            |                | 控制Teams 會議室裝置上的音訊設定。 此元素有兩個屬性：<br><ul><li><b>預設</b> 決定當會議開始時，麥克風會在哪個裝置上作用中。 通常只有一個裝置 (Teams 會議室裝置) 可以將此欄位設定為 `true` ，而其他裝置必須設定此欄位，以避免 `false` 音訊回音和意見反應。</li><li><b>啟用</b> 判斷會議中的參與者是否可以開啟或關閉麥克風。 設為 `false` **Audio 預設** 值的裝置應將此設定設為 `false` ，讓參與者無法意外開啟麥克風並造成音訊回音或意見反應。<p>如果 **音訊預設** 值設為 `true` ，則會忽略 **啟用音訊的** 設定，且參與者可以將麥克風設為靜音或取消靜音。</li></ul>                        |
| \<Video\>                                   | 布林值&#x2777;            |                | 控制Teams 會議室裝置上的視訊設定。 此元素有兩個屬性：<br><ul><li><b>預設</b> 決定會議開始時相機會在哪個裝置上使用。 為獲得最佳體驗，建議您在所有其他裝置都設 `false` 為 `true` 時，只設定Teams 會議室裝置。</li><li><b>啟用</b> 判斷會議中的參與者是否可以開啟或關閉相機。 您可以將此設定在 `true` 活動參與者想要分享不同視訊觀點的任何其他裝置上， (例如參與者正在使用Surface Hub白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將此設定設為 `false` 。<p> 如果 **[視訊] 預設** 值設為 `true` ，則會忽略 **啟用視訊的** 設定，且參與者可以開啟或關閉相機。</li></ul> |
| \<Whiteboard\>                              | 布林值&#x2777;            |                | 控制Teams 會議室裝置上的白板設定。 此元素有兩個屬性：<br><ul><li><b>預設</b> 決定白板會在會議開始時使用哪個裝置。 為獲得最佳體驗，建議您將Teams 會議室裝置設定為 `false` ，並讓您在Surface Hub上使用白板。</li><li><b>啟用</b> 決定會議中的參與者是否可以開啟或關閉白板。 如果您不希望參與者在裝置上開啟或關閉白板，請將此設定設為 `false` 。<p> 如果 **Whiteboard 預設** 設定 `true` 為 ， **啟用白板的** 設定會被忽略，參與者可以開啟或關閉白板。</li></ul>                                                                                                                                                   |
| \<EnableResolutionAndScalingSetting\> | 布林值&#x2777; | 第一個&#x2776; | 預設會停用。 如果您想要變更 [會議室前方] 的解析度和縮放比例，請將它設為 True。 如果為 True，將會套用顯示器解析度和縮放比例設定。 啟用此設定後，此設定會同時影響主 FoR 和延伸 FoR。 |
| \<MainFoRDisplay\> | 容器 | | 如果您的裝置使用單一顯示模式，請使用此容器。<br><br>在雙顯示模式下，會議室 (FoR) 的主要前方是會議) 中時鐘 (離開會議) 和自我預覽視訊 (的畫面。 \<MainFoRDisplayResolution\> 並且 \<MainFoRDisplayScaling\> 一次必須一起設定。 如果您只使用其中一 \<MainFoRDisplayResolution\> 種或 \<MainFoRDisplayScaling\> ，則會忽略。 |
| \<MainFoRDisplayResolution\> | String | | Width、Height (的輸入數值，例如 1920，1080) 。 如果您的 FoR 不支援此功能，則會忽略此設定。|
| \<MainFoRDisplayScaling\> | 數量 | | 縮放比例的輸入數值。 有效的值為建議) 、125、150、175、200、225、250、300、350、400、450 和 500 的 100 (值。 如果您輸入 500 且 FoR 支援最多 300 個，則會設定為 300。|
| \<ExtendedFoRDisplay\> | 容器 | | 在雙顯示模式下，[會議室外延前 (FoR) 是您在會議) 中看到共用內容 (的畫面。  \<ExtendedFoRDisplayResolution\> 並且 \<ExtendedFoRDisplayScaling\> 一次必須一起設定。 如果您只使用其中一 \<ExtendedFoRDisplayResolution\> 種或 \<ExtendedFoRDisplayScaling\> ，則會忽略。 |
| \<ExtendedFoRDisplayResolution\> | String | |例如：1920，1080) Width、Height (的輸入數值。 如果您的 FoR 不支援該值，則會忽略該值。 |
| \<ExtendedFoRDisplayScaling\> | 數量 | | 縮放比例的輸入數值。 有效的值為建議) 、125、150、175、200、225、250、300、350、400、450 和 500 的 100 (值。 如果您輸入 500 且 FoR 支援最多 300 個，則會設定為 300。 |

&#x2776;所有第一層元素都是選用的。 如果省略第一層元素，裝置上的所有子參數都會保持不變。
  
&#x2777;布林值標幟可以是：true、false、0 或 1。 將布林值或數值留白可能會使 XML 呈現錯誤格式，並防止變更設定。
  
&#x2778; 如果字串參數存在且為空白，而空白為有效值，則會在裝置上清除參數。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 設定檔管理主機設定

啟動時，如果Microsoft Teams 會議室主機找到名為 SkypeSettings.xml 位置 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 的 XML 檔案，它會套用 XML 檔案所指示的組態設定，然後刪除 XML 檔案。
  
根據您的企業擁有多少Microsoft Teams 會議室裝置，以及您選擇如何進行設定，有幾種方式可以放置 XML 組態檔。 將檔案推送到主機後，請重新開機以處理設定變更。 成功處理 XML 組態檔後，即會予以刪除。 針對Microsoft Teams 會議室裝置建議的管理方法如下所述：
  
- [設定 Microsoft Teams 會議室 的群組原則](rooms-operations.md#GroupPolicy)
- [使用 PowerShell 遠端系統管理](rooms-operations.md#RemotePS) 及 [設定檔案專案](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

只要您可以使用任何您喜歡的方法來傳輸檔案，並在主機裝置上觸發重新開機，您就可以自由使用。 檔案必須由裝置的本機使用者帳戶讀取、寫入及刪除。 最好是由該使用者擁有，而且擁有完整的許可權。 如果檔案許可權設定不正確，軟體可能無法套用設定、處理成功時無法刪除檔案，甚至可能會當機。
  
## <a name="supported-meeting-modes-app-version-49"></a>支援的會議模式應用程式版本 4.9

**商務用 Skype (預設) 和Microsoft Teams**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>     |   真         |
| \<SfbMeetingEnabled>        |   真         |
| \<IsTeamsDefaultClient>     |   假        |

**商務用 Skype和Microsoft Teams (預設)**

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

**僅限Microsoft Teams**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   真         |
| \<SfbMeetingEnabled>        |   假         |
| \<IsTeamsDefaultClient>     |   真        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>支援的會議模式應用程式版本 4.8 或較低版本

**商務用 Skype (預設) 和Microsoft Teams**

| XML 標記法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   真         |
|  \<IsTeamsDefaultClient>     |   假        |

**商務用 Skype和Microsoft Teams (預設)**

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

自訂主題影像檔案必須放在資料夾中 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 在變數中 \<CustomThemeImageUrl\> 輸入檔案名和副檔名。
  
影像檔應為 3840X1080 圖元，而且必須是下列其中一種檔案格式：jpg、jpeg、png 和 bmp。 如果您的組織想要自訂影像，圖形設計師可以使用 [[自訂主題 Photoshop 範本]](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含各種使用者介面元素相對於主題影像其餘部分的位置，以及主機和顯示器上顯示哪些區域的進一步詳細資料。
  
XML 組態檔必須在裝置啟動時更新，才能辨識主題影像。 處理並刪除新的 XML 檔案後，主題圖形檔就會從目錄中刪除。

## <a name="locate-the-content-camera-usb-instance-path"></a>找出 [內容相機] USB 實例路徑

若要找出實例路徑：

1. 移至Microsoft Teams 會議室主機上的Windows設定。
2. 輸入系統管理員密碼。
3. 在命令提示字元中輸入 `devmgmt.msc` 以顯示裝置管理員。
4. 在 **裝置管理員** 中，查看 **[影像裝置**] 節點並找出內容相機。
5. 以滑鼠右鍵按一下相機，然後開啟 [ **內容]**。
6. 選取 [ **詳細資料] 索** 引標籤，然後在下拉式清單中找出 **[裝置實例路徑** ] 屬性。
7. 顯示的值是要在 XML 組態檔中設定的裝置實例路徑。 在 XML 中指定路徑時，請將安培 (&) 取代為 `&amp;` 。

## <a name="set-front-row-as-the-default-layout"></a>將前列設定為預設版面配置

如果您沒有在 XML 設定中設定聊天室的預設顯示版面配置，預設版面配置會設定為 [圖庫]。 若要將前列視為預設版面配置，請新 ```<DefaultFoRExperience>1</DefaultFoRExperience>``` 增至您的 XML 組態檔。

使用者可以在會議期間使用版面配置選擇器，從預設顯示版面配置切換。

## <a name="turn-off-front-row"></a>關閉前列

前列預設為啟用。 如果您不想讓使用者在特定會議室中使用 Front 列，請關閉 [前列]。 若要這麼做，請新 ```<FrontRowEnabled>false</FrontRowEnabled>``` 增至您的 XML 組態檔。

## <a name="set-front-of-room-scale-and-resolution"></a>設定房間最前面的縮放比例和解析度

若要設定 [會議室前] 顯示器的縮放比例和解析度，請使用容器新 ```<EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting>``` 增至您的 XML 組態檔 `<MainFoRDisplay>` 。 如果您的裝置使用雙顯示器，也包括 `<ExtendedFoRDisplay>` 容器。 

如果您使用單一顯示器將Teams室和 `<MainFoRDisplay>` `<ExtendedFoRDisplay>` 容器同時使用， `<ExtendedFoRDisplay>` 則會忽略容器。 如需詳細資訊，請參閱上面的 XML 和元素表範例。

## <a name="see-also"></a>另請參閱

[內容相機](content-camera.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)

[設定檔案專案](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
