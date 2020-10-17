---
title: Lync Server 2013： Persistent Chat Server 的技術需求
description: Lync Server 2013： Persistent Chat Server 的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905563f31de36d41a48aea5fb8db3cfde9cb2434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550329"
---
# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="61d59-103">Lync Server 2013 中 Persistent Chat Server 的技術需求</span><span class="sxs-lookup"><span data-stu-id="61d59-103">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61d59-104">_**主題上次修改日期：** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="61d59-104">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="61d59-105">主控 Persistent Chat Server 的每一部電腦都必須能夠存取現有的 Lync Server 2013 拓撲，其元件如下：</span><span class="sxs-lookup"><span data-stu-id="61d59-105">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="61d59-106">**Lync server 2013，前端伺服器。**  前端伺服器是會話初始通訊協定 (SIP) 路由的基礎，它使得執行持續聊天伺服器的電腦與可能的持久聊天功能之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="61d59-106">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="61d59-107">在您開始部署 Persistent Chat Server 之前，請根據組織的需要，確認 Lync Server 2013、Standard Edition 或 Lync Server 前端集區和任何其他執行 Lync Server 之內部電腦的部署。</span><span class="sxs-lookup"><span data-stu-id="61d59-107">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="61d59-108">下列各節說明 Persistent Chat Server 和儲存 Persistent Chat 資料之資料庫的特定需求。</span><span class="sxs-lookup"><span data-stu-id="61d59-108">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="61d59-109">Persistent Chat Server 需求</span><span class="sxs-lookup"><span data-stu-id="61d59-109">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="61d59-110">如需部署 Lync Server 的建議硬體及最新版本的 Persistent Chat Server 的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="61d59-110">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="61d59-111">如需有關 Lync Server 和 Persistent Chat Server 之伺服器和工具作業系統支援的詳細資訊，請參閱支援檔中的 [伺服器和工具作業系統支援（Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="61d59-111">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="61d59-112">如需部署 Persistent Chat Server 所需之其他軟體的詳細資訊，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="61d59-112">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="61d59-113">Persistent Chat Server 軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="61d59-113">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61d59-114">軟體</span><span class="sxs-lookup"><span data-stu-id="61d59-114">Software</span></span></th>
<th><span data-ttu-id="61d59-115">描述</span><span class="sxs-lookup"><span data-stu-id="61d59-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61d59-116">訊息佇列</span><span class="sxs-lookup"><span data-stu-id="61d59-116">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="61d59-117">由 Persistent Chat Server 和 Persistent Chat 規章服務（若已部署）使用。</span><span class="sxs-lookup"><span data-stu-id="61d59-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="61d59-118">Persistent Chat Server 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="61d59-118">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="61d59-119">Persistent Chat Server 會使用 Persistent Chat 資料庫來儲存聊天記錄、設定和使用者布建資料。</span><span class="sxs-lookup"><span data-stu-id="61d59-119">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="61d59-120">另外，它會使用 Persistent 聊天室規範資料庫來儲存規範資料。</span><span class="sxs-lookup"><span data-stu-id="61d59-120">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61d59-121">Persistent Chat database (mgc) 與規範資料庫 (mgccomp) 可以位於相同的 SQL Server 實例或不同的 SQL Server 上。</span><span class="sxs-lookup"><span data-stu-id="61d59-121">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="61d59-122">若要準備資料庫伺服器平臺，請確定每一部電腦都符合硬體需求，然後安裝必要軟體。</span><span class="sxs-lookup"><span data-stu-id="61d59-122">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="61d59-123">Persistent Chat 資料庫伺服器的伺服器平臺需要與 Lync Server 後端資料庫伺服器相同的硬體。</span><span class="sxs-lookup"><span data-stu-id="61d59-123">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="61d59-124">如需詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="61d59-124">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="61d59-125">在資料庫伺服器上，確定已安裝下列其中一個軟體應用程式：</span><span class="sxs-lookup"><span data-stu-id="61d59-125">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="61d59-126">Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="61d59-126">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="61d59-127">如需如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱《安裝 SQL Server 2012 》 [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559) 。</span><span class="sxs-lookup"><span data-stu-id="61d59-127">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="61d59-128">Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="61d59-128">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="61d59-129">如需如何安裝 Microsoft SQL Server 2008 R2 的詳細資訊，請參閱《 SQL server 安裝 (SQL Server 2008 R2) 》 [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702) 。</span><span class="sxs-lookup"><span data-stu-id="61d59-129">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="61d59-130">Persistent Chat Server 憑證需求</span><span class="sxs-lookup"><span data-stu-id="61d59-130">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="61d59-131">如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="61d59-131">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

