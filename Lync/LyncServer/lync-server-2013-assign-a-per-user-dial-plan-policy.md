---
title: Lync Server 2013：指派每個使用者的撥號對應表原則
description: Lync Server 2013：指派每個使用者的撥號對應表原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 654c1f15ccb1efa4d1aa35d957df7a2654fa41d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559899"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的撥號對應表原則

 


若要為企業語音使用者或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指定撥號對應表。 當您未明確指派現有的每一使用者撥號對應表時，使用者帳戶會自動使用全域撥號對應表或網站層級撥號對應表（如果有的話）。 如果您想要針對所有已啟用 Enterprise Voice 的使用者使用全域或網站撥號對應表，您可以略過本節。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台指派撥號對應表

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。

5.  在表格中，按一下您要指派撥號對應表的使用者帳戶。

6.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

7.  在 [ **編輯 Lync Server 使用者** ] 頁面的 [ **電話**語音] 下，按一下 [ **企業語音**]。

8.  按一下 [撥號對應表 **原則**]，然後選擇想要的撥號對應表。

9.  按一下 **[認可]**。

如需設定撥號對應表的詳細資訊，請參閱在 [Lync Server 2013 中設定撥號](lync-server-2013-configuring-dial-plans.md) 對應表主題。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派 Per-User 撥號對應表

您可以將每一使用者撥號對應表指派給 Windows PowerShell 和 **get-csdialplan** Cmdlet。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>將每一使用者撥號對應表指派給單一使用者

  - 下列命令會指派每個使用者的撥號對應表 RedmondDialPlan 給使用者 Ken Myer。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>將每一使用者撥號對應表指派給多位使用者

  - 這個命令會將個別使用者撥號對應表 RedmondDialPlan 指派給 Redmond 的城市中的所有使用者。 如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>取消指派個別使用者撥號對應表

  - 下列命令 unassigns 先前指派給 Ken Myer 的任何每一使用者撥號對應表。 未指派每個使用者的撥號對應表後，Ken Myer 會透過全域撥號對應表自動管理，他的本機網站撥號對應表 (若存在) 或指派給其註冊機構或 PSTN 閘道的服務範圍撥號對應表。 服務範圍撥號對應表優先于任何網站撥號對應表，而網站撥號對應表的優先順序會高於全域撥號對應表。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱 [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) Cmdlet 的 [說明] 主題。

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)  
[啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-user-accounts-enabled-for-lync-server.md)

