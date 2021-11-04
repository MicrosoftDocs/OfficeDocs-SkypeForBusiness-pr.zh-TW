---
title: 在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要：瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。
ms.openlocfilehash: d82be95a3e6ff6fcfc65c5fd7449f9035ee64635
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763811"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議的 PIN 原則。
  
在您組織中具有 Active Directory 網域服務 (AD DS) 認證的商務用 Skype Server 使用者，您可以使用個人識別碼 (PIN) ，將電話撥入式會議加入為已驗證的使用者。 PIN 原則可定義電話撥入式會議 PIN 的運作方式規則。
  
 如果您要對整個組織使用相同的 PIN 原則，您可以使用全域 PIN 原則，並視需要加以修改。 全域 PIN 原則可在樹系層級上定義電話撥入式會議 PIN 的規則。 您可以修改全域 PIN 原則，但無法加以刪除。
  
如果您要將特定原則套用至網站或特定使用者群組，您可以建立新的 PIN 原則。
  
對使用者套用 PIN 原則時，會優先套用最小的範圍。 如果您為使用者指派了使用者層級 PIN 原則，這些設定將會優先套用。 如果您未指派使用者原則，則會套用網站層級 PIN 原則 (若有的話)。 如果未套用使用者或網站原則，則會使用全域 PIN 原則的預設設定。
  
## <a name="view-information-about-pin-policies"></a>查看有關 PIN 原則的資訊

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，查看 PIN 原則的相關資訊。
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台，查看 PIN 原則的相關資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。
    
4. 在 [ **PIN 原則** ] 頁面上，按一下您要查看的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面，查看 PIN 原則的相關資訊

若要查看有關 PIN 原則的資訊，請使用 **Get-CsPinPolicy** Cmdlet。 例如，下列命令會傳回 Identity 為 site： Redmond 的單一 PIN 原則資訊：
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps)。
  
## <a name="modify-the-global-pin-policy"></a>修改通用 PIN 原則

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，修改全域 PIN 原則。
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改全域電話撥入式會議 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。
    
4. 在 **[PIN 原則]** 頁面上，依序按一下 **[通用]** 原則、**[編輯]** 和 **[顯示詳細資料]**。
    
5. 在 **[編輯 PIN 原則]** 的 **[最小 PIN 長度]** 中，輸入或選取您要允許的最小 PIN 長度。預設的最小長度為五位數。
    
6. 若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。
    
7. 如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。
    
8. 若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。
    
9. 如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。
    
10. 在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。
    
11. 若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。
    
    > [!IMPORTANT]
    > 基於安全性的考慮，Microsoft 建議您不要允許通用模式。 
  
12. 按一下 **[認可]**。
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面，修改全域電話撥入式會議 PIN 原則

若要修改全域電話撥入式會議 PIN 原則，請使用 **Set-CsPinPolicy** Cmdlet。
  
下列命令會變更所有設定供組織使用之 PIN 碼原則的 MinPasswordLength 值。 為達到此目的，命令會先呼叫不含任何參數的 **Get-CsPinPolicy** Cmdlet，以取回所有現有 PIN 碼原則的集合。 然後，該集合會管線傳送至 **Set-CsPinPolicy** Cmdlet，此 Cmdlet 會修改集合中每個原則的 MinPasswordLength 屬性值：
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，來建立使用者或網站 PIN 原則。
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立使用者或網站 PIN 原則

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。
    
4. 在 [ **PIN 原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
   - 若要建立使用者層級原則，請按一下 [ **使用者原則**]。 在 [ **新增 PIN 原則**] 的 [ **名稱**] 中，輸入描述原則的名稱。
    
   - 若要建立網站層級原則，請按一下 [ **網站原則**]。 在 [ **選取網站** ] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。 在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
5. 在 [ **描述** ] 欄位中，輸入 PIN 原則的描述。
    
6. 在 [ **最小 PIN 碼長度** ] 欄位中，輸入或選取您想要允許的最小 pin 碼長度。 預設的最小長度為五位數。
    
7. 若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。
    
8. 如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。
    
9. 若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。
    
10. 如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。
    
11. 在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。
    
12. 若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。
    
    > [!IMPORTANT]
    > 基於安全性的考慮，Microsoft 建議您不要允許通用模式。 
  
13. 按一下 **[認可]**。
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立使用者或網站 PIN 原則

若要建立使用者或網站 PIN 原則，請使用 **get-cspinpolicy** Cmdlet。
  
下列命令會使用 Identity site： Redmond 建立新的 PIN 原則。 這個命令只包含一個 optional 參數 MinPasswordLength，可用來將 MinPasswordLength 屬性設定為7。 所有剩餘的原則屬性都會以預設值進行設定。
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [get-cspinpolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps)。
  
## <a name="modify-a-user-or-site-pin-policy"></a>修改使用者或網站 PIN 原則

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，修改使用者或網站 PIN 原則。
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改使用者或網站 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。
    
4. 在 [ **PIN 原則** ] 頁面上，按一下您要變更的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯 PIN 原則**] 中，修改原則名稱 (以外的任何原則設定，但無法修改) 。
    
6. 按一下 **[認可]**。
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面修改使用者或網站 PIN 原則

若要修改電話撥入式會議 PIN 原則，請使用 **Set-CsPinPolicy** Cmdlet。
  
下列命令會修改指派給 Redmond 網站的 PIN 碼原則。 在此情況下，此命令會將 MinPasswordLength 屬性的值變更為10。這表示新 Pin 必須至少包含10位數：
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps)。
  
## <a name="delete-a-user-or-site-pin-policy"></a>刪除使用者或網站 PIN 原則

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來刪除使用者或網站 PIN 原則。
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台刪除使用者或網站 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [會議] 再按一下 [PIN 原則]。
    
4. 在 [ **PIN 原則** ] 頁面上，按一下您要變更的 PIN 原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面刪除使用者或網站 PIN 原則

若要刪除使用者或網站 PIN 原則，請使用 **get-cspinpolicy** Cmdlet。
  
下列命令會移除已在網站範圍設定的所有 PIN 碼原則。 若要這麼做，請使用 **Get-CsPinPolicy** Cmdlet 及 Filter 參數，傳回 Identity 以字元 "site：" 開頭的所有原則的集合。 然後，此集合會管線傳送至 **get-cspinpolicy** Cmdlet，以刪除集合中的每個原則：
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

如需詳細資訊，包括完整的語法描述及參數清單，請參閱 [Remove-get-cspinpolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。
