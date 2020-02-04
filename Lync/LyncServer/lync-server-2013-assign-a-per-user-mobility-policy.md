---
title: Lync Server 2013：指派每個使用者的行動原則
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
ms.openlocfilehash: 20b5929959e87f4a39c69ab09f7836a471e16b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722843"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的行動原則

 


行動原則是您可以在 Lync Server [控制台] 或 [Lync Server 管理命令介面] 中設定的使用者帳戶個人設定之一。

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>使用 Lync Server [控制台] 指派每使用者行動原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  使用下列其中一種方法來尋找使用者：
    
      - 在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。
    
      - 如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。

5.  可選指定額外的搜尋準則以縮小結果範圍：
    
    1.  按一下 [**新增篩選**]。
    
    2.  輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。
    
    3.  在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。
    
    4.  根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。
        

        > [!TIP]  
        > 若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。

    
    5.  按一下 [**尋找**]。

6.  在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。
    

    > [!TIP]  
    > 如果您想要將相同的每個使用者行動策略套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。



7.  在 [**指派原則**] 的 [**行動原則**] 底下，執行下列其中一項操作：
    

    > [!NOTE]  
    > 因為您可以在<STRONG>指派原則</STRONG>中設定多個原則， <STRONG> &lt; &gt; </STRONG>所以預設會為對話方塊中的每個原則選取 [保留為]。 針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。

    
      - 選取** \<[\>自動**]，讓 Lync Server 2013 自動選擇 [全域階層原則] 或 [（如果已定義）] 網站層級原則。
    
      - 按一下您先前在 [**行動原則**] 頁面上定義的每個使用者行動原則的名稱。
        

        > [!TIP]  
        > 若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （<STRONG>查看</STRONG>），以查看原則中定義的使用者權利和許可權。



8.  完成後，請按一下 **[確定]**。

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的移動策略

您可以使用 Windows PowerShell 和**Grant CsMobilityPolicy** Cmdlet 指派每個使用者的行動原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>將每個使用者的行動策略指派給單一使用者

  - 下列命令會將每個使用者的移動策略 RedmondMobilityPolicy 指派給使用者 Ken Myer。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>將每個使用者的行動策略指派給多個使用者

  - 下列命令會將每個使用者的行動原則 RedmondMobilityPolicy 指派給目前已獲指派 policy NorthAmericaMobilityPolicy 的所有使用者。 如需此命令中使用之篩選參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>若要取消指派每個使用者的行動原則

  - 下列命令會以前指派給 Ken Myer 的任何每使用者行動原則。 未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。 網站原則的優先順序高於全域原則。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[授與 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\))。

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定行動原則](lync-server-2013-configuring-mobility-policy.md)

