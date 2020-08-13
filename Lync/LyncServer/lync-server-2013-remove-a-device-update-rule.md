---
title: Lync Server 2013：移除裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13b639e6541478874e80ab632b2ee231ea65151d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中移除裝置更新規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

移除裝置更新規則會將其永久移出裝置更新佇列。

移除規則與從您部署中的裝置卸載或從測試裝置卸載的更新不同。 若要從您的部署卸載已核准的更新，請 *還原* 裝置更新規則。 如需詳細資訊，請參閱 [Restore a Device Update rule In Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)。 若要卸載尚未從測試裝置核准的更新，請將其 *重設* 。 如需詳細資訊，請參閱 [Reset a Device Update rule In Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md)。

您可以使用 Lync Server 控制台或 Windows PowerShell 移除裝置更新規則。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台移除裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **裝置更新** ] 導覽按鈕。

4.  在 [ **裝置更新** ] 頁面上，執行下列其中一項操作：
    
      - 若要移除一個規則，請選取您要刪除的規則。
    
      - 若要移除所有規則，請按一下 [ **編輯** ] 功能表，然後按一下 [ **全選**]。

5.  按一下 [ **編輯**]，然後按一下 [ **刪除**]。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除裝置更新規則

您也可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** Cmdlet 來移除裝置更新規則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>從伺服器移除單一裝置更新規則

  - 下列命令會從上上的網頁伺服器中移除裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>從伺服器移除所有裝置更新規則

  - 此命令會從 atl-cs-001.litwareinc.com 上的網頁伺服器中移除所有裝置更新規則。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[核准 Lync Server 2013 中的裝置更新規則](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

