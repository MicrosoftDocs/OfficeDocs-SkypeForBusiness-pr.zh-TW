---
title: 使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
description: 本文將討論 Microsoft 團隊聊天室裝置所使用的預設設定的遠端系統管理，包括套用自訂主題。
ms.openlocfilehash: e33934dcabc420b7e84886f0301c343f5caf333a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827393"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定

本文將討論 Microsoft 團隊聊天室裝置所使用的預設設定的遠端系統管理，包括套用自訂主題。 本文討論如何建立主設定檔案，以及在遠端受管理的裝置上，如何根據需要將這些檔案放置到討論區的連結。
  
您可以透過更新主 XML 檔案並將複本傳送到受管理的主控台，來變更遠端系統管理裝置的預設設定。 您也可以使用 XML 設定檔，在 Microsoft 團隊聊天室主控台上實現自訂主題。
  
## <a name="create-an-xml-configuration-file"></a>建立 XML 設定檔

任何文字編輯器都可以用來建立設定檔。 **Xml 元素**表格說明此範例 SkypeSettings （必要檔案名）設定檔中顯示的元素。
  
```XML
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
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
</SkypeSettings>
```

如果變數值的類型錯誤，元素沒有順序、元素未閉合，或是發現其他錯誤，則 XML 檔案的*格式*不正確。 在處理格式不正確的 XML 檔案時，會套用到錯誤發生位置的設定，然後略過檔案的其餘部分。 XML 中的任何未知元素都會被忽略。 如果省略某個參數，則會在裝置上保持不變。 如果參數值無效，則其前一個值會保持不變。
  
**XML 元素**

|元件|類型|層級|用法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |所有元素的容器。 ||必填。 |
| \<AutoScreenShare\>  |布林值 &#x2777;  |第一 &#x2776;  | 如果為 true，則會啟用自動螢幕共用。  |
|\<HideMeetingName\> |布林值 &#x2777;  |第一 &#x2776;  |如果為 true，會議名稱就會隱藏。 |
|\<UserAccount\> |包裝箱 |第一 &#x2776;  |認證參數的容器。 [登入位址]、[Exchange 位址] 或 [電子郵件地址] 通常相同，<span></span>例如 [RanierConf @contoso .com]。 |
|\<SkypeMeetingsEnabled\>  |布林值 &#x2777;  |第一 &#x2776;  |預設為啟用。 |
|\<SkypeSignInAddress\> |字串 &#x2778;  ||主機的 SfB 或團隊裝置帳戶的登入名稱。 |
|\<ExchangeAddress\> |字串 &#x2778;  ||主機 Exchange 裝置帳戶的登入名稱。 如果省略 ExchangeAddress，則不會自動重複使用 SkypeSignInAddress。 |
|\<DomainUsername\> |字串 &#x2778;  ||主控台裝置的網域和使用者名稱，例如 Seattle\RanierConf。 |
|\<口令\> |字串3  || 密碼參數就是商務用 Skype 裝置帳戶登入所用的密碼。  |
| \<ConfigureDomain\>  |字串 &#x2778;  ||您可以列出數個網域，並以逗號分隔。 |
|\<TeamsMeetingsEnabled\> |布林值 &#x2777;  |第一 &#x2776;  |預設為停用。 <br/> <br/> 如果\<SkypeMeetingsEnabled\>和\<TEAMSMEETINGSENABLED\>都停用，則 XML 檔案會被視為錯誤的格式，但同時啟用這兩個設定。 |
|\<IsTeamsDefaultClient> |布林值 &#x2777;  |第一 &#x2776;  |預設為停用。 |
|\<BluetoothAdvertisementEnabled> |布林值 &#x2777;  |第一 &#x2776;  |預設為啟用。 |
|\<DualScreenMode\>  |布林值 &#x2777;  |第一 &#x2776;  |如果為 true，則會啟用雙螢幕模式。 否則，裝置會使用單一畫面模式。 |
|\<SendLogs\> |包裝箱 |第一 &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\> |字串 &#x2778;  || 設定當 [提供意見反應] 視窗出現時，可以傳送記錄的選擇性電子郵件地址。 |
|\<SendLogsAndFeedback\> |布林值 &#x2777;  || 如果為 true，則會將記錄傳送給系統管理員。如果是 false，則只會傳送意見反應給系統管理員（而非記錄）。  |
| \<裝置\>  |包裝箱 |第一 &#x2776;  | 子項目中連接的音訊裝置名稱與 [裝置管理器] 應用程式中所列的值相同。 此設定可以包含目前不存在於系統中的裝置，例如目前未連線到主機的 A/V 裝置。 該設定將會保留給個別裝置使用。  |
|\<MicrophoneForCommunication\> |字串 &#x2778;  ||設定在會議中用來做為錄製裝置的麥克風。 |
|\<SpeakerForCommunication\> |字串 &#x2778;  ||要作為會議演講者使用的裝置。 這個設定是用來設定通話中使用的喇叭裝置。 |
|\<DefaultSpeaker\> |字串 &#x2778;  ||要用來從 HDMI 攝取來源播放音訊的裝置。 |
|\<ContentCameraId>  | 字串 &#x2778;  | | 定義會議室中設定的相機實例路徑，在會議中共用模擬白板內容。 請參閱[找出內容相機 USB 實例路徑](#locate-the-content-camera-usb-instance-path)。|
|\<ContentCameraInverted>  | 布林值 &#x2777; | | 指定是否將 [內容相機] 實際安裝為倒置。 針對支援自動旋轉的內容攝影機，請指定 false。 |
|\<ContentCameraEnhancement>  | 布林值 &#x2777; | |當設定為 true （預設值）時，會以數位加強內容相機影像：已偵測到白板邊緣，且已選取適當的縮放比例，手寫線已增強，且在白板上撰寫的人員則變成透明。  <br><br> 如果您想要將原始影片摘要傳送給會議參與者，以取得不使用手寫筆繪製白板的空間，而是使用相機來顯示粘滯筆記、海報或其他媒體，請將它設為 false。  |
| \<主題\>  |包裝箱 |第一 &#x2776;  |可以在 XML 檔案中套用的其中一個功能，就是貴組織的自訂主題。 您可以指定 [主題名稱]、[背景圖像] 和 [色彩]。 |
|\<ThemeName\> |字串 &#x2778;  || 用來識別用戶端上的主題。 [主題名稱] 選項為 [預設值]、[提供的其中一個預設主題] 或 [自訂]。 <br/>  自訂主題名稱總是使用 [*自訂*]。 用戶端 UI 可以在主控台上設定為預設或其中一個預設，但使用自訂主題必須由系統管理員進行遠端設定。 <br/>  預設主題包括： <br/>  設置 <br/>  藍波 <br/>  數位目錄林 <br/>  Dreamcatcher <br/>  Limeade <br/>  圖元完美 <br/>  之中 <br/>  斜 <br/>  若要停用目前的主題，請使用「無主題」進行 ThemeName。  |
|\<CustomThemeImageUrl\> |字串 &#x2778;  ||對於自訂主題是必要的，請選用其他選項。 只輸入檔案名。   |如需自訂主題圖像的詳細資訊，請參閱[自訂主題影像](xml-config-file.md#Themes)區段。
|\<CustomThemeColor\> |包裝箱 ||[ \<RedComponent\>]、 \<[GreenComponent\>] 和\<[\> BlueComponent] 值的容器。 這些值是自訂主題所必需的。 |
|\<RedComponent\> |Byte （0-255） ||代表紅色色彩分量。 |
|\<GreenComponent\> |Byte （0-255） ||代表綠色色彩分量。 |
|\<BlueComponent\> |Byte （0-255） ||代表藍色色彩分量。 |
| | | |

&#x2776; 所有的第一層元素都是選用的。 如果省略第一層元素，則其所有子參數在裝置上保持不變。
  
&#x2777; 布林值標誌可以是： true、false、0或1。 如果將布林值或數值保留空白，可能會轉譯 XML 格式不正確，並防止變更設定。
  
&#x2778; 如果字串參數存在且為空白，而空是有效的值，則會在裝置上清除該參數。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 設定檔管理主控台設定

在啟動時，如果 Microsoft [團隊聊天室] 主控台找到名為 SkypeSettings 的 XML 檔案`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`，則會套用 xml 檔案指示的設定設定，然後刪除 xml 檔案。
  
根據您的企業有多少 Microsoft 團隊房間裝置以及您選擇的管理方式來進行設定，有幾種方式可以放置 XML 設定檔。 將檔案推送到主控台之後，請重新開機該檔案以處理設定變更。 在成功處理 XML 設定檔之後，就會刪除該檔案。 Microsoft 團隊會議室裝置建議的管理方法將在下列專案中討論：
  
- [為 Microsoft 團隊聊天室設定群組原則](rooms-operations.md#GroupPolicy)
- [使用 PowerShell 進行遠端系統管理](rooms-operations.md#RemotePS)並[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

您可以隨意使用任何您喜歡的方法，只要您使用它來傳輸檔案，然後在主控台裝置上觸發重新開機。 該檔案必須是裝置的本機使用者帳戶可供閱讀、可寫入且可刪除的檔案。 最好是由該使用者所擁有且擁有完整許可權。 如果檔案許可權設定不正確，軟體可能無法套用這些設定、無法在成功處理後刪除檔案，甚至可能會造成損毀。
  
## <a name="custom-theme-images"></a>自訂主題圖像

<a name="Themes"> </a>

自訂主題圖像檔案必須放在`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`資料夾中。 在\<CustomThemeImageUrl\>變數中輸入檔案名和副檔名。
  
Image 檔案應該是完全3840X1080 的圖元，且必須是下列其中一種檔案格式： jpg、jpeg、png 和 bmp。 如果您的組織想要自訂影像，圖形設計工具可以使用 [[自訂主題 Photoshop] 範本](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含有關不同的使用者介面元素相對於其他主題圖像的位置，以及哪些區域出現在主控台和顯示器上的詳細資訊。
  
XML 設定檔必須在裝置啟動時更新，才能辨識主題影像。 處理並刪除新的 XML 檔案之後，主題圖形檔案就會從目錄中刪除。
  
## <a name="locate-the-content-camera-usb-instance-path"></a>找出內容相機 USB 實例路徑

若要找出實例路徑：

1. 移至 Microsoft [團隊聊天室] 主控台上的 [Windows 設定]。
2. 輸入管理員密碼。
3. 在命令提示字元中， `devmgmt.msc`輸入以顯示 [裝置管理器]。
4. 在 [**裝置管理器**] 中，查看 [**影像裝置**] 節點並找出 [內容相機]。
5. 以滑鼠右鍵按一下相機，然後開啟 [**屬性**]。
6. 選取 [**詳細資料**] 索引標籤，然後找出下拉式清單中的 [**裝置實例路徑**] 屬性。
7. 顯示的值是要在 XML 設定檔中設定的裝置實例路徑。 在 XML 中指定路徑時，請以 [&] 取代 & `&amp;`符號（&）。

## <a name="see-also"></a>另請參閱

[內容相機](content-camera.md)

[管理 Microsoft 團隊聊天室](rooms-manage.md)

[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
