---
title: Lync Server 2013：指派每個使用者的行動性原則
description: Lync Server 2013：指派每個使用者的行動性原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559829"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的行動性原則

 


行動性原則是您可以在 Lync Server 控制台或 Lync Server 管理命令介面中設定之使用者帳戶的其中一個個別設定。

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server 控制台指派每個使用者的行動性原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

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
    > 如果您要將相同的個別使用者行動原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ <STRONG>動作</STRONG>]，再按一下 [ <STRONG>指派原則</STRONG>]。



7.  在 [ **指派原則**] 的 [ **行動原則**] 底下，執行下列其中一項動作：
    

    > [!NOTE]  
    > 因為您可以在 [<STRONG>指派原則</STRONG>] 中設定多個原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。 不變更此設定，即可繼續沿用先前指派給使用者的原則。

    
      - 選取 **\<Automatic\>** 此項可讓 Lync Server 2013 自動選擇全域層級原則或網站層級原則（如果已定義）。
    
      - 在 [ **行動性原則** ] 頁面上，按一下您先前定義的每個使用者行動性原則的名稱。
        

        > [!TIP]  
        > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。



8.  完成時，請按一下 **[確定]**。

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 行動性原則

您可以使用 Windows PowerShell 和 **Grant-CsMobilityPolicy** Cmdlet 指派每個使用者的行動性原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>將每一使用者行動性原則指派給單一使用者

  - 下列命令會指派每個使用者的行動性原則 RedmondMobilityPolicy 至使用者 Ken Myer。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>將每一使用者行動性原則指派給多個使用者

  - 下列命令會將每個使用者的行動原則 RedmondMobilityPolicy 指派給目前已指派原則 NorthAmericaMobilityPolicy 的所有使用者。 如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>取消指派每個使用者的行動性原則

  - 下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者行動性原則。 一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。 網站原則優先順序高於全域原則。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))。

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定行動性原則](lync-server-2013-configuring-mobility-policy.md)

