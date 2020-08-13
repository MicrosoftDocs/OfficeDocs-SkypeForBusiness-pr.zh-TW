---
title: Lync Server 2013：指派每個使用者的會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134449"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的會議原則

 


會議原則是您可以在 Lync Server 控制台中設定之使用者帳戶的其中一個個別設定。

您可以選擇部署一或多個個別使用者會議原則。您也可以只部署一個全域層級會議原則或網站層級會議原則。如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。未指派特定網站層級或個別使用者原則時，會議使用者權限會自動預設為全域層級會議原則中定義的權限。

至少建立一個個別使用者會議原則之後，請使用本主題中的程序來指派原則，此原則指定想要伺服器授與特定使用者所召集之會議的使用者權限。

如需所有可用之會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。

如需建立會議原則的詳細資訊，請參閱[建立或修改 Lync Server 2013 中的會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。

## <a name="to-assign-a-per-user-conferencing-policy"></a>指派個別使用者會議原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  使用下列其中一種方法，找到使用者：
    
      - 在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。
    
      - 如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。

5.  (選用) 指定其他搜尋條件，縮減結果：
    
    1.  按一下 **[新增篩選]**。
    
    2.  輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。
    
    3.  在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。
    
    4.  依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。
        

        > [!TIP]  
        > 若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。

    
    5.  按一下 **[尋找]**。

6.  依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。
    

    > [!TIP]  
    > 如果想將同一個個別使用者會議原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後依序按一下<STRONG>[動作]</STRONG> 和 <STRONG>[指派原則]</STRONG>。



7.  在 **[指派原則]** 的 **[會議原則]** 下方，執行下列其中一項動作：
    

    > [!NOTE]  
    > 因為您可以在 [<STRONG>指派原則</STRONG>] 中設定多個原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。 不變更此設定，即可繼續沿用先前指派給使用者的原則。

    
      - 選取 [ ** \< 自動 \> ** ] 以允許 Lync Server 2013 自動選擇全域層級原則，或網站層級原則（如果已定義）。
    
      - 按一下先前在 **[會議原則]** 頁面上定義的個別使用者會議原則名稱。
        

        > [!TIP]  
        > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。



8.  完成時，請按一下 **[確定]**。

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 會議原則

您可以使用 Windows PowerShell 和 Grant-CsConferencingPolicy Cmdlet 指派每個使用者的會議原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>將每一使用者會議原則指派給單一使用者

  - 下列命令可將個別使用者會議原則 RedmondConferencingPolicy 指派給使用者 Ken Myer。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>將每一使用者會議原則指派給多位使用者

  - 此命令可將個別使用者會議原則 HRConferencingPolicy，指派給所有任職於人力資源部門的使用者。 如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>取消指派個別使用者會議原則

  - 下列命令可將先前指派給 Ken Myer 的任何個別使用者會議原則予以解除指派。一旦解除指派個別使用者原則，即會自動使用全域原則或其本機網站原則 (如果存在的話) 來管理 Ken Myer。網站原則的優先順序高於全域原則。
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[在 Lync Server 2013 中指派每一使用者原則](lync-server-2013-assigning-per-user-policies.md)

