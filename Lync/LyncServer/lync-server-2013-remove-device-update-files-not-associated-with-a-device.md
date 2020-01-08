---
title: Lync Server 2013：移除未與裝置相關聯的裝置更新檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>移除在 Lync Server 2013 中未與裝置相關聯的裝置更新檔案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

每次將新的裝置更新上傳到系統時，都會建立對應的裝置更新規則。 根據預設，這些新的裝置更新規則會指派至擱置狀態。 這表示這些規則可以在測試裝置上下載並安裝，而不是在生產裝置上，這可讓您在將更新提供給使用者之前先進行測試。 根據測試，您可以接受並部署或拒絕並刪除更新。 當您拒絕更新時，裝置更新會從它的裝置更新規則解除關聯。

<div>


您可以使用 Windows PowerShell 和**Clear CsDeviceUpdateFile** Cmdlet 來移除不再與裝置相關聯的裝置更新檔案。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


  - 例如，下列命令會移除 Web 服務器 atl-cs-001.litwareinc.com 上已不再與裝置相關聯的任何裝置更新規則：
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

如需詳細資訊，請參閱[Clear CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

