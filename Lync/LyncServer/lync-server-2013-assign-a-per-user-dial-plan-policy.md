---
title: Lync Server 2013：指派每個使用者的撥號方案原則
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722963"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的撥號方案原則

 


若要為企業語音或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指派撥號方案。 如果您不明確指派現有的每個使用者撥號方案，使用者帳戶就會自動使用全域撥號方案，或（如果有的話）。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站撥號方案，您可以略過本節。

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台指派撥號方案

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5.  在表格中，按一下您要指派撥號方案的使用者帳戶。

6.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

7.  在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**] 底下，按一下 [**企業語音**]。

8.  按一下 [**撥號計畫原則**]，然後選擇想要的撥號方案。

9.  按一下 [認可]****。

如需有關設定撥號方案的詳細資訊，請參閱在[Lync Server 2013 中設定撥號方案](lync-server-2013-configuring-dial-plans.md)主題。

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派每個使用者的撥號方案

您可以將每個使用者的撥號方案指派給 Windows PowerShell 和**Grant CsdialPlan** Cmdlet。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>若要將每個使用者的撥號方案指派給單一使用者

  - 下列命令會將每個使用者的撥號方案 RedmondDialPlan 指派給使用者 Ken Myer。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>若要將每個使用者的撥號方案指派給多個使用者

  - 這個命令會將每個使用者的撥號方案 RedmondDialPlan 指派給在雷德蒙者所在城市的所有使用者。 如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>取消指派每個使用者的撥號方案

  - 下列命令會先前指派給 Ken Myer 的任何每使用者撥號方案。 未指派每個使用者的撥號方案後，會使用全域撥號方案、其當地網站撥號方案（如果有的話），或指派給其註冊機構或 PSTN 閘道的服務範圍撥號方案，來自動管理 Ken Myer。 服務範圍撥號方案的優先順序高於任何網站的撥號方案，而且網站撥號計畫的優先順序高於全域撥號方案。
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

如需詳細資訊，請參閱[Grant CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) Cmdlet 的說明主題。

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)  
[已啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-user-accounts-enabled-for-lync-server.md)

