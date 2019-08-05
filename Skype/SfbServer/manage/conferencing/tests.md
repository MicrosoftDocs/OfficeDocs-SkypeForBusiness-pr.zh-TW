---
title: 在商務用 Skype Server 中測試電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '摘要: 瞭解如何在商務用 Skype Server 中測試電話撥入式會議。'
ms.openlocfilehash: cd1192950ff7c8b609655d78bbc57dfdbc4c1710
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188920"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中測試電話撥入式會議
 
**摘要:** 瞭解如何在商務用 Skype Server 中測試電話撥入式會議。
  
針對您的電話撥入式會議設定的最終驗證, 您可以搜尋其電話撥入式會議區域不是由任何存取號碼所使用的撥號方案, 以及尚未指定電話撥入式會議區域的存取號碼。 您也應該確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>使用電話撥入式會議區域尋找不是由存取號碼使用的撥號方案

1. 以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作:
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    這個 Cmdlet 會傳回具有電話撥入式會議區域的所有撥號方案, 這些方案不是由存取號碼所使用。
    
如需詳細資訊, 請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="find-access-numbers-without-assigned-regions"></a>尋找不含指派區域的存取號碼

1. 以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作:
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    這個 Cmdlet 會傳回與區域不相關的所有電話撥入式會議存取號碼。
    
如需詳細資訊, 請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="test-webpage-and-access-numbers"></a>測試網頁和存取號碼

若要確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作, 您必須執行下列動作:
  
- 登入簡單的 URL, 測試電話撥入式會議設定網頁。
    
- 您可以在本主題稍後執行腳本, 以測試存取號碼是否能在特定的池中正常運作。 此腳本會類比存取號碼的通話。 您需要在特定的池中託管的單一整合通訊 (UC) 用戶端的 SIP 位址和認證, 才能使用此腳本。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>測試特定資源的存取號碼

1. 以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作:
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    產生的報告會顯示成功或失敗, 以及特定的診斷資訊。 -Verbose 標誌提供已找到多少個存取號碼的詳細資訊, 以及它們的詳細資料。
    
如需詳細資訊, 請參閱[測試 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。
  

