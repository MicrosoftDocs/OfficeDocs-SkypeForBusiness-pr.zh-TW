---
title: Lync Server 2013：封存的技術需求
description: Lync Server 2013：封存的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6100753ad2c62424eb68c8c258094ba51848170e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577169"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="44718-103">在 Lync Server 2013 中封存的技術需求</span><span class="sxs-lookup"><span data-stu-id="44718-103">Technical requirements for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44718-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="44718-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="44718-105">Lync Server 2013 技術需求包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="44718-105">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="44718-106">基礎結構需求。</span><span class="sxs-lookup"><span data-stu-id="44718-106">Infrastructure requirements.</span></span>

  - <span data-ttu-id="44718-107">必須針對封存安裝的必要軟體。</span><span class="sxs-lookup"><span data-stu-id="44718-107">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="44718-108">封存的資料儲存需求。</span><span class="sxs-lookup"><span data-stu-id="44718-108">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="44718-109">封存部署的擴充需求和考慮。</span><span class="sxs-lookup"><span data-stu-id="44718-109">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="44718-110">封存資料庫的效能需求和考慮。</span><span class="sxs-lookup"><span data-stu-id="44718-110">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44718-111">在此 Lync Server 2013 版本中，無法使用調整和效能資訊。</span><span class="sxs-lookup"><span data-stu-id="44718-111">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="44718-112">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="44718-112">Infrastructure Requirements</span></span>

<span data-ttu-id="44718-113">Lync Server 2013 封存基礎結構需求與部署 Lync Server 2013 相同。</span><span class="sxs-lookup"><span data-stu-id="44718-113">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="44718-114">如需詳細資訊，請參閱規劃檔中的 [判斷您的 Lync Server 2013 基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="44718-114">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="44718-115">封存必要條件</span><span class="sxs-lookup"><span data-stu-id="44718-115">Archiving Prerequisites</span></span>

<span data-ttu-id="44718-116">Lync Server 2013 簡化封存的必要條件，原因如下：</span><span class="sxs-lookup"><span data-stu-id="44718-116">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="44718-117">封存伺服器不再是伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="44718-117">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="44718-118">相反地，整合的資料收集代理程式會在集區和 Standard Edition server 的前端伺服器上執行，以捕獲要封存的資料，因此您不會設定個別的系統平臺進行封存。</span><span class="sxs-lookup"><span data-stu-id="44718-118">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="44718-119">封存使用 Lync Server 2013 檔案存放區來暫時儲存會議內容檔案，所以您不會設定個別的檔案存放區進行封存。</span><span class="sxs-lookup"><span data-stu-id="44718-119">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="44718-120">在 Lync Server 2013 中，不需要訊息佇列。</span><span class="sxs-lookup"><span data-stu-id="44718-120">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="44718-121">封存的資料儲存需求</span><span class="sxs-lookup"><span data-stu-id="44718-121">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="44718-122">此外，您還需要設定封存儲存的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="44718-122">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="44718-123">這包括下列其中一項或兩項：</span><span class="sxs-lookup"><span data-stu-id="44718-123">This includes one or both of the following:</span></span>

  - <span data-ttu-id="44718-124">**Microsoft Exchange storage**。</span><span class="sxs-lookup"><span data-stu-id="44718-124">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="44718-125">會議內容檔案（例如 PowerPoint 簡報）會封存為附件。</span><span class="sxs-lookup"><span data-stu-id="44718-125">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="44718-126">如果您想要使用 Microsoft Exchange 整合，讓 Lync 封存資料儲存在 Exchange 合規性資料中，您必須使用 Exchange 2013 進行 Exchange 部署，並確保儲存大小上限支援會議內容檔案的儲存。</span><span class="sxs-lookup"><span data-stu-id="44718-126">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="44718-127">如果您使用 Microsoft Exchange 整合選項部署封存，則只有位於 Exchange 2013 伺服器上的使用者才會儲存 Lync 封存資料與 Exchange 2013 相容性資料。</span><span class="sxs-lookup"><span data-stu-id="44718-127">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="44718-128">您必須先部署 Exchange 2013，再使用 Microsoft Exchange 整合選項部署及啟用封存。</span><span class="sxs-lookup"><span data-stu-id="44718-128">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="44718-129">如果您選擇使用 Exchange 2013 儲存區，除非您有未位於 Exchange 2013 伺服器的 Lync 使用者，否則不需要部署個別的 SQL Server 資料庫進行封存。</span><span class="sxs-lookup"><span data-stu-id="44718-129">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="44718-130">**用於封存的 SQL Server 資料庫儲存區**。</span><span class="sxs-lookup"><span data-stu-id="44718-130">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="44718-131">若要支援非位於 Exchange 2013 伺服器的使用者，或是不想要使用 Microsoft Exchange 整合選項，您必須使用 SQL Server 資料庫部署封存儲存區。</span><span class="sxs-lookup"><span data-stu-id="44718-131">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="44718-132">Lync Server 2013 支援下列64位版本的 SQL Server：</span><span class="sxs-lookup"><span data-stu-id="44718-132">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="44718-133">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="44718-133">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="44718-134">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="44718-134">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="44718-135">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="44718-135">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="44718-136">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="44718-136">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44718-137">Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支援封存。</span><span class="sxs-lookup"><span data-stu-id="44718-137">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="44718-138">不支援32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="44718-138">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="44718-139">如需其他 SQL Server 需求和限制，請參閱規劃檔或支援檔中的 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 中的資料庫軟體支援</A> 。</span><span class="sxs-lookup"><span data-stu-id="44718-139">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="44718-140">在部署及啟用封存之前，您必須先設定 SQL Server 平臺。</span><span class="sxs-lookup"><span data-stu-id="44718-140">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="44718-141">若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。</span><span class="sxs-lookup"><span data-stu-id="44718-141">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="44718-142">您也可以之後再建立資料庫，包括在安裝程序中。</span><span class="sxs-lookup"><span data-stu-id="44718-142">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="44718-143">如需 SQL Server 的詳細資訊，請參閱 SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。</span><span class="sxs-lookup"><span data-stu-id="44718-143">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

