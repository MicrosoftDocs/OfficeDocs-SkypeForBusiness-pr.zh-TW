---
title: Lync Server 2013：移除與裝置無關聯的裝置更新檔
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
ms.openlocfilehash: a21ef2e9dae4c09ce975bd048f628930cd3dfeda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536440"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>在 Lync Server 2013 中移除與裝置無關聯的裝置更新檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

每次將新裝置更新上傳至系統時，就會建立對應的裝置更新規則。 依預設，這些新的裝置更新規則會指派給擱置狀態。 這表示可以在測試裝置上下載和安裝規則，而不是在生產裝置上進行測試，這樣可讓您先測試更新，然後再讓使用者使用。 根據測試，您可以接受並部署或拒絕和刪除更新。 當您拒絕更新時，裝置更新會與其裝置更新規則解除關聯。

<div>


使用 Windows PowerShell 和 **CsDeviceUpdateFile** 指令程式，可以移除與裝置不再相關聯的裝置更新檔案。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>


  - 例如，下列命令會移除網頁伺服器 atl-cs-001.litwareinc.com 上任何已不再與裝置相關聯的裝置更新規則：
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

如需詳細資訊，請參閱 Help 主題 for the [CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) Cmdlet。

</div>

</div>

<span> </span>

</div>

</div>

</div>

