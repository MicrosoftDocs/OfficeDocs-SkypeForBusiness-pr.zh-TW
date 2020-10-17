---
title: 監控、啟動和停止 Persistent Chat service
description: 監控、啟動和停止 Persistent Chat service。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring, starting, and stopping the Persistent Chat services
ms:assetid: 05761d02-e7b5-494e-a58f-f3d213483035
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398105(v=OCS.15)
ms:contentKeyID: 48183291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54eaa7039cacbaa22320b20b7edeecfe2a13a0cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559319"
---
# <a name="monitoring-starting-and-stopping-the-persistent-chat-services-in-lync-server-2013"></a><span data-ttu-id="8b65d-103">在 Lync Server 2013 中監控、啟動和停止持續性聊天服務</span><span class="sxs-lookup"><span data-stu-id="8b65d-103">Monitoring, starting, and stopping the Persistent Chat services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b65d-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8b65d-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8b65d-105">Persistent Chat service 和 Persistent Chat 服務規範服務是 Lync Server 2013 拓撲的一部分，因此可以分別使用 Windows PowerShell Cmdlet、 **get-CsWindowsService**、 **stop-CsWindowsService**和 **start-CsWindowsService**加以監控、停止及啟動。</span><span class="sxs-lookup"><span data-stu-id="8b65d-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Lync Server 2013 topology and can therefore be monitored, stopped, and started by using the Windows PowerShell cmdlets, **get-CsWindowsService**, **stop-CsWindowsService**, and **start-CsWindowsService**, respectively.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

