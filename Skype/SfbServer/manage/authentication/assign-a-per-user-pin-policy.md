---
title: 在 商務用 Skype Server 中指派個別使用者 PIN 原則
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
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：將個別使用者 PIN 原則指派給商務用 Skype Server中的使用者。
ms.openlocfilehash: 26df2323647f295c7a1fbff41efbeae3e12b151f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675505"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>在 商務用 Skype Server 中指派個別使用者 PIN 原則

**總結：** 暫存 AV 和 OAuth 憑證商務用 Skype Server。

電話撥入式會議個人識別碼 (PIN) 原則是使用者帳戶的其中一個可在商務用 Skype Server 主控台中設定的個別設定。

部署一或多個每位使用者 PIN 原則是選擇性的。 您也可以只部署全域層級 PIN 原則或月臺層級 PIN 原則。 如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。 當未指派特定月臺層級或每一使用者原則時，有關使用 PIN 進行撥入式會議的使用者權限和許可權，會自動預設為全域層級 PIN 原則中定義的使用者權限。

建立至少一個每一使用者 PIN 原則之後，請使用本主題中的程式來指派原則，以指定您希望伺服器對特定使用者所建立和使用的 PIN 施加的條件約束。

## <a name="to-assign-a-per-user-pin-policy"></a>指派每位使用者 PIN 原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理員 URL 以開啟商務用 Skype Server 主控台。

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
    > 如果您想要將相同的個別使用者 PIN 原則套用至多個使用者，請在搜尋結果中選取多個使用者，然後按一下 [ **動作]**，然後按一下 [ **指派原則]**。

7. 在 [ **指派原則**] 的 **[PIN 原則]** 下，執行下列其中一項：

    > [!NOTE]
    > 由於您可以使用 [指 **派** 原則] 對話方塊來設定多個原則， **\<Keep as is\>** 因此預設會針對對話方塊中的每個原則選取 。 不變更此設定，即可繼續沿用先前指派給使用者的原則。

   - 允許商務用 Skype Server自動選擇全域層級原則，或在定義時選擇月臺層級原則。

   - 按一下您先前在 [PIN 原則] 頁面上定義的每個使用者 **PIN 原則** 名稱。

     > [!TIP]
     > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 **[檢視]** 可以檢視該原則所定義的使用者權限。

8. 完成時，請按一下 **[確定]**。

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派Per-User PIN 原則

您可以使用 Windows PowerShell 和 **Grant-CsPinPolicy** Cmdlet 來指派每個使用者的 PIN 原則。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需使用遠端Windows PowerShell連線到商務用 Skype Server的詳細資訊，請參閱[Microsoft Lync 遠端 PowerShell 管理」](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 程式在商務用 Skype Server中相同。

### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>將個別使用者 PIN 原則指派給單一使用者

- 下列命令會將個別使用者 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>將個別使用者 PIN 原則指派給多個使用者

- 下列命令會將每位使用者 PIN 原則 RedmondUsersPinPolicy 指派給在 Redmond 市中工作的所有使用者。 如需此命令中所使用 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser)。

  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>取消指派每位使用者 PIN 原則

- 下列命令會取消指派先前指派給 Ken Myer 的任何每位使用者 PIN 原則。 一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。 網站原則優先順序高於全域原則。

  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

如需詳細資訊，請參閱 [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy)。

## <a name="see-also"></a>另請參閱

[在 商務用 Skype Server 中建立新的 PIN 原則](create-a-new-pin-policy.md)
