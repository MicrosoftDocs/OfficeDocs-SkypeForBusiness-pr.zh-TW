---
title: Lync Server 2013：設定將要監視的 Lync Server 電腦
description: Lync Server 2013：設定將要監視的 Lync Server 電腦。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556829"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="0f134-103">設定將在 Lync Server 2013 中監控的 Lync Server 電腦</span><span class="sxs-lookup"><span data-stu-id="0f134-103">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f134-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0f134-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0f134-105">因為 Lync Server 2013 未使用 Microsoft Lync Server 2010 中所用的中央探索程式，所以您要監視的每一部 Lync Server 2013 電腦都必須能夠自我報告其存在於管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f134-105">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="0f134-106">若要做到這一點，您必須在要監視的每一部電腦上安裝 Operations Manager 代理程式檔案。</span><span class="sxs-lookup"><span data-stu-id="0f134-106">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="0f134-107">安裝代理程式檔案之後，您必須將電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="0f134-107">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="0f134-108">請注意，在這些電腦上安裝及設定 Lync Server 之後，應該執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="0f134-108">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

