---
title: Lync Server 2013：新的封存功能
description: Lync Server 2013：新的封存功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561349"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="d7d26-103">Lync Server 2013 中的新封存功能</span><span class="sxs-lookup"><span data-stu-id="d7d26-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7d26-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="d7d26-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="d7d26-105">Lync Server 2013 中的封存可封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="d7d26-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="d7d26-106">對等立即訊息</span><span class="sxs-lookup"><span data-stu-id="d7d26-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="d7d26-107">會議 (參加多方立即訊息) </span><span class="sxs-lookup"><span data-stu-id="d7d26-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="d7d26-108">會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)</span><span class="sxs-lookup"><span data-stu-id="d7d26-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="d7d26-109">此外，Lync Server 2013 中的封存功能提供了可提升部署和作業效率的新功能。</span><span class="sxs-lookup"><span data-stu-id="d7d26-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="d7d26-110">這些新功能包括：</span><span class="sxs-lookup"><span data-stu-id="d7d26-110">These new features consist of:</span></span>

  - <span data-ttu-id="d7d26-111">**前端伺服器上封存的組合。**    Lync Server 2013 沒有個別的封存伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="d7d26-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="d7d26-112">封存是可在企業版部署的所有前端伺服器上，以及 Standard Edition server 上的所有前端伺服器上可用的選用功能，可針對集區或網站執行設定。</span><span class="sxs-lookup"><span data-stu-id="d7d26-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="d7d26-113">**Microsoft Exchange 整合。**    當您部署封存時，您可以將資料儲存區與現有的 Exchange 2013 儲存區整合，以用於所有位於 Exchange 2013 的使用者，並將其信箱置於 In-Place 保留狀態，所以您不需要部署個別的 SQL Server 資料庫來封存 Lync 資料。</span><span class="sxs-lookup"><span data-stu-id="d7d26-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="d7d26-114">如果您沒有 Exchange 2013 部署，或您不想要將其與其整合，或者如果您有任何 Lync 2013 使用者未裝載在 Exchange 2013 上，且其信箱置於 In-Place 保留狀態，您可以使用 SQL Server 來儲存不同的封存資料庫，使其具有 Lync 通訊的封存資料。</span><span class="sxs-lookup"><span data-stu-id="d7d26-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="d7d26-115">如果您想要對部分但不是部署中的所有使用者使用 Microsoft Exchange 整合，您可以使用 Microsoft Exchange 整合和 Lync Server 2013 封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="d7d26-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="d7d26-116">如需 In-Place 保留的詳細資訊，請參閱的「In-Place 保留」 [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) 。</span><span class="sxs-lookup"><span data-stu-id="d7d26-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="d7d26-117">**SQL 存放區鏡像。**    當您部署封存時，您可以啟用封存資料庫的 SQL Server 資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="d7d26-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="d7d26-118">**白板和投票的封存。**    封存的會議內容現在包含在會議期間共用的白板和投票。</span><span class="sxs-lookup"><span data-stu-id="d7d26-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="d7d26-119">不會封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="d7d26-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="d7d26-120">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="d7d26-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="d7d26-121">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="d7d26-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="d7d26-122">對等立即訊息與會議的應用程式共用</span><span class="sxs-lookup"><span data-stu-id="d7d26-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d7d26-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d7d26-123">See Also</span></span>


[<span data-ttu-id="d7d26-124">在 Lync Server 2013 中規劃封存</span><span class="sxs-lookup"><span data-stu-id="d7d26-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

