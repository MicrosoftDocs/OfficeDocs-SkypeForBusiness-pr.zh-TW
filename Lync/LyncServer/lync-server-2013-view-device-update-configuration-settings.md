---
title: Lync Server 2013：查看裝置更新設定
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
ms.openlocfilehash: 7f7f3d6ae80aa83d7edcf6d64a13c4cbda90c9ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506450"
---
# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="41047-102">在 Lync Server 2013 中查看裝置更新設定設定</span><span class="sxs-lookup"><span data-stu-id="41047-102">View Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41047-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="41047-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="41047-104">您可以使用 Lync Server 管理命令介面和 **Get-CsDeviceUpdateConfiguration** Cmdlet 來查看裝置更新服務設定設定，您可以從 lync Server 2013 管理命令介面或 Windows 的遠端會話執行該指令程式 PowerShell</span><span class="sxs-lookup"><span data-stu-id="41047-104">You can view the Device Update Service configuration settings by using Lync Server Management Shell and the **Get-CsDeviceUpdateConfiguration** cmdlet, which you can run from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41047-105">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="41047-105">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>


  - <span data-ttu-id="41047-106">若要查看所有語音路由的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="41047-106">To view information about all your voice routes, type the following command in the Lync Server Management Shell and press Enter:</span></span>
    
        Get-CsDeviceUpdateConfiguration
    
    <span data-ttu-id="41047-107">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="41047-107">This command returns information similar to the following:</span></span>
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

<span data-ttu-id="41047-108">如需此 Cmdlet 的詳細資訊，請參閱 [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration)的 Help 主題。</span><span class="sxs-lookup"><span data-stu-id="41047-108">For details about this cmdlet, see Help topic at [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

