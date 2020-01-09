---
title: 鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 摘要：針對商務用 Skype Server 鎖定或解除鎖定使用者的電話撥入式會議 PIN。
ms.openlocfilehash: bbf082fd85780972387cf014573e22996a9edcf0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992310"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN
 
**摘要：** 針對商務用 Skype Server 鎖定或解除鎖定使用者的電話撥入式會議 PIN。
  
您可以從商務用 Skype Server [控制台] 的 [**使用者**] 區段鎖定或解除鎖定使用者的 PIN。
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server [控制台] 中鎖定使用者的 PIN

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 使用下列其中一種方法來尋找使用者：
    
    - 在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。
    
    - 如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。
    
5. 可選指定額外的搜尋準則以縮小結果範圍：
    
   是. 按一下 [**新增篩選**]。
    
   乙. 輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。
    
   c-clip. 在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。
    
   希望. 根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。
    
    > [!TIP]
    > 若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。 
  
   e. 按一下 [**尋找**]。
    
   °. 按一下使用者，按一下 [**動作**]，然後按一下 [**鎖定 PIN**]。
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>在商務用 Skype Server [控制台] 中解除鎖定使用者的 PIN

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 使用下列其中一種方法來尋找使用者：
    
   - 在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。
    
   - 如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。
    
5. 可選指定額外的搜尋準則以縮小結果範圍：
    
   是. 按一下 [**新增篩選**]。
    
   乙. 輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。
    
   c-clip. 在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。
    
   希望. 根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。
    
    > [!TIP]
    > 若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。 
  
   e. 按一下 [**尋找**]。
    
   °. 按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 PIN**]。
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 鎖定及解除鎖定使用者 Pin

您可以使用 Windows PowerShell 以及 Lock CsClientPin 和解除 CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話中執行這些 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-lock-a-user-pin"></a>鎖定使用者 PIN

- 若要鎖定使用者的 PIN，請使用 Lock CsClientPin Cmdlet。 例如：
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>解除鎖定使用者 PIN

- 若要解除鎖定使用者的 PIN，請使用 Unlock CsClientPin Cmdlet。 例如：
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

如需詳細資訊，請參閱[Lock CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps)和[解除 CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) Cmdlet 的說明主題。
