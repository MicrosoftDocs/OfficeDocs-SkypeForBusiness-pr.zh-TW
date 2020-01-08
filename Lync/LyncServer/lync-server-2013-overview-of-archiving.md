---
title: Lync Server 2013：封存概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4aa88f94f0e32b35ab3fc5f71359e5a1c00d99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="d1799-102">Lync Server 2013 中的封存概觀</span><span class="sxs-lookup"><span data-stu-id="d1799-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1799-103">_**主題上次修改日期：** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="d1799-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="d1799-104">Lync Server 2013 中的 [封存] 可讓您封存透過 Lync Server 2013 傳送的通訊。</span><span class="sxs-lookup"><span data-stu-id="d1799-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="d1799-105">您可以在初始的 Lync Server 2013 部署中執行封存，也可以將它新增到現有的部署。</span><span class="sxs-lookup"><span data-stu-id="d1799-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="d1799-106">若要使用 Lync Server 2013 封存資料庫（SQL Server 資料庫）儲存存檔資料，您可以使用 [拓撲建立器] 將資料庫新增到拓撲結構，然後再次發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d1799-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="d1799-107">如果您的所有使用者都是以 Exchange 2013 為宿主，且其信箱放在就地保留中，您就不必更新您的拓撲，只需要啟用 Microsoft Exchange 整合，即可在 Exchange 2013 中儲存已歸檔的資料。</span><span class="sxs-lookup"><span data-stu-id="d1799-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="d1799-108">當您實現封存時，您可以設定存檔來指定要存檔的內容。</span><span class="sxs-lookup"><span data-stu-id="d1799-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="d1799-109">根據預設，沒有任何存檔。</span><span class="sxs-lookup"><span data-stu-id="d1799-109">By default, nothing is archived.</span></span> <span data-ttu-id="d1799-110">您可以使用 Lync Server 2013 的 [控制台] 來設定及管理存檔。</span><span class="sxs-lookup"><span data-stu-id="d1799-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d1799-111">您可以針對內部通訊、外部通訊或同時執行這兩者的歸檔。</span><span class="sxs-lookup"><span data-stu-id="d1799-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="d1799-112">您可以設定您整個組織的存檔設定，也可以將其設定為特定網站、特定的群組，以及特定的使用者和使用者組。</span><span class="sxs-lookup"><span data-stu-id="d1799-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="d1799-113">如需判斷貴組織適當選項的詳細資訊，請參閱在規劃檔中的[Lync Server 2013 中定義您的存檔需求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d1799-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="d1799-114">如需有關如何實施封存原則與設定的詳細資料，以及有關資訊可以或無法歸檔的詳細資訊，請參閱在規劃檔、部署檔或作業檔中的 [ [Lync Server 2013 存檔] 的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="d1799-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

