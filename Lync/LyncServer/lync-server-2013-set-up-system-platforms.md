---
title: Lync Server 2013：設定系統平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="e7c28-102">在 Lync Server 2013 中設定系統平台</span><span class="sxs-lookup"><span data-stu-id="e7c28-102">Set up system platforms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7c28-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e7c28-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e7c28-104">開始部署持久聊天伺服器之前，您必須在符合伺服器上系統需求的硬體上安裝所需的作業系統：</span><span class="sxs-lookup"><span data-stu-id="e7c28-104">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="e7c28-105">如需執行 Lync Server 2013、資料庫伺服器和檔案伺服器之伺服器支援的硬體相關詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c28-105">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="e7c28-106">如需支援的作業系統和資料庫軟體的詳細資訊，請參閱支援檔中的[Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c28-106">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="e7c28-107">如需有關 Windows 更新需求的詳細資訊，請參閱支援檔中的[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c28-107">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e7c28-108">永久聊天伺服器前端伺服器（ **PersistentChatService**）可在 Lync Server 2013 企業版文件庫中的一或多台獨立電腦上部署。</span><span class="sxs-lookup"><span data-stu-id="e7c28-108">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="e7c28-109">在 Lync Server Enterprise Edition 前端伺服器上無法 collocated。</span><span class="sxs-lookup"><span data-stu-id="e7c28-109">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="e7c28-110">引導程式可以部署持久聊天伺服器，就像其他 Lync 伺服器角色一樣。</span><span class="sxs-lookup"><span data-stu-id="e7c28-110">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="e7c28-111">[檔案**上傳]/[下載**] 與 [**聊天室管理**] 的持續聊天 Web 服務是在 Lync Server 2013 前端伺服器上部署的網頁元件。</span><span class="sxs-lookup"><span data-stu-id="e7c28-111">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="e7c28-112">單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7c28-112">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="e7c28-113">您可以使用最多4個作用中的持續聊天伺服器池，以支援總共80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="e7c28-113">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="e7c28-114">持續聊天后端伺服器（ **PersistentChatStore**）會儲存聊天室和類別。</span><span class="sxs-lookup"><span data-stu-id="e7c28-114">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="e7c28-115">我們建議您在企業版文件庫的專用 SQL Server 後端伺服器上安裝**PersistentChatStore** ;雖然我們支援 collocating Lync Server 2013 後端伺服器和**PersistentChatStore**在相同的 SQL Server 實例上。</span><span class="sxs-lookup"><span data-stu-id="e7c28-115">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="e7c28-116">如果您的組織需要合規性支援，您可以使用 [拓撲建立器] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="e7c28-116">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="e7c28-117">永久聊天伺服器合規性服務會安裝在與永久聊天伺服器前端伺服器相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="e7c28-117">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="e7c28-118">需要一個單獨的資料庫來實現合規性。</span><span class="sxs-lookup"><span data-stu-id="e7c28-118">A separate database is required for compliance.</span></span> <span data-ttu-id="e7c28-119">如需持續聊天伺服器的規範需求的詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c28-119">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="e7c28-120">每個拓撲至少都需要裝有 Lync Server 2013 的伺服器，以及已安裝 SQL Server database 軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7c28-120">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="e7c28-121">拓撲建造器支援多個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="e7c28-121">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="e7c28-122">遵循相同的部署指示來部署多個持續聊天伺服器池，就像您在部署檔中[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)的任何池一樣。</span><span class="sxs-lookup"><span data-stu-id="e7c28-122">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e7c28-123">您也可以使用 Lync Server 2013 標準版來部署持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7c28-123">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="e7c28-124">在這種情況下， **PersistentChatService**前端伺服器是在標準版 server 上 collocated，您可以在本機 SQL Server Express 實例上部署**PersistentChatStore**後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7c28-124">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7c28-125">我們不支援持續聊天伺服器&nbsp;標準版來提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="e7c28-125">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="e7c28-126">效能和比例會受到限制。</span><span class="sxs-lookup"><span data-stu-id="e7c28-126">Performance and scale will be limited.</span></span> <span data-ttu-id="e7c28-127">此外，我們只支援新的持續聊天&nbsp;伺服器標準版伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="e7c28-127">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="e7c28-128">我們不支援 Lync Server 2010 的升級，將 [群組聊天伺服器] 升級為 Lync Server&nbsp;2013 持續聊天&nbsp;伺服器標準版。</span><span class="sxs-lookup"><span data-stu-id="e7c28-128">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7c28-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="e7c28-129">See Also</span></span>


[<span data-ttu-id="e7c28-130">Lync Server 2013 中的其他伺服器支援和需求</span><span class="sxs-lookup"><span data-stu-id="e7c28-130">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="e7c28-131">Lync Server 2013 的受支援硬體</span><span class="sxs-lookup"><span data-stu-id="e7c28-131">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="e7c28-132">Lync Server 2013 中的伺服器軟體和基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="e7c28-132">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="e7c28-133">在 Lync Server 2013 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="e7c28-133">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="e7c28-134">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7c28-134">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

