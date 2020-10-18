---
title: Lync Server 2013：查看裝置更新設定
description: Lync Server 2013：查看裝置更新設定。
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
ms.openlocfilehash: e686562d99da679149b6b977bd3cb9feb5c9a7fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579419"
---
# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看裝置更新設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以使用 Lync Server 管理命令介面和 **Get-CsDeviceUpdateConfiguration** Cmdlet 來查看裝置更新服務設定設定，您可以從 lync Server 2013 管理命令介面或 Windows 的遠端會話執行該指令程式 PowerShell

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

<div>


<div>


  - 若要查看所有語音路由的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：
    
        Get-CsDeviceUpdateConfiguration
    
    此命令會傳回與下列相似的資訊：
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

如需此 Cmdlet 的詳細資訊，請參閱 [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)的 Help 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

