---
title: 鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要：鎖定或解除鎖定使用者的電話撥入式會議 PIN 以取得商務用 Skype Server。
ms.openlocfilehash: 6f09886b9f8a3e95317c19e1cd509cc8f1abd1d7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410896"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN
 
**總結：** 鎖定或解除鎖定使用者的電話撥入式會議 PIN，以供商務用 Skype Server。
  
您可以從商務用 Skype Server 控制台的 [**使用者**] 區段鎖定或解除鎖定使用者的 PIN。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中鎖定使用者的 PIN

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
    
   f. 按一下使用者、**[動作]**，然後按一下 **[鎖定 PIN]**。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中解除鎖定使用者的 PIN

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
    
   f. 按一下使用者、**[動作]**，然後按一下 **[解除鎖定 PIN]**。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 鎖定和解除鎖定使用者 pin

您可以使用 Windows PowerShell 和 Lock-CsClientPin 及 Unlock-CsClientPin Cmdlet 來鎖定和解除鎖定使用者 pin。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。
  
### <a name="to-lock-a-user-pin"></a>鎖定使用者 PIN

- 若要鎖定使用者的 PIN 碼，請使用 Lock-CsClientPin Cmdlet。 例如：
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>解除鎖定使用者 PIN

- 若要解除鎖定使用者的 PIN 碼，請使用 Unlock-CsClientPin Cmdlet。 例如：
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

如需詳細資訊，請參閱 [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) 和 [Unlock-CsClientPin](/powershell/module/skype/unlock-csclientpin?view=skype-ps) Cmdlet 的 [說明] 主題。