---
title: 在商務用 Skype Server 中指派每位使用者的 PIN 原則
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
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：適用于商務用 Skype Server 的 [階段 AV] 和 [OAuth 憑證]。
ms.openlocfilehash: b7c353090f9eef3d2d2fbd0e6f8884121458f2f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818865"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中指派每位使用者的 PIN 原則

**摘要：** 針對商務用 Skype Server 階段 AV 和 OAuth 憑證。
  
電話撥入式會議個人識別碼（PIN）原則是可在商務用 Skype Server [控制台] 中設定的使用者帳戶個人設定之一。
  
部署一或多個使用者 PIN 原則是選擇性的。 您也可以只部署全域層級的 PIN 原則或網站層級的 PIN 原則。 如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。 指派電話撥入式會議 Pin 的使用者權利和許可權，在沒有指派任何特定網站層級或每使用者原則時，系統會自動將預設值設為全域層級 PIN 原則中定義的 Pin。
  
建立至少一個針對每位使用者的 PIN 原則之後，請使用本主題中的程式，指派指定您希望伺服器強加在由特定使用者所建立之 Pin 所產生之限制的原則。
  
### <a name="to-assign-a-per-user-pin-policy"></a>指派每位使用者的 PIN 原則

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
    
6. 在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。
    
    > [!TIP]
    > 如果您想要將相同的每個使用者 PIN 原則套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [**動作**]，再按一下 [**指派原則**]。 
  
7. 在 [**指派原則**] 的 [ **PIN 原則**] 底下，執行下列其中一項操作：
    
    > [!NOTE]
    > 因為您可以使用 [**指派原則**] 對話方塊來設定多個原則， ** \< \> **所以對話方塊中的每個原則預設都會選取 [持續保持為]。 針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。
  
   - [允許商務用 Skype 伺服器] 自動選擇 [全域層級原則] 或 [（如果已定義）] 網站層級原則。
    
   - 按一下您先前在 [ **PIN 策略**] 頁面上定義之每個使用者 PIN 原則的名稱。
    
     > [!TIP]
     > 若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （**查看**），以查看原則中定義的使用者權利和許可權。
  
8. 完成後，請按一下 **[確定]**。
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的 PIN 原則

您可以使用 Windows PowerShell 和**Grant CsPinPolicy** Cmdlet 來指派每個使用者的 PIN 原則。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>將每位使用者 PIN 原則指派給單一使用者

- 下列命令會將每個使用者的 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>將每位使用者 PIN 原則指派給多個使用者

- 下列命令會將每位使用者的 PIN 原則 RedmondUsersPinPolicy 指派給所有在雷蒙德市中工作的使用者。 如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>若要取消指派每位使用者的 PIN 原則

- 下列命令會以前指派給 Ken Myer 的任何每使用者 PIN 原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

如需詳細資訊，請參閱[授與 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立新的 PIN 原則](create-a-new-pin-policy.md)
