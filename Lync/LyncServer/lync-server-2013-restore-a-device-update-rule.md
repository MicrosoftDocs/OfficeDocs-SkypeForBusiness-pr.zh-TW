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
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中還原裝置更新規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

若要從部署中的裝置卸載裝置更新規則，請將它還原。 還原裝置更新規則時，會卸載此更新，並重新安裝該規則的前一個版本。

您可以使用 Lync Server [控制台] 或 [Windows PowerShell] 來還原裝置更新規則。

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 還原裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 瀏覽按鈕。

4.  在 [**裝置更新**] 頁面上，執行下列其中一項操作：
    
      - 若要還原一個規則，請選取該規則。
    
      - 若要還原所有規則，請按一下 [**編輯**]，然後按一下 [**全選**]。

5.  按一下 [**動作**] 功能表，然後按一下 [**還原**]。

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來還原裝置更新規則

您也可以使用 Windows PowerShell 和**Restore CsDeviceUpdateRule** Cmdlet 來還原裝置更新規則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>在伺服器上還原單一裝置更新規則

  - 下列命令會在 Web 服務器 dc2d9b1222ff9 上還原裝置更新規則 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>在伺服器上還原所有裝置更新規則

  - 這個命令會還原 web 伺服器 atl-cs-001.litwareinc.com 上的所有裝置更新規則：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱[Restore CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

