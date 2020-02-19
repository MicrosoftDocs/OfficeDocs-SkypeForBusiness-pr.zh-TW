---
title: Lync Server 2013： 移除與裝置無關的裝置更新檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7089e3f055d89fb07215d119ea287471fd211de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>移除與 Lync Server 2013 中的裝置不相關的裝置更新檔案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

每次將新裝置更新上傳至系統時，就會建立對應的裝置更新規則。 根據預設，這些新的裝置更新規則會指派給 「 擱置 」 狀態。 這表示，規則可以下載並安裝在測試裝置，但無法在實際執行的裝置，可讓您測試之前讓使用者可用的更新。 根據測試，您可以接受部署或拒絕和刪除更新。 當您拒絕更新時，裝置更新會解除關聯其裝置更新規則。

<div>


使用 Windows PowerShell 和**清除 CsDeviceUpdateFile**指令程式可以移除不再與裝置相關聯的裝置更新檔。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


  - 例如，下列命令會移除任何裝置更新規則在 Web 伺服器 atl-cs-001.litwareinc.com 上的不再與裝置相關聯：
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

如需詳細資訊，請參閱[清除 CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

