---
title: 測試商務用 Skype Server 中的電話撥入式會議
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要：瞭解如何在商務用 Skype Server 中測試電話撥入式會議。
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827933"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>測試商務用 Skype Server 中的電話撥入式會議
 
**摘要：** 瞭解如何在商務用 Skype Server 中測試電話撥入式會議。
  
做為您的電話撥入式會議設定的最終驗證，您可以搜尋撥號對應表，該撥號對應表中的電話撥入式會議地區未使用任何存取號碼，且未指定電話撥入式會議區域的存取號碼。 此外，您也應驗證電話撥入式會議設定網頁和撥入式存取號碼是否運作正常。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>使用電話撥入式會議區域（未使用的存取號碼）尋找撥號對應表

1. 以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    此 Cmdlet 會傳回所有電話撥入式會議地區未由存取號碼使用的撥號對應表。
    
如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="find-access-numbers-without-assigned-regions"></a>尋找未指派地區的存取號碼

1. 以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    此 Cmdlet 會傳回與地區無關聯的所有電話撥入式會議存取號碼。
    
如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="test-webpage-and-access-numbers"></a>測試網頁和存取號碼

若要確認電話撥入式會議設定網頁和撥入式存取號碼正確運作，您需要執行下列動作：
  
- 登入簡單 URL，以測試 [電話撥入式會議設定] 網頁。
    
- 執行本主題稍後的指令碼，以測試特定集區的存取號碼是否正常運作。此指令碼會模擬撥打存取號碼。您需要特定集區裝載控之某個整合通訊 (UC) 用戶端的 SIP 位址和認證，才能使用此指令碼。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>若要測試特定集區的存取號碼

1. 以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    產生的報告會顯示「成功」或「失敗」，以及特定的診斷資訊。 -Verbose 旗標提供找到多少存取號碼及相關詳細資料的詳細資訊。
    
如需詳細資訊，請參閱 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。
  

