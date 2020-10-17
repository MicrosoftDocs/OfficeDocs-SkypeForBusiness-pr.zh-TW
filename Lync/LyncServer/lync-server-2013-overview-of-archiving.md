---
title: Lync Server 2013：封存簡介
description: Lync Server 2013：封存簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548d82d6731fd28fafbde5816a7a0dc77a1fcc02
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566799"
---
# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="34994-103">Lync Server 2013 中的封存綜述</span><span class="sxs-lookup"><span data-stu-id="34994-103">Overview of Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34994-104">_**主題上次修改日期：** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="34994-104">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="34994-105">在 Lync Server 2013 中封存可讓您封存透過 Lync Server 2013 傳送的通訊。</span><span class="sxs-lookup"><span data-stu-id="34994-105">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="34994-106">您可以在初始 Lync Server 2013 部署中執行封存，也可以將其新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="34994-106">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="34994-107">若要使用 Lync Server 2013 封存資料庫 (SQL Server 資料庫) 以儲存封存資料，您可以使用拓撲產生器將資料庫新增至您的拓撲，然後再發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="34994-107">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="34994-108">如果您的所有使用者都位於 Exchange 2013，而且其信箱置於 In-Place 保留狀態，您就不需要更新拓撲，但只需要啟用 Microsoft Exchange 整合，即可將封存的資料儲存在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="34994-108">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="34994-109">當您執行封存時，可將其設定為指定封存的內容。</span><span class="sxs-lookup"><span data-stu-id="34994-109">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="34994-110">根據預設，不會封存任何專案。</span><span class="sxs-lookup"><span data-stu-id="34994-110">By default, nothing is archived.</span></span> <span data-ttu-id="34994-111">您可以使用 Lync Server 2013 控制台來設定及管理封存。</span><span class="sxs-lookup"><span data-stu-id="34994-111">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="34994-112">您可以對內部通訊、外部通訊或兩者執行封存。</span><span class="sxs-lookup"><span data-stu-id="34994-112">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="34994-113">您可以設定整個組織的封存設定，也可以為特定網站、特定集區和特定使用者和使用者群組設定封存設定。</span><span class="sxs-lookup"><span data-stu-id="34994-113">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="34994-114">如需決定組織的適當選項的詳細資訊，請參閱規劃檔中的在 [Lync Server 2013 中定義您的封存需求](lync-server-2013-defining-your-requirements-for-archiving.md) 。</span><span class="sxs-lookup"><span data-stu-id="34994-114">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="34994-115">如需如何執行封存原則及設定的詳細資訊，以及哪些資訊可或無法封存的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存 [在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="34994-115">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

