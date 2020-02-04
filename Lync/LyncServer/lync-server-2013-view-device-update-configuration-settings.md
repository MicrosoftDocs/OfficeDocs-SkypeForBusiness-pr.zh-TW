---
title: Lync Server 2013：檢視裝置更新組態設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01edeb2d40fae7b82ac35fb5561a1332f67c9e11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中檢視裝置更新組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以使用 Lync Server 管理命令介面和**CsDeviceUpdateConfiguration** Cmdlet （您可以從 lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行）來查看裝置更新服務設定設定。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>


  - 若要查看所有語音路由的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：
    
        Get-CsDeviceUpdateConfiguration
    
    這個命令會傳回如下所示的資訊：
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

如需此 Cmdlet 的詳細資訊，請參閱[取得 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

