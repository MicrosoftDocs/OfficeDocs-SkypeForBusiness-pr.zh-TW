---
title: Lync Server 2013：監控 IIS 要求的追蹤記錄檔
description: Lync Server 2013：監控 IIS 要求的追蹤記錄檔。
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
ms.openlocfilehash: 09692b79b1cc59ad18ad520885c0a795736b53cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569949"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="dea2b-103">在 Lync Server 2013 中監控 IIS 要求的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="dea2b-103">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dea2b-104">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="dea2b-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="dea2b-105">當您啟用 Internet Information Services (的) 要求追蹤 Lync Server 行動性服務 (Mcx) 時，所產生的記錄檔可能會消耗最多三 gb 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="dea2b-105">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="dea2b-106">預設會啟用 IIS 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="dea2b-106">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="dea2b-107">您應該監視前端伺服器，確定其磁碟空間不足。</span><span class="sxs-lookup"><span data-stu-id="dea2b-107">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="dea2b-108">根據預設，IIS 會將記錄檔儲存在% 系統磁片% inetpub 記錄檔日誌檔 \\ \\ \\ 。</span><span class="sxs-lookup"><span data-stu-id="dea2b-108">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="dea2b-109">若要關閉整個伺服器的 IIS 要求追蹤，請在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="dea2b-109">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="dea2b-110">如需 **HTTPLogging** 命令的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) 。</span><span class="sxs-lookup"><span data-stu-id="dea2b-110">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

