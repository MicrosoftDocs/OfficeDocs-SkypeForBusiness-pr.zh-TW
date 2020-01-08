---
title: Lync Server 2013：持久聊天伺服器的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ee68d-102">Lync Server 2013 中持續聊天伺服器的技術需求</span><span class="sxs-lookup"><span data-stu-id="ee68d-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee68d-103">_**主題上次修改日期：** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="ee68d-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="ee68d-104">每個主持持久聊天伺服器的電腦都必須具備使用下列元件的現有 Lync Server 2013 拓撲的存取權：</span><span class="sxs-lookup"><span data-stu-id="ee68d-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="ee68d-105">**Lync Server 2013，前部端伺服器。** 前端伺服器是會話初始通訊協定（SIP）路由的基礎，可讓執行持續聊天伺服器的電腦與持久的聊天功能都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="ee68d-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="ee68d-106">開始部署持續聊天伺服器之前，請先確認 Lync Server 2013、標準版或 Lync Server 前端池，以及任何其他執行 Lync Server 的內部電腦（視您的組織而定）。</span><span class="sxs-lookup"><span data-stu-id="ee68d-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="ee68d-107">下列各節說明持久聊天伺服器和儲存持續聊天資料之資料庫的特定需求。</span><span class="sxs-lookup"><span data-stu-id="ee68d-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="ee68d-108">持續聊天伺服器需求</span><span class="sxs-lookup"><span data-stu-id="ee68d-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="ee68d-109">如需有關部署 Lync Server 及最新版本持久性聊天伺服器的建議硬體的詳細資料，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="ee68d-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ee68d-110">如需有關 Lync Server 與永久聊天伺服器支援的伺服器和工具作業系統的詳細資訊，請參閱支援檔中的[Lync server 2013 中的 [伺服器與工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)]。</span><span class="sxs-lookup"><span data-stu-id="ee68d-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ee68d-111">如需部署持久聊天伺服器所需的其他軟體的詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="ee68d-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="ee68d-112">持續聊天伺服器軟體必備元件</span><span class="sxs-lookup"><span data-stu-id="ee68d-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee68d-113">軟體</span><span class="sxs-lookup"><span data-stu-id="ee68d-113">Software</span></span></th>
<th><span data-ttu-id="ee68d-114">描述</span><span class="sxs-lookup"><span data-stu-id="ee68d-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee68d-115">訊息佇列</span><span class="sxs-lookup"><span data-stu-id="ee68d-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="ee68d-116">持續聊天伺服器和持續聊天相容性服務（如果已部署）使用。</span><span class="sxs-lookup"><span data-stu-id="ee68d-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="ee68d-117">持續聊天伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="ee68d-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="ee68d-118">持續聊天伺服器會使用持續聊天資料庫來儲存聊天記錄、設定和使用者供給資料。</span><span class="sxs-lookup"><span data-stu-id="ee68d-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="ee68d-119">您也可以使用持續性聊天規範資料庫來儲存合規性資料。</span><span class="sxs-lookup"><span data-stu-id="ee68d-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee68d-120">持久聊天資料庫（mgc）和規範資料庫（mgccomp）可位於相同的 SQL Server 實例或不同的 SQL 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ee68d-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="ee68d-121">若要準備資料庫伺服器平臺，請確定每個電腦都符合硬體需求，然後再安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="ee68d-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="ee68d-122">持續聊天資料庫伺服器的伺服器平臺需要與 Lync Server 後端資料庫伺服器相同的硬體。</span><span class="sxs-lookup"><span data-stu-id="ee68d-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="ee68d-123">如需詳細資訊，請參閱支援檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="ee68d-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ee68d-124">在資料庫伺服器上，請確定已安裝下列其中一個軟體應用程式：</span><span class="sxs-lookup"><span data-stu-id="ee68d-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="ee68d-125">Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="ee68d-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="ee68d-126">如需有關如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱「安裝 SQL Server [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)2012」。</span><span class="sxs-lookup"><span data-stu-id="ee68d-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="ee68d-127">Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="ee68d-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="ee68d-128">如需有關如何安裝 Microsoft SQL Server 2008 R2 的詳細資料，請參閱「SQL Server 安裝（SQL Server 2008 R2 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)）」。</span><span class="sxs-lookup"><span data-stu-id="ee68d-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="ee68d-129">持續聊天伺服器憑證需求</span><span class="sxs-lookup"><span data-stu-id="ee68d-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="ee68d-130">如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。</span><span class="sxs-lookup"><span data-stu-id="ee68d-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

