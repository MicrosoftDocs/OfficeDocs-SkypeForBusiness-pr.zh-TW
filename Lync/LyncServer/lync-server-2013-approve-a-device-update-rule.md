---
title: Lync Server 2013：核准裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>在 Lync Server 2013 中核准裝置更新規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

匯入裝置更新規則之後，就會將它安裝在您的測試裝置上。 如果您的測試成功，而您想要推出貴組織的更新，請使用 Lync Server [控制台] 或 [Windows PowerShell] 進行核准。

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 核准裝置更新規則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在 [**裝置更新**] 頁面上，執行下列其中一項操作：
    
      - 若要核准一個規則，請選取該規則。
    
      - 若要核准所有規則，請按一下 [**編輯**]，然後按一下 [**全選**]。

4.  按一下 [**動作**]，然後按一下 [**核准**]。

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 核准裝置更新規則

您也可以使用 Windows PowerShell 和**核准 CsDeviceUpdateRule** Cmdlet 來核准裝置更新規則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>核准單一裝置更新規則

  - 下列命令可核准裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 在網頁 server atl-cs-001.litwareinc.com 上找到：
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>核准多個裝置更新規則

  - 這個命令會核准 Microsoft 品牌裝置的所有裝置更新規則：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

如需詳細資訊，請參閱[核准 CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中匯入裝置更新規則](lync-server-2013-import-device-update-rules.md)  
[在 Lync Server 2013 中還原裝置更新規則](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

