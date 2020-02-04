---
title: Lync Server 2013：監視 IIS 要求追蹤記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d29082fd4f2e988d586501d4d867be0dc23a0c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="06f17-102">在 Lync Server 2013 中監視 IIS 要求追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="06f17-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06f17-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="06f17-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="06f17-104">當您針對 Lync Server 行動服務（Mcx）啟用 Internet Information Services （IIS）要求追蹤時，產生的記錄檔案每天最多可以消耗 3 gb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="06f17-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="06f17-105">預設會啟用 IIS 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="06f17-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="06f17-106">您應該監視前端伺服器，以確保它們不會耗盡磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="06f17-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="06f17-107">根據預設，IIS 會將記錄檔儲存在% SystemDrive\\%\\inetpub\\記錄日誌檔。</span><span class="sxs-lookup"><span data-stu-id="06f17-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="06f17-108">若要關閉整個伺服器的 IIS 要求追蹤，請在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="06f17-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="06f17-109">如需**HTTPLogging**命令的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)請參閱。</span><span class="sxs-lookup"><span data-stu-id="06f17-109">For details about the **httpLogging** command, see [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

