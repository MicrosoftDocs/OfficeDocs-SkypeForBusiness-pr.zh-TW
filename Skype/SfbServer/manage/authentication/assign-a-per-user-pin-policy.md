---
title: 在商務用 Skype Server 中指派每個使用者的 PIN 原則
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：階段 AV 和 OAuth 商務用 Skype Server 的憑證。
ms.openlocfilehash: 51bf650d907923c83801799a28220eae9a1f385c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845476"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中指派每個使用者的 PIN 原則

**摘要：** 階段 AV 和 OAuth 商務用 Skype Server 的憑證。
  
電話撥入式會議個人身分識別號碼 (PIN) 原則是可在 [商務用 Skype Server 控制台] 中設定之使用者帳戶的個別設定之一。
  
部署一或多個個別使用者 PIN 碼原則是選用的。 您也可以只部署全域層級的 PIN 原則或網站層級的 PIN 原則。 如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。 在未指派任何特定的網站層級或個別使用者原則時，自動將電話撥入式會議 Pin 使用之 Pin 的使用者權利和許可權預設設為全域層級 PIN 原則中所定義的使用者權限。
  
在建立至少一個個別使用者 PIN 原則之後，請使用本主題中的程式來指派原則，以指定您想要讓伺服器強加于特定使用者所建立及使用之 Pin 的限制。
  
### <a name="to-assign-a-per-user-pin-policy"></a>若要指派每個使用者的 PIN 原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 使用下列其中一種方法，找到使用者：
    
   - 在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。
    
   - 如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。
    
5. (選用) 指定其他搜尋條件，縮減結果：
    
   a. 按一下 **[新增篩選]**。
    
   b. 輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。
    
   c. 在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。
    
   d. 依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。
    
    > [!TIP]
    > 若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。 
  
   e. 按一下 **[尋找]**。
    
6. 依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。
    
    > [!TIP]
    > 如果您要將相同的個別使用者 PIN 原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ **動作**]，再按一下 [ **指派原則**]。 
  
7. 在 [ **指派原則**] 的 [ **PIN 原則**] 底下，執行下列其中一項動作：
    
    > [!NOTE]
    > 因為有多種可使用 [ **指派原則** ] 對話方塊進行設定的原則，所以 **\<Keep as is\>** 預設會選取對話方塊中的每個原則。 不變更此設定，即可繼續沿用先前指派給使用者的原則。
  
   - 允許商務用 Skype Server 自動選擇全域層級原則，或網站層級原則（如果已定義）。
    
   - 按一下您先前在 [ **PIN 原則** ] 頁面上定義之個別使用者 PIN 原則的名稱。
    
     > [!TIP]
     > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 **[檢視]** 可以檢視該原則所定義的使用者權限。
  
8. 完成時，請按一下 **[確定]**。
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User PIN 原則

您可以使用 Windows PowerShell 和 **授與 get-cspinpolicy 指令程式** 指派每個使用者的 PIN 原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync 遠端 PowerShell 管理](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>將每一使用者 PIN 原則指派給單一使用者

- 下列命令會將每位使用者 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>將每一使用者 PIN 原則指派給多個使用者

- 下列命令會將個別使用者 PIN 原則 RedmondUsersPinPolicy 指派給 Redmond 的城市中所有工作的使用者。 如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>取消指派每個使用者的 PIN 原則

- 下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者 PIN 原則。 一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。 網站原則優先順序高於全域原則。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

如需詳細資訊，請參閱 [授與 get-cspinpolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立新的 PIN 原則](create-a-new-pin-policy.md)