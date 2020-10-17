---
title: Lync Server 2013：指派每一使用者的封存原則
description: Lync Server 2013：指派每一使用者的封存原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559989"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每一使用者的封存原則

 


封存原則是您可以在 Lync Server 2013 控制台中設定之使用者帳戶的個別設定之一。

部署一或多個個別使用者封存原則是選用的。 您也可以只部署全域層級的封存原則或網站層級的封存原則。 如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。 若未指派任何特定的網站層級或個別使用者原則，則封存需求會自動預設為全域層級會議原則中所定義的使用者。

在建立至少一個個別使用者封存原則之後，請使用本主題中的程式來指派原則，以適當指定特定使用者的內部通訊、外部通訊或兩者，是否會由伺服器進行封存。

如需建立個別使用者封存原則的詳細資訊，請參閱 [在 Lync Server 2013 中建立封存原則，以針對特定網站或使用者啟用或停用內部或外部通訊](lync-server-2013-create-archiving-policy-sites-users.md)的封存。

## <a name="to-assign-a-per-user-archiving-policy"></a>指派每位使用者的封存原則

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
    > 如果您要將相同的個別使用者封存原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ <STRONG>動作</STRONG>]，再按一下 [ <STRONG>指派原則</STRONG>]。



7.  在 [ **指派原則**] 的 [封存 **原則**] 下，執行下列其中一項動作：
    

    > [!NOTE]  
    > 因為有多種可使用 [<STRONG>指派原則</STRONG>] 對話方塊進行設定的原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。 不變更此設定，即可繼續沿用先前指派給使用者的原則。

    
      - 允許 Lync Server 2013 自動選擇全域層級原則，或網站層級原則（如果已定義）。
    
      - 按一下您先前在 [封存 **原則** ] 頁面上定義之每一使用者封存原則的名稱。
        

        > [!TIP]  
        > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。



8.  完成時，請按一下 **[確定]**。

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 封存原則

您可以使用 Windows PowerShell 和 **Grant-CsArchivingPolicy** Cmdlet 指派每個使用者的封存原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>將每一使用者封存原則指派給單一使用者

  - 下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>將每一使用者封存原則指派給多個使用者

  - 這個命令會將個別使用者的封存原則 RedmondArchivingPolicy 指派給所有在註冊機構集區 atl-cs-001.litwareinc.com 上擁有帳戶的使用者。 如需此命令中所使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>取消指派個別使用者的封存原則

  - 下列命令解除指派任何先前指派給 Ken Myer 的個別使用者封存原則。一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。網站原則優先順序高於全域原則。
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立封存原則，以針對特定網站或使用者啟用或停用內部或外部通訊的封存](lync-server-2013-create-archiving-policy-sites-users.md)  


[在 Lync Server 2013 中指派每一使用者原則](lync-server-2013-assigning-per-user-policies.md)

