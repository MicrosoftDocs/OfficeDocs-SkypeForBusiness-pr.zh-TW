---
title: 在商務用 Skype Server 中查看使用者 PIN 碼資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在商務用 Skype Server 中查看使用者 PIN 資訊。
ms.openlocfilehash: eb30ae22f5a80835e73962f0e2441633fdc1d46e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622375"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看使用者 PIN 碼資訊
 
**摘要：** 在商務用 Skype Server 中查看使用者 PIN 碼資訊。
  
若要將電話撥入式會議加入為已驗證的使用者，具有 Active Directory 網域服務 (AD DS) 認證的商務用 Skype Server 使用者必須有個人識別碼 (PIN) 。 您可以從商務用 Skype Server 控制台] 中查看使用者的 PIN 碼資訊。
  
> [!NOTE]
> 您可以檢視諸如是否已設定 PIN 或上次變更 PIN 的時間之類的 PIN 狀態資訊，但無法藉由查看 PIN 狀態來查看目前的 PIN。 如果使用者已遺失 PIN 碼，您可以遵循在[商務用 Skype Server 中設定使用者電話撥入式會議 PIN](set-a-user-s-dial-in-conferencing-pin.md)中的程式來重設其 pin 碼。
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中查看使用者的 PIN

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
    
   d. 視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。
    
    > [!TIP]
    > 若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。 
  
   e. 按一下 [尋找]。
    
    > [!NOTE]
    > 如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行] 和 [解除鎖定 PIN]。 
  
6. 依序按一下搜尋結果中的使用者、[執行] 和 [檢視 PIN 狀態]。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看使用者 PIN 碼資訊

您可以使用 Get-CsClientPinInfo Cmdlet 來檢視使用者 PIN 資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-view-user-pin-information"></a>檢視使用者 PIN 資訊

若要查看使用者的 PIN 資訊，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 enter：
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

如此將傳回類似如下的資訊：

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

如需詳細資訊，請參閱 [Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) Cmdlet 的 [說明] 主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN](set-a-user-s-dial-in-conferencing-pin.md)
  
[鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN](lock-or-unlock-a-user-pin.md)