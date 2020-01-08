---
title: Lync Server 2013：移除裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中移除裝置更新規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

移除裝置更新規則會將它永久從裝置更新佇列中移除。

移除規則與從部署中的裝置或從測試裝置中卸載的更新有所不同。 若要從您的部署卸載核准的更新，請*還原*裝置更新規則。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原裝置更新規則](lync-server-2013-restore-a-device-update-rule.md)。 若要卸載您尚未從測試裝置核准的更新，請*重設*。 如需詳細資訊，請參閱[在 Lync Server 2013 中重設裝置更新規則](lync-server-2013-reset-a-device-update-rule.md)。

您可以使用 Lync Server [控制台] 或 [Windows PowerShell] 移除裝置更新規則。

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 移除裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 瀏覽按鈕。

4.  在 [**裝置更新**] 頁面上，執行下列其中一項操作：
    
      - 若要移除一個規則，請選取您要刪除的規則。
    
      - 若要移除所有規則，請按一下 [**編輯**] 功能表，然後按一下 [**全選**]。

5.  按一下 [**編輯**]，然後按一下 [**刪除**]。

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除裝置更新規則

您也可以使用 Windows PowerShell 與**Remove CsDeviceUpdateRule** Cmdlet 來移除裝置更新規則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>從伺服器移除單一裝置更新規則

  - 下列命令會從 dc2d9b1222ff9 上的網頁伺服器移除裝置更新規則 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>從伺服器移除所有裝置更新規則

  - 這個命令會從 atl-cs-001.litwareinc.com 的網頁伺服器移除所有裝置更新規則。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱[Remove CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中核准裝置更新規則](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

