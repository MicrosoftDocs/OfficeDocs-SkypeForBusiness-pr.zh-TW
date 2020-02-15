---
title: Lync Server 2013 支援大型會議
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
ms.openlocfilehash: 705640e7bd75292f67ed0dcd551db83a61dc7fd4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="05e91-102">Lync Server 2013 中的大型會議的支援</span><span class="sxs-lookup"><span data-stu-id="05e91-102">Support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05e91-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="05e91-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="05e91-104">Lync Server 2013 可支援使用會議最多 1000年參與者使用音訊/視訊 (A / V) 會議，包括共用 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="05e91-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="05e91-105">此支援要求的專屬集區設定為支援大型會議，並管理，以確保只將單一大型會議，一次主控的方式。</span><span class="sxs-lookup"><span data-stu-id="05e91-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="05e91-106">本節說明如何以支援大型會議使用專用的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="05e91-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="05e91-107">它說明延展性考量及實作需求的專屬集區，包括拓撲、 硬體、 軟體及組態需求。</span><span class="sxs-lookup"><span data-stu-id="05e91-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="05e91-108">它也提供一組的最佳作法建議支援大型會議、 測試方法及伺服器延展性測試進行 Lync Server 工程團隊，並支援常見問題的答案的結果的摘要大型會議。</span><span class="sxs-lookup"><span data-stu-id="05e91-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05e91-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="05e91-109">In This Section</span></span>

  - <span data-ttu-id="05e91-110">[在 [Lync Server 2013 會議延展性的概觀](lync-server-2013-conferencing-scalability-overview.md)</span><span class="sxs-lookup"><span data-stu-id="05e91-110">[Overview of conferencing scalability in Lync Server 2013](lync-server-2013-conferencing-scalability-overview.md)</span></span>

  - [<span data-ttu-id="05e91-111">支援使用 Lync Server 2013 的大型會議</span><span class="sxs-lookup"><span data-stu-id="05e91-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="05e91-112">Lync Server 2013 的大型會議支援常見問題集</span><span class="sxs-lookup"><span data-stu-id="05e91-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

