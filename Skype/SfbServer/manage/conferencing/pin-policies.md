---
title: 在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: '摘要: 瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。'
ms.openlocfilehash: a8db6fc0398d2f577afe54ab2289c3122adcb197
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188923"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。
  
在貴組織中擁有 Active Directory 網域服務 (AD DS) 認證的商務用 Skype 伺服器使用者可以使用個人識別碼 (PIN), 將電話撥入式會議加入為已驗證的使用者。 PIN 原則定義電話撥入式會議 Pin 如何運作的規則。
  
 如果您想要為您的整個組織使用相同的 PIN 原則, 您可以使用全域 PIN 原則, 並視需要加以修改。 全域 PIN 原則會定義目錄林層級電話撥入式會議 Pin 的規則。 您可以修改全域 PIN 原則, 但無法將其刪除。
  
如果您想要將特定原則套用至網站或特定使用者群組, 您可以建立新的 PIN 原則。
  
PIN 原則適用于最窄範圍的使用者到最廣泛的範圍。 如果您將使用者層級的 PIN 原則指派給使用者, 這些設定就會優先。 如果您沒有指派使用者原則, 就會套用網站層級的 PIN 原則 (如果有的話)。 如果沒有適用的使用者或網站原則, 全域 PIN 原則就會提供預設設定。
  
## <a name="view-information-about-pin-policies"></a>查看 PIN 原則的相關資訊

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面, 查看 PIN 原則的相關資訊。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 來查看 PIN 原則的相關資訊

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下您要查看的 PIN 原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來查看 PIN 原則的相關資訊

若要查看 PIN 原則的相關資訊, 請使用**CsPinPolicy** Cmdlet。 例如, 下列命令會傳回具有身分識別網站的單一 PIN 原則的相關資訊: 雷德蒙:
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

如需詳細資訊 (包括完整的語法描述及參數清單), 請參閱[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。
  
## <a name="modify-the-global-pin-policy"></a>修改全域 PIN 原則

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來修改全域 PIN 原則。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改全域電話撥入式會議 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下 [**全域**原則], 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中, 輸入或選取您要允許的最小 pin 長度。 預設的最小長度為5位數。
    
6. 若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設, 會自動決定最大嘗試次數。
    
7. 如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。
    
8. 若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項, 針腳將永不過期。 根據預設, Pin 永遠不會過期。
    
9. 如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。
    
10. 在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設, 使用者可以重複使用他們的 Pin。
    
11. 若要在 Pin 中允許通用位數 (例如順序編號和重複的數位組), 請選取 [**允許常見模式**] 核取方塊。 如果您沒有選取此選項, 則只允許使用複雜的數位模式。 根據預設, 只允許使用複雜的數位模式。
    
    > [!IMPORTANT]
    > 出於安全性考慮, Microsoft 建議您不要允許常見模式。 
  
12. 按一下 [認可]****。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改全域電話撥入式會議 PIN 原則

若要修改全域電話撥入式會議 PIN 原則, 請使用**CsPinPolicy** Cmdlet。
  
下列命令會變更在組織中設定為使用的所有 PIN 原則的 MinPasswordLength 值。 若要這樣做, 命令會先呼叫**CsPinPolicy Cmdlet (** 不含任何參數), 才能檢索所有現有的 PIN 原則集合。 然後, 該集合會以管道傳送給**CsPinPolicy** Cmdlet, 以修改集合中每個原則的 MinPasswordLength 屬性值:
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

如需詳細資訊 (包括完整的語法描述及參數清單), 請參閱[設定 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來建立使用者或網站 PIN 原則。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立使用者或網站 PIN 原則

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下 [**新增**], 然後執行下列其中一項操作:
    
   - 若要建立使用者層級原則, 按一下 [**使用者原則**]。 在 [**新 PIN 原則**] 的 [**名稱**] 中, 輸入描述原則的名稱。
    
   - 若要建立網站層級原則, 按一下 [**網站原則**]。 在 [**選取網站**搜尋] 欄位中, 輸入您要為其建立原則之網站的全部或部分名稱。 在網站清單中, 按一下您想要的網站, 然後按一下 **[確定]**。
    
5. 在 [**描述**] 欄位中, 輸入 PIN 原則的描述。
    
6. 在 [**最小 pin 長度**] 欄位中, 輸入或選取您要允許的最小 PIN 長度。 預設的最小長度為5位數。
    
7. 若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設, 會自動決定最大嘗試次數。
    
8. 如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。
    
9. 若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項, 針腳將永不過期。 根據預設, Pin 永遠不會過期。
    
10. 如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。
    
11. 在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設, 使用者可以重複使用他們的 Pin。
    
12. 若要在 Pin 中允許通用位數 (例如順序編號和重複的數位組), 請選取 [**允許常見模式**] 核取方塊。 如果您沒有選取此選項, 則只允許使用複雜的數位模式。 根據預設, 只允許使用複雜的數位模式。
    
    > [!IMPORTANT]
    > 出於安全性考慮, Microsoft 建議您不要允許常見模式。 
  
13. 按一下 [認可]****。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來建立使用者或網站 PIN 原則

若要建立使用者或網站 PIN 原則, 請使用**CsPinPolicy** Cmdlet。
  
下列命令會建立具有身分識別網站: 雷德蒙的新 PIN 原則。 這個命令只包含一個選用參數 MinPasswordLength, 可用於將 MinPasswordLength 屬性設為7。 所有剩餘的原則屬性都將使用預設值進行設定。
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 如需詳細資訊 (包括完整的語法描述及參數清單), 請參閱[新 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。
  
## <a name="modify-a-user-or-site-pin-policy"></a>修改使用者或網站的 PIN 原則

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來修改使用者或網站的 PIN 原則。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改使用者或網站的 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下您要變更的固定原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯 PIN 原則**] 中, 修改任何原則設定 (除了不能修改的原則名稱之外)。
    
6. 按一下 [認可]****。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改使用者或網站的 PIN 原則

若要修改電話撥入式會議 PIN 原則, 請使用**CsPinPolicy** Cmdlet。
  
下列命令會修改指派給雷德蒙者網站的 PIN 原則。 在這種情況下, 該命令會將 MinPasswordLength 屬性的值變更為 10;這表示新的 Pin 必須至少包含10個數字:
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

如需詳細資訊 (包括完整的語法描述及參數清單), 請參閱[設定 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="delete-a-user-or-site-pin-policy"></a>刪除使用者或網站 PIN 原則

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面, 刪除使用者或網站的 PIN 原則。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 刪除使用者或網站的 PIN 原則

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [ **PIN 規則**]。
    
4. 在 [ **PIN 原則**] 頁面上, 按一下您要變更的固定原則, 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management 命令介面刪除使用者或網站的 PIN 原則

若要刪除使用者或網站 PIN 原則, 請使用**CsPinPolicy** Cmdlet。
  
下列命令會移除已在網站範圍中設定的所有 PIN 原則。 若要這樣做, 請使用**CsPinPolicy** Cmdlet 與 Filter 參數, 以傳回以「site:」字元打頭之身分識別的所有原則集合。 然後將此集合輸送為**CsPinPolicy** Cmdlet, 這會刪除集合中的每個原則:
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

如需詳細資訊 (包括完整的語法描述及參數清單), 請參閱[移除-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。
  

