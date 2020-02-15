---
title: 封存的 Lync Server 2013： 概觀
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
ms.openlocfilehash: fe615b0bf434b0c87a452a35528aa565c85fe5d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="3fd1b-102">Lync Server 2013 中封存概觀</span><span class="sxs-lookup"><span data-stu-id="3fd1b-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fd1b-103">_**上次修改主題：** 2013年-09-30_</span><span class="sxs-lookup"><span data-stu-id="3fd1b-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="3fd1b-104">Lync Server 2013 中的封存可讓您封存透過 Lync Server 2013 傳送的通訊。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="3fd1b-105">您可以實作封存初始 Lync Server 2013 部署的一部分，或您可以將它新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="3fd1b-106">若要使用 Lync Server 2013 封存資料庫 （SQL Server 資料庫） 來儲存封存資料，您可以使用拓撲產生器將資料庫新增至您的拓撲，並再一次發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="3fd1b-107">如果您的所有使用者都位於 Exchange 2013，且其信箱放在原有範圍暫止，您不需要更新您的拓撲，但只需要啟用封存的資料儲存在 Exchange 2013 的 Microsoft Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="3fd1b-108">當您實作封存時，您將其設定為指定封存的項目。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="3fd1b-109">根據預設，不被封存。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-109">By default, nothing is archived.</span></span> <span data-ttu-id="3fd1b-110">您設定及管理封存使用 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="3fd1b-111">您可以實作封存內部通訊、 外部通訊或兩者。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="3fd1b-112">您可以設定封存設定整個組織和 （選擇性） 針對特定網站、 特定集區]，和特定使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="3fd1b-113">如需決定貴組織的適當選項的詳細資訊，請參閱規劃文件中的[定義 Lync Server 2013 中的封存需求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="3fd1b-114">詳細如何實作封存原則和設定，與何種資訊可以或無法封存相關的詳細資訊，請參閱[如何封存適用於 Lync Server 2013 中](lync-server-2013-how-archiving-works.md)規劃文件、 部署文件或作業文件中。</span><span class="sxs-lookup"><span data-stu-id="3fd1b-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

