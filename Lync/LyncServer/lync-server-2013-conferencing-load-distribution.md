---
title: Lync Server 2013 會議載入發佈
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="0c07a-102">在 Lync Server 2013 中的會議載入發佈</span><span class="sxs-lookup"><span data-stu-id="0c07a-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c07a-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0c07a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0c07a-104">與其他一些專用會議解決方案不同，Lync Server 架構是共用硬體模型。</span><span class="sxs-lookup"><span data-stu-id="0c07a-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="0c07a-105">這表示同一個硬體是由許多軟體元件所共用，每個元件都支援不同的即時通訊。</span><span class="sxs-lookup"><span data-stu-id="0c07a-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="0c07a-106">每個即時通訊類型都會將伺服器上的特定負載放在一起。</span><span class="sxs-lookup"><span data-stu-id="0c07a-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="0c07a-107">例如，前端伺服器可以執行會話初始通訊協定（SIP）路由元件、web 應用程式（例如通訊錄搜尋）、Web 會議服務、A/V 會議服務、企業語音應用程式（例如，會議助理應用程式與回應群組應用程式），以及中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0c07a-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="0c07a-108">前端伺服器上的一組資料庫也會提供儲存與處理，以供使用者、連絡人、目前狀態、會議及語音路由資料使用。</span><span class="sxs-lookup"><span data-stu-id="0c07a-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="0c07a-109">針對 CPU 和記憶體資源而言，有這種硬體共用、元件、服務和程式可爭用，所以非會議工作負載會直接影響伺服器的規模。</span><span class="sxs-lookup"><span data-stu-id="0c07a-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="0c07a-110">與其他硬體埠式會議解決方案相比，Lync Server 會議架構是無保留模型。</span><span class="sxs-lookup"><span data-stu-id="0c07a-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="0c07a-111">當使用者排程會議時，Lync Server 會在會議資料庫中建立一筆記錄，該記錄會儲存會議資料，但不會提前為排程的會議保留任何硬體資源。</span><span class="sxs-lookup"><span data-stu-id="0c07a-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="0c07a-112">相反地，Lync Server 有內建的負載平衡邏輯，可在前端伺服器上以平均分佈負載的方式，在池中的所有前端伺服器上平均分配會議資源。</span><span class="sxs-lookup"><span data-stu-id="0c07a-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="0c07a-113">這會有效地提供和使用硬體資源，但在支援超大型會議時，特別是不需要進行適當規劃的挑戰。</span><span class="sxs-lookup"><span data-stu-id="0c07a-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="0c07a-114">例如，當 Lync Server 2013 池執行接近其最上層容量時，每個前端伺服器都可能主持大約125平均大小的會議。</span><span class="sxs-lookup"><span data-stu-id="0c07a-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="0c07a-115">新增另一個小型會議並不是問題，但為1000使用者新增會議時可能會有問題，因為前端伺服器可能無法與其他125會議同時支援這類大型會議。</span><span class="sxs-lookup"><span data-stu-id="0c07a-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

