---
title: Lync Server 2013 會議負載分散
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
ms.openlocfilehash: 66cfdab2f59ca29022435a1f7863e8fce79075e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="d2f5c-102">Lync Server 2013 中的會議負載分散</span><span class="sxs-lookup"><span data-stu-id="d2f5c-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2f5c-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="d2f5c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d2f5c-104">與其他部分專用的會議解決方案，不同 Lync Server 架構是共用硬體模型。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="d2f5c-105">這表示相同的硬體可以由許多軟體元件共用，每個軟體元件都支援不同的即時通訊。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="d2f5c-106">每個類型的即時通訊都會在伺服器上放置特定的負載。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="d2f5c-107">比方說，前端伺服器可以執行的工作階段初始通訊協定 (SIP) 路由元件、 web 應用程式 （例如通訊錄搜尋）、 Web 會議服務、 A / V 會議服務、 企業語音應用程式 （例如會議服務員應用程式和回應群組應用程式），以及中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="d2f5c-108">一組的前端伺服器上的資料庫也提供儲存和處理的使用者、 連絡人、 目前狀態、 會議和語音路由的資料。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="d2f5c-109">藉由此硬體共用，元件、服務及處理程序就能競用 CPU 和記憶體資源，讓非會議的工作負載能夠在伺服器延展上產生直接影響。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="d2f5c-110">相較於其他硬體基於連接埠的會議解決方案，Lync Server 會議架構是非保留模型。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="d2f5c-111">當使用者排程會議時，Lync Server 會在會議的資料庫，其中儲存會議資料，但是不會保留的事先排定的會議任何硬體資源建立一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="d2f5c-112">相反地，Lync Server 具有內建負載平衡邏輯以動態方式配置前端伺服器上的會議資源，以分散負載同樣的每個跨所有前端伺服器集區中的方式。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="d2f5c-113">這樣會以有效率的方式來佈建和運用硬體資源，但在支援超大型會議時便是一項挑戰 (特別是在沒有適當規劃的情況下)。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="d2f5c-114">例如，接近其上方容量執行 Lync Server 2013 集區時，每個前端伺服器可能會主控大約 125 個平均大小會議。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="d2f5c-115">新增另一個小型的會議不會發生問題，但新增 1000 個使用者的會議就是問題，因為前端伺服器便可能無法以支援在同一時間為其他 125 個會議這類大型會議。</span><span class="sxs-lookup"><span data-stu-id="d2f5c-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

