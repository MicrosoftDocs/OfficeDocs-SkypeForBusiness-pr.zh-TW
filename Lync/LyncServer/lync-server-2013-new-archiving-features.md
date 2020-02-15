---
title: Lync Server 2013： 新的封存功能
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
ms.openlocfilehash: bf8c632fa5858eaf35464e9885e65343bc699e54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="21c31-102">Lync Server 2013 中的新封存功能</span><span class="sxs-lookup"><span data-stu-id="21c31-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21c31-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="21c31-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="21c31-104">封存的 Lync Server 2013 可以封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="21c31-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="21c31-105">對等立即訊息</span><span class="sxs-lookup"><span data-stu-id="21c31-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="21c31-106">多方立即訊息的會議 （會議）</span><span class="sxs-lookup"><span data-stu-id="21c31-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="21c31-107">會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)</span><span class="sxs-lookup"><span data-stu-id="21c31-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="21c31-108">此外，封存 Lync Server 2013 中的提供改善部署和作業效率的新功能。</span><span class="sxs-lookup"><span data-stu-id="21c31-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="21c31-109">這些新功能所組成：</span><span class="sxs-lookup"><span data-stu-id="21c31-109">These new features consist of:</span></span>

  - <span data-ttu-id="21c31-110">**組合的封存在前端伺服器上。**   Lync Server 2013 沒有個別封存伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="21c31-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="21c31-111">封存是選擇性功能可在所有前端伺服器在 Enterprise Edition 部署中，以及在 Standard Edition 伺服器，可實作針對集區或網站上使用。</span><span class="sxs-lookup"><span data-stu-id="21c31-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="21c31-112">**Microsoft Exchange 整合。**   當您部署封存，您可以在整合針對與您現有的 Exchange 2013 儲存區位於 Exchange 2013 的所有使用者的封存資料存放區，他們的信箱放在原有範圍暫止時，因此您不需要部署個別的 SQL Server 資料庫，要封存 Lync 資料。</span><span class="sxs-lookup"><span data-stu-id="21c31-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="21c31-113">如果您沒有 Exchange 2013 部署中，如果您不想整合，或如果您有任何 Lync 2013 的使用者不位於 Exchange 2013 與他們放入原有範圍暫止的信箱，您可以使用 SQL Server 來儲存部署個別封存資料庫e 封存資料從 Lync 通訊。</span><span class="sxs-lookup"><span data-stu-id="21c31-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="21c31-114">如果您想要使用 Microsoft Exchange 整合的部署中的部分，但並非所有使用者，您可以使用 Microsoft Exchange 整合和 Lync Server 2013 封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="21c31-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="21c31-115">如需原有範圍暫止的詳細資訊，請參閱 「 就地保留 」，在[http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)。</span><span class="sxs-lookup"><span data-stu-id="21c31-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="21c31-116">**SQL 存放區鏡像。**   當您部署封存時，您可以啟用為封存資料庫的 SQL Server 資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="21c31-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="21c31-117">**白板與投票的封存。**   封存會議內容現在包括白板與投票，在會議期間共用。</span><span class="sxs-lookup"><span data-stu-id="21c31-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="21c31-118">不會封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="21c31-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="21c31-119">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="21c31-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="21c31-120">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="21c31-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="21c31-121">應用程式共用的端對端即時訊息與會議</span><span class="sxs-lookup"><span data-stu-id="21c31-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="21c31-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21c31-122">See Also</span></span>


[<span data-ttu-id="21c31-123">規劃 Lync Server 2013 中的封存</span><span class="sxs-lookup"><span data-stu-id="21c31-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

