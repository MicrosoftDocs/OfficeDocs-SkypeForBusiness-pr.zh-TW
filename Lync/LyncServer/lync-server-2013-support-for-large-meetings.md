---
title: Lync Server 2013 大型會議支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a8da2c58cc650fa0d2ddb7fe71ba62b4b29af9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="f5db4-102">Lync Server 2013 中的大型會議支援</span><span class="sxs-lookup"><span data-stu-id="f5db4-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5db4-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f5db4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f5db4-104">Lync Server 2013 可支援最多1000個參與者使用音訊/視頻（A/V）會議的會議，包括共用 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="f5db4-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="f5db4-105">此支援要求將專用的池設定為支援大型會議，並以確保一次只主持單一大型會議的方式來管理。</span><span class="sxs-lookup"><span data-stu-id="f5db4-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="f5db4-106">本節說明如何使用專用的 Lync Server 2013 池支援大型會議。</span><span class="sxs-lookup"><span data-stu-id="f5db4-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="f5db4-107">它描述可伸縮性考慮，以及專用池的實現需求，包括拓撲、硬體、軟體及設定需求。</span><span class="sxs-lookup"><span data-stu-id="f5db4-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="f5db4-108">它也提供支援大型會議的一組最佳做法建議，此摘要說明 Lync Server 工程小組所進行的伺服器伸縮性測試的測試方法和結果，以及支援的常見問題的解答大型會議。</span><span class="sxs-lookup"><span data-stu-id="f5db4-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5db4-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="f5db4-109">In This Section</span></span>

  - [<span data-ttu-id="f5db4-110">Lync Server 2013 中的會議可伸縮性概覽</span><span class="sxs-lookup"><span data-stu-id="f5db4-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="f5db4-111">使用 Lync Server 2013 支援大型會議</span><span class="sxs-lookup"><span data-stu-id="f5db4-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="f5db4-112">大型會議支援 Lync Server 2013 的常見問題</span><span class="sxs-lookup"><span data-stu-id="f5db4-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

