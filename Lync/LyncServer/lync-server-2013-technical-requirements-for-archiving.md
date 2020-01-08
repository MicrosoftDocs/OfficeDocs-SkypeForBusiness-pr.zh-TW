---
title: Lync Server 2013：存檔的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="6ca67-102">Lync Server 2013 中的存檔技術需求</span><span class="sxs-lookup"><span data-stu-id="6ca67-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ca67-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6ca67-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6ca67-104">Lync Server 2013 的技術需求包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6ca67-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="6ca67-105">基礎結構需求。</span><span class="sxs-lookup"><span data-stu-id="6ca67-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="6ca67-106">必須針對歸檔進行安裝的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="6ca67-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="6ca67-107">存檔的資料儲存需求。</span><span class="sxs-lookup"><span data-stu-id="6ca67-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="6ca67-108">針對您的封存部署調整需求和考慮。</span><span class="sxs-lookup"><span data-stu-id="6ca67-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="6ca67-109">歸檔資料庫的效能需求和考慮。</span><span class="sxs-lookup"><span data-stu-id="6ca67-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ca67-110">在此 Lync Server 2013 版本中無法使用縮放和效能資訊。</span><span class="sxs-lookup"><span data-stu-id="6ca67-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="6ca67-111">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="6ca67-111">Infrastructure Requirements</span></span>

<span data-ttu-id="6ca67-112">Lync Server 2013 的 [存檔基礎結構需求] 與「部署 Lync Server 2013」是一樣的。</span><span class="sxs-lookup"><span data-stu-id="6ca67-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="6ca67-113">如需詳細資訊，請參閱在規劃檔中[判斷 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ca67-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="6ca67-114">歸檔必備元件</span><span class="sxs-lookup"><span data-stu-id="6ca67-114">Archiving Prerequisites</span></span>

<span data-ttu-id="6ca67-115">Lync Server 2013 簡化了存檔的先決條件，原因如下：</span><span class="sxs-lookup"><span data-stu-id="6ca67-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="6ca67-116">封存伺服器已不再是伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="6ca67-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="6ca67-117">相反地，整合的資料收集代理程式是在 pool 及標準版伺服器的前端伺服器上執行，以捕獲資料以供歸檔，因此您不需要設定個別的系統平臺來進行封存。</span><span class="sxs-lookup"><span data-stu-id="6ca67-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="6ca67-118">封存使用 Lync Server 2013 檔案儲存空間來暫時儲存會議內容檔案，因此您不需要設定個別的檔案存放區來進行封存。</span><span class="sxs-lookup"><span data-stu-id="6ca67-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="6ca67-119">在 Lync Server 2013 中，不需要訊息佇列。</span><span class="sxs-lookup"><span data-stu-id="6ca67-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="6ca67-120">存檔的資料存儲需求</span><span class="sxs-lookup"><span data-stu-id="6ca67-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="6ca67-121">此外，您還需要設定儲存空間的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6ca67-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="6ca67-122">這包括下列其中一項或兩項：</span><span class="sxs-lookup"><span data-stu-id="6ca67-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="6ca67-123">**Microsoft Exchange 儲存空間**。</span><span class="sxs-lookup"><span data-stu-id="6ca67-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="6ca67-124">會議內容檔案（例如 PowerPoint 簡報）會封存為附件。</span><span class="sxs-lookup"><span data-stu-id="6ca67-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="6ca67-125">如果您想要使用 Microsoft Exchange 整合，讓 Lync 封存資料與 Exchange 合規性資料儲存在一起，您必須使用 Exchange 2013 進行 Exchange 部署，並確保最大儲存空間大小支援儲存會議內容檔案。</span><span class="sxs-lookup"><span data-stu-id="6ca67-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="6ca67-126">如果您使用 Microsoft Exchange 整合選項部署歸檔，Lync 封存資料只會儲存在 Exchange 2013 伺服器上的使用者的 Exchange 2013 合規性資料。</span><span class="sxs-lookup"><span data-stu-id="6ca67-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="6ca67-127">您必須先部署 Exchange 2013，然後才能使用 Microsoft Exchange 整合選項部署並啟用封存。</span><span class="sxs-lookup"><span data-stu-id="6ca67-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="6ca67-128">如果您選擇使用 Exchange 2013 儲存空間，就不需要部署個別的 SQL Server 資料庫來進行封存，除非您有不是駐留在 Exchange 2013 伺服器上的 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="6ca67-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="6ca67-129">**用於存檔的 SQL Server 資料庫儲存空間**。</span><span class="sxs-lookup"><span data-stu-id="6ca67-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="6ca67-130">若要支援不是託管于 Exchange 2013 伺服器的使用者，或者不想使用 Microsoft Exchange 整合選項，您必須使用 SQL Server 資料庫部署封存儲存空間。</span><span class="sxs-lookup"><span data-stu-id="6ca67-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="6ca67-131">Lync Server 2013 支援下列64位版本的 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="6ca67-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="6ca67-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6ca67-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="6ca67-133">Microsoft SQL Server 2008 R2 標準版</span><span class="sxs-lookup"><span data-stu-id="6ca67-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="6ca67-134">Microsoft SQL Server 2012 企業版</span><span class="sxs-lookup"><span data-stu-id="6ca67-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="6ca67-135">Microsoft SQL Server 2012 標準版</span><span class="sxs-lookup"><span data-stu-id="6ca67-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ca67-136">Microsoft SQL Server 2008 R2 Express 及 Microsoft SQL Server 2012 Express 不支援封存。</span><span class="sxs-lookup"><span data-stu-id="6ca67-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="6ca67-137">不支援32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6ca67-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="6ca67-138">如需其他 SQL Server 需求與限制，請參閱在規劃檔或支援檔中的<A href="lync-server-2013-database-software-support.md">Lync Server 2013 資料庫軟體支援</A>。</span><span class="sxs-lookup"><span data-stu-id="6ca67-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="6ca67-139">您必須先設定 SQL Server 平臺，然後才能部署並啟用封存。</span><span class="sxs-lookup"><span data-stu-id="6ca67-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="6ca67-140">如果要用來發佈拓朴的帳戶具有適當的管理員權力和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。</span><span class="sxs-lookup"><span data-stu-id="6ca67-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="6ca67-141">您也可以日後建立資料庫，包括安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ca67-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="6ca67-142">如需 SQL Server 的詳細資料，請參閱 SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)技術中心（位於）。</span><span class="sxs-lookup"><span data-stu-id="6ca67-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

