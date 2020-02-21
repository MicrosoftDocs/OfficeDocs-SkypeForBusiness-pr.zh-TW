---
title: Lync Server 2013： 匯入裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5436be837af75045d75b8feee31886aaaf324f0b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>匯入 Lync Server 2013 中的裝置更新規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-23_

只能透過使用 Windows PowerShell 和**Import-csdeviceupdate** cmdlet 可以匯入裝置更新規則。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>若要匯入裝置更新規則的單一網頁伺服器

  - 下列命令會將裝置更新規則匯入網頁伺服器 atl-edge-001.litwareinc.com-atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>若要匯入裝置更新規則至所有網頁伺服器

  - 在這個範例中，在組織中部署的所有網頁伺服器都會匯都入裝置更新規則。 此命令可工作時，該資料夾的\\ \\atl-fs-001.litwareinc.com\\更新必須是共用，並可供所有網頁伺服器。
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

如需詳細資訊，請參閱[Import-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[檢視 Lync Server 2013 中的裝置更新規則的相關資訊](lync-server-2013-view-information-about-device-update-rules.md)  
[核准 Lync Server 2013 中的裝置更新規則](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

