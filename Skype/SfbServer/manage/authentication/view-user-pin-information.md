---
title: 在商務用 Skype Server 中查看使用者 PIN 資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 摘要：在商務用 Skype Server 中查看使用者 PIN 資訊。
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818685"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看使用者 PIN 資訊
 
**摘要：** 在商務用 Skype Server 中查看使用者 PIN 資訊。
  
若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的商務用 Skype 伺服器使用者需要個人識別碼（PIN）。 您可以從商務用 Skype Server [控制台] 查看使用者的 PIN 資訊。
  
> [!NOTE]
> 您可以查看 PIN 狀態資訊，例如，PIN 是否已設定，或是 PIN 上次變更的時間，但是您看不到目前的 PIN，只需要查看 PIN 狀態即可。 如果使用者遺失其 PIN，您可以依照在[商務用 Skype Server 中設定使用者的電話撥入式會議 PIN](set-a-user-s-dial-in-conferencing-pin.md)中的程式來重設它。
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server [控制台] 中查看使用者的 PIN

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
    
    > [!NOTE]
    > 如果 PIN 已鎖定，您必須先解除鎖定 PIN，才能進行設定。 若要解除鎖定 PIN，請按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 pin**]。 
  
6. 在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**查看 PIN 狀態**]。
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看使用者 PIN 資訊

您可以使用 CsClientPinInfo Cmdlet 來查看使用者 PIN 資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-view-user-pin-information"></a>若要查看使用者 PIN 資訊

若要查看使用者的 PIN 資訊，請在商務用 Skype Server 管理命令介面中輸入類似以下的命令，然後按 ENTER：
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

這會傳回如下所示的資訊：

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

如需詳細資訊，請參閱[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) Cmdlet 的說明主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN](set-a-user-s-dial-in-conferencing-pin.md)
  
[鎖定或解除鎖定商務用 Skype Server 中的使用者 PIN](lock-or-unlock-a-user-pin.md)
