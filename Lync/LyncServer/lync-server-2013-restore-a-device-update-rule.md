---
title: Lync Server 2013：還原裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c6b6084577979264648e706c70fb6387b47971
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511630"
---
# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中還原裝置更新規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

若要從部署中的裝置卸載裝置更新規則，請將其還原。 還原裝置更新規則會同時卸載此更新，並重新安裝該規則的先前版本。

您可以使用 Lync Server 控制台或 Windows PowerShell 還原裝置更新規則。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台還原裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **裝置更新** ] 導覽按鈕。

4.  在 [ **裝置更新** ] 頁面上，執行下列其中一項操作：
    
      - 若要還原一個規則，請選取該規則。
    
      - 若要還原所有規則，請按一下 [ **編輯**]，然後按一下 [ **全選**]。

5.  按一下 [ **動作** ] 功能表，然後按一下 [ **還原**]。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 還原裝置更新規則

您也可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** Cmdlet 來還原裝置更新規則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>在伺服器上還原單一裝置更新規則

  - 下列命令會在網頁伺服器上上還原裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com：
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>在伺服器上還原所有裝置更新規則

  - 這個命令會還原網頁伺服器 atl-cs-001.litwareinc.com 上的所有裝置更新規則：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

