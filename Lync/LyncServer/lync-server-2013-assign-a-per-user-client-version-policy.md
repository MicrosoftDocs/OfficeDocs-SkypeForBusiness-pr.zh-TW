---
title: Lync Server 2013：指派每位使用者的用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134459"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的用戶端版本原則

 


用戶端版本原則是您可以在 Lync Server 控制台中設定之使用者帳戶的其中一個個別設定。

部署一或多個個別使用者用戶端版本原則是選用的。 您也可以只部署全域層級用戶端版本原則，或網站層級或集區層級的用戶端版本原則。 如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。 若未指派任何特定的網站層級、集區層級或個別使用者原則，則允許以 Lync Server 2013 註冊的預設用戶端為全域層級用戶端版本原則中所定義的用戶端。

至少建立一個個別使用者用戶端版本原則後，請使用本主題中的程式來指派原則，以指定您要允許其註冊 Lync Server 的用戶端版本。

如需建立各使用者用戶端版本原則的詳細資訊，請參閱[指定可用於登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。

## <a name="to-assign-a-per-user-client-version-policy"></a>指派每位使用者的用戶端版本原則

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
    > 如果您要將相同的個別使用者用戶端版本原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。



7.  在 [**指派原則**] 的 [**用戶端版本原則**] 底下，執行下列其中一項操作：
    

    > [!NOTE]  
    > 因為有多種可使用 [<STRONG>指派原則</STRONG>] 對話方塊進行設定的原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。 不變更此設定，即可繼續沿用先前指派給使用者的原則。

    
      - 允許 Lync Server 自動選擇全域層級原則，或在網站層級原則或集區層級原則（如果有定義）。
    
      - 在 [**用戶端版本原則**] 頁面上，按一下您先前定義的每個使用者用戶端版本原則名稱。
        

        > [!TIP]  
        > 為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。



8.  完成時，請按一下 **[確定]**。

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 用戶端版本原則

您可以使用授與 Get-csclientversionpolicy 指令程式指派每個使用者的用戶端版本原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>將每一使用者用戶端版本原則指派給單一使用者

  - 下列命令會將每個使用者的用戶端版本原則 RedmondClientVersionPolicy 指派給使用者 Ken Myer。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>將每位使用者的用戶端版本原則指派給多位使用者

  - 此命令會將每位使用者的用戶端版本原則 RedmondClientVersionPolicy 指派給目前已指派語音原則 RedmondVoicePolicy 的所有使用者。 如需此命令中所使用之 Filter 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>取消指派每位使用者的用戶端版本原則

  - 下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者用戶端版本原則。 未指派每個使用者原則之後，Ken Myer 將會透過全域原則自動進行管理，其本機網站原則 (（如果有的話）) 或指派給他的註冊服務範圍原則。 服務範圍原則的優先順序高於任何網站原則，而網站原則則優先于全域原則。
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[get-csclientversionpolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中指派每一使用者原則](lync-server-2013-assigning-per-user-policies.md)  
[在 Lync Server 2013 中管理裝置、電話及用戶端應用程式](lync-server-2013-managing-devices-phones-and-client-applications.md)

