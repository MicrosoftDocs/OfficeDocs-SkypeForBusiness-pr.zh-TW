---
title: 適用于大型會議的 Lync Server 2013 支援
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
ms.openlocfilehash: 1f177c7555a945be4e871c53e0e49a57c1a304a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519410"
---
# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="4b301-102">Lync Server 2013 中的大型會議支援</span><span class="sxs-lookup"><span data-stu-id="4b301-102">Support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b301-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4b301-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4b301-104">使用音訊/視頻 (A/V) 會議（包括共用 PowerPoint 簡報），Lync Server 2013 可支援最多1000位參與者的會議。</span><span class="sxs-lookup"><span data-stu-id="4b301-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="4b301-105">此支援需要設定為支援大型會議和管理的專屬集區，其方式是可確保一次只主控一項大型會議。</span><span class="sxs-lookup"><span data-stu-id="4b301-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="4b301-106">本節說明如何使用專用的 Lync Server 2013 集區支援大型會議。</span><span class="sxs-lookup"><span data-stu-id="4b301-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="4b301-107">本文說明專用集區的可伸縮性考慮和執行需求，包括拓撲、硬體、軟體及設定需求。</span><span class="sxs-lookup"><span data-stu-id="4b301-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="4b301-108">此外，它還提供一組最佳作法建議，以支援大型會議、Lync Server 工程設計小組所執行之伺服器可伸縮性測試的測試方法和結果摘要，以及有關大型會議支援的常見問題解答。</span><span class="sxs-lookup"><span data-stu-id="4b301-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4b301-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4b301-109">In This Section</span></span>

  - [<span data-ttu-id="4b301-110">Lync Server 2013 中的會議可擴充性綜述</span><span class="sxs-lookup"><span data-stu-id="4b301-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="4b301-111">使用 Lync Server 2013 支援大型會議</span><span class="sxs-lookup"><span data-stu-id="4b301-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="4b301-112">Lync Server 2013 的大型會議支援常見問題</span><span class="sxs-lookup"><span data-stu-id="4b301-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

