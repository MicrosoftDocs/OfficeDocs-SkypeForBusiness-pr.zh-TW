---
title: 在商務用 Skype 中自訂 Mac 用戶端體驗
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: 本文將說明 Mac 版商務用 Skype 的客戶喜好設定及預設值, 以及如何在 App 外編輯這些設定。
ms.openlocfilehash: 6b343c076d0fd1736cc6974a5c33103f0b6dfcda
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234445"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>在商務用 Skype 中自訂 Mac 用戶端體驗
 
本文將說明 Mac 版商務用 Skype 的客戶喜好設定及預設值, 以及如何在 App 外編輯這些設定。
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Mac 版商務用 Skype 用戶端喜好設定

Mac 用戶端上的商務用 Skype 所能使用的某些功能和行為是由用戶端上的喜好設定決定。 Mac 版商務用 Skype 喜好設定會在 mac 上的檔案中找到, 該檔案已安裝位於下列路徑的商務用 Skype 用戶端: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
若要設定這些喜好設定, 請在用戶端的 Mac 上取得終端提示, 並視需要輸入預設值 write Com.microsoft.skypeforbusiness.plugin.plist 按鍵命令, 使用下表所述的喜好設定鍵。
  
**用戶端喜好設定鍵**


| 快速鍵 | 類型 | 值 | 說明 |
|:-----|:-----|:-----|:-----|
|AutoDetectAutoDiscoveryURLs    |Bool    |0 = 手動伺服器設定  <br/> 1 = 自動伺服器偵測 (預設)    |指定商務用 Skype 識別登入期間要使用的傳輸和伺服器的方式。 如果您啟用此原則設定, 您必須指定**internalAutoDiscoveryURL**和**externalAutoDiscoveryURL**。   |
|internalAutoDiscoveryURL    |String    |完整的自動探索 URL    |內部自動探索 URL    |
|externalAutoDiscoveryURL    |String    |完整的自動探索 URL    |外部自動探索 URL    |
|HTTPProxyDomain    |String    ||HTTP Proxy 網域    |
|HTTPProxyUserName    |String    ||HTTP Proxy 使用者名稱    |
|HTTPProxyPassword    |String    ||HTTP Proxy 密碼    |
|trustedDomainList    |陣列    ||HTTP 重新導向的信任網域清單。    |
|autoAcceptTimeout    |電話    |300 (預設值)    |針對沒有伺服器端交談記錄的使用者, 自動接受超時。    |
|warnWhenUnknownLocationForE911    |Bool    |0 = 停用  <br/> 1 = 已啟用    |從未知位置撥入緊急號碼時警告使用者。    |
|sipAddress    |String    ||用來登入商務用 Skype 的 SIP 位址 (電子郵件)。    |
|userName    |String    ||用來登入商務用 Skype 的 UPN (使用者名稱)。    |
|userNameInAdvancedOnly    |Bool    |0 = 在主要登錄畫面和 [高級屬性] 對話方塊中顯示 [使用者名稱] 欄位  <br/> 1 = 只在 [高級屬性] 對話方塊中顯示 [使用者名稱] 欄位 (預設)    |指定登入期間 [使用者名稱] 欄位的顯示位置。    |
   
### <a name="usage-examples"></a>用法範例

若要新增單一網域 (Contoso.com) 至 [受信任的網域] 清單, 您可以使用 trustedDomainList 金鑰, 如下所示:
  
預設寫入 Com.microsoft.skypeforbusiness.plugin.plist trustedDomainList-array-add "Contoso.com"
  
若要在受信任的網域清單中新增多個網域, 您可以使用 trustedDomainList 鍵, 如下所示:
  
預設寫入 Com.microsoft.skypeforbusiness.plugin.plist trustedDomainList-array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>範例未編輯的設定

若是參照, 以下是僅使用預設設定的範例設定檔案: 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
