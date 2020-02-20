---
title: Lync Server 2013： 監控 IIS 要求的追蹤記錄檔
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
ms.openlocfilehash: b1377eabd4ffc199fe7a9014d28f153aba10afa4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="16e2e-102">監控 IIS 要求在 Lync Server 2013 中的追蹤記錄檔</span><span class="sxs-lookup"><span data-stu-id="16e2e-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16e2e-103">_**上次修改主題：** 2013年-02-14_</span><span class="sxs-lookup"><span data-stu-id="16e2e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="16e2e-104">當您啟用網際網路資訊服務 (IIS) 要求的追蹤的 Lync Server Mobility Service (Mcx) 時，所產生的記錄檔可能會耗用最多三個 gb 的每日的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="16e2e-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="16e2e-105">依預設會啟用 IIS 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="16e2e-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="16e2e-106">您應該監視前端伺服器若要確定，他們無法執行磁碟空間不足。</span><span class="sxs-lookup"><span data-stu-id="16e2e-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="16e2e-107">根據預設，IIS 會儲存在 %systemdrive%並記錄檔\\inetpub\\記錄\\記錄檔。</span><span class="sxs-lookup"><span data-stu-id="16e2e-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="16e2e-108">若要關閉 IIS 要求的追蹤整部伺服器，請在命令列中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="16e2e-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="16e2e-109">如需**httpLogging**命令的詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927)。</span><span class="sxs-lookup"><span data-stu-id="16e2e-109">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

