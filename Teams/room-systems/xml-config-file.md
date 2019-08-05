---
title: 使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: 本文將討論 Microsoft 團隊聊天室裝置所使用的預設設定的遠端系統管理, 包括套用自訂主題。
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182454"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定
 
本文將討論 Microsoft 團隊聊天室裝置所使用的預設設定的遠端系統管理, 包括套用自訂主題。
  
更新主版 XML 檔案並將複本傳送到您管理的主控台, 就能讓您變更遠端受管理裝置的預設設定。 本文將說明如何建立此類檔案, 以及在遠端受管理的裝置上, 如何根據需要將這些檔案放置到討論區的連結。 您也可以使用這個方法, 在 Microsoft 團隊聊天室主控台上實現自訂主題。 
  
## <a name="creating-an-xml-configuration-file"></a>建立 XML 設定檔

下表說明此範例 SkypeSettings 中顯示的元素 (這是必要的檔案名) 設定檔。 
  
```
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
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

如果 XML 檔案的格式不正確 (例如, 變數值的類型不正確、元素沒有順序、元素沒有閉合等等), 則會在處理期間忽略指向找到的錯誤所在位置的設定, 然後在處理期間忽視檔案的其餘部分。 XML 中的任何未知元素都會被忽略。 如果省略某個參數, 則會在裝置上保持不變。 如果參數的值無效, 則其前一個值會保持不變。
  
**XML 元素**
 
|元件|類型|層級|用法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |所有元素的容器。   ||必填。   |
| \<AutoScreenShare\>  |布林值 &#x2777;  |第一 &#x2776;  | 如果為 true, 則會啟用自動螢幕共用。  |
|\<HideMeetingName\>   |布林值 &#x2777;  |第一 &#x2776;  |如果為 true, 會議名稱就會隱藏。   |
|\<UserAccount\>   |包裝箱   |第一 &#x2776;  |認證參數的容器。   [登入位址]、[Exchange 位址] 或 [電子郵件地址] 通常相同,<span></span>例如 [RanierConf @contoso .com]。   |
|\<SkypeMeetingsEnabled\>  |布林值 &#x2777;  |第一 &#x2776;  |預設為啟用。   |
|\<SkypeSignInAddress\>   |字串 &#x2778;  ||主機商務用 Skype 裝置帳戶的登入名稱。   |
|\<ExchangeAddress\>   |字串 &#x2778;  ||主機 Exchange 裝置帳戶的登入名稱。   如果省略 ExchangeAddress, SkypeSignInAddress 將不會自動重複使用。   |
|\<DomainUsername\>   |字串 &#x2778;  ||主控台裝置的網域和使用者名稱, 例如 Seattle\RanierConf。   |
|\<口令\>   |字串3  || 密碼參數就是商務用 Skype 裝置帳戶登入所用的密碼。  |
| \<ConfigureDomain\>  |字串 &#x2778;  ||您可以列出數個網域, 並以逗號分隔。   |
|\<TeamsMeetingsEnabled\>   |布林值 &#x2777;  |第一 &#x2776;  |預設為停用。 <br/> <br/> 如果\<SkypeMeetingsEnabled\>和\<TEAMSMEETINGSENABLED\>都停用, 則 XML 檔案會被視為錯誤的格式, 但同時啟用這兩個設定。   |
|\<IsTeamsDefaultClient> |布林值 &#x2777;  |第一 &#x2776;  |預設為停用。 |
|\<BluetoothAdvertisementEnabled> |布林值 &#x2777;  |第一 &#x2776;  |預設為啟用。 |
|\<DualScreenMode\>  |布林值 &#x2777;  |第一 &#x2776;  |如果為 true, 則會啟用雙螢幕模式。 否則, 裝置將會使用單一螢幕模式。   |
|\<SendLogs\>   |包裝箱   |第一 &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |字串 &#x2778;  ||此選項會設定在 [提供意見反應] 視窗出現時, 記錄可以傳送至的電子郵件地址。   |
|\<SendLogsAndFeedback\>   |布林值 &#x2777;  || 如果為 true, 則會將記錄傳送給系統管理員。如果是 false, 則只會傳送意見反應給系統管理員 (而非記錄)。  |
| \<台\>  |包裝箱   |第一 &#x2776;  | 子項目中連接的音訊裝置名稱與 [裝置管理器] 應用程式中所列的值相同。 此設定可以包含目前不存在於系統中的裝置, 例如目前未連線到主機的 A/V 裝置。 該設定將會保留給個別裝置使用。  |
|\<MicrophoneForCommunication\>   |字串 &#x2778;  ||設定將在會議中用來做為錄製裝置的麥克風。   |
|\<SpeakerForCommunication\>   |字串 &#x2778;  ||要作為會議演講者使用的裝置。 這個設定是用來設定在通話中聆聽音訊時所要使用的喇叭裝置。   |
|\<DefaultSpeaker\>   |字串 &#x2778;  ||要用來從 HDMI 攝取來源播放音訊的裝置。   |
| \<主題\>  |包裝箱   |第一 &#x2776;  |您可以使用 XML 檔案來套用的其中一個功能, 就是貴組織的自訂主題。 您可以指定 [主題名稱]、[背景圖像] 和 [色彩]。   |
|\<ThemeName\>   |字串 &#x2778;  || 用來識別用戶端上的主題。 [主題名稱] 選項為 [預設值]、[提供的其中一個預設主題] 或 [自訂]。 <br/>  自訂主題名稱應該總是使用*自訂*的名稱。 用戶端 UI 可以在主控台上設定為預設或其中一個預設, 但是必須由系統管理員來遠端設定您的自訂主題。 <br/>  預設主題包括: <br/>  設置 <br/>  藍波 <br/>  數位目錄林 <br/>  Dreamcatcher <br/>  Limeade <br/>  圖元完美 <br/>  之中 <br/>  斜 <br/>  若要停用目前的主題, 請使用「無主題」進行 ThemeName。  |
|\<CustomThemeImageUrl\>   |字串 &#x2778;  ||如果使用自訂主題, 則為必要, 否則則為選用。 如需自訂主題圖像的詳細資料, 請參閱下方的[自訂主題影像](xml-config-file.md#Themes)一節。  |
|\<CustomThemeColor\>   |包裝箱   ||[ \<RedComponent\>]、 \<[GreenComponent\>] 和\<[\> BlueComponent] 值的容器。 如果使用自訂主題, 這些值就是必要的。   |
|\<RedComponent\>   |Byte (0-255)   ||代表紅色色彩分量。   |
|\<GreenComponent\>   |Byte (0-255)   ||代表綠色色彩分量。   |
|\<BlueComponent\>   |Byte (0-255)   ||代表藍色色彩分量。   |
| | | |
   
&#x2776; 所有的第一層元素都是選用的。 如果省略第一層元素, 則其所有子參數在裝置上保持不變。
  
&#x2777; 布林值旗可以是下列任何一項: true、false、0或1。 布林值或數值保留空白, 可能會將 XML 轉譯為格式錯誤, 因此不會對設定進行任何變更。
  
 &#x2778; 如果字串參數存在、空白且空白是有效的值, 則會在裝置上清除該參數。
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>使用 XML 設定檔管理主控台設定

在啟動時, 如果 Microsoft [團隊聊天室] 主控台在位置**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**找到名為 SKYPESETTINGS 的 xml 檔案, 則會套用設定設定由 XML 檔案指示, 然後刪除 XML 檔案。
  
根據您的企業有多少 Microsoft 團隊房間裝置, 以及您選擇如何管理以進行設定, 您可以使用多種方式來放置 XML 設定檔。 將檔案推送到主控台之後, 請重新開機該檔案以處理設定變更。 在成功處理 XML 設定檔之後, 就會刪除該檔案。 Microsoft 團隊會議室裝置建議的管理方法將在下列專案中討論:
  
- [為 Microsoft 團隊聊天室設定群組原則](room-systems-v2-operations.md#GroupPolicy)
    
- [使用 PowerShell 進行遠端系統管理](room-systems-v2-operations.md#RemotePS)並[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
您可以隨意使用任何您喜歡的方法, 只要您使用它來傳輸檔案, 然後在主控台裝置上觸發重新開機。 該檔案必須是由裝置的本機使用者帳戶所擁有的可讀、可寫且可刪除的檔案 (最好是該檔案擁有, 且擁有該使用者的完整許可權)。 如果檔案許可權設定不正確, 軟體可能無法套用設定, 可能無法在成功處理後刪除檔案, 甚至可能會損毀。
  
## <a name="custom-theme-images"></a>自訂主題圖像
<a name="Themes"> </a>

自訂主題圖像檔案必須放在**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**中, 只要在\<CustomThemeImageUrl\>變數中輸入檔案名和副檔名即可。
  
Image 檔案應該是完全3840X1080 的圖元, 且必須是下列其中一種檔案格式: jpg、jpeg、png 和 bmp。 如果您的組織想要自訂影像, 圖形設計師會發現我們的[自訂主題 Photoshop 範本](https://go.microsoft.com/fwlink/?linkid=870441)很有用。 它包含在主題影像中放置各種元素的位置的詳細資訊, 以及哪些區域會顯示在主控台和顯示器上。
  
XML 設定檔必須在裝置啟動時更新, 才能辨識主題影像。 處理並刪除新的 XML 檔案之後, 主題圖形檔案就會從目錄中刪除。
  
## <a name="see-also"></a>另請參閱


[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)

[設定檔案專案](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
