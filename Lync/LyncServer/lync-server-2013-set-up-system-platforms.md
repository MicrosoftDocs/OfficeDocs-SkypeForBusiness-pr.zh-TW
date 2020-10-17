---
title: Lync Server 2013：設定系統平臺
description: Lync Server 2013：設定系統平臺。
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
ms.openlocfilehash: bd02c519d5632b7aa5732fbd9b880f7d1084b50f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550439"
---
# <a name="set-up-system-platforms-in-lync-server-2013"></a><span data-ttu-id="f4a30-103">在 Lync Server 2013 中設定系統平臺</span><span class="sxs-lookup"><span data-stu-id="f4a30-103">Set up system platforms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4a30-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f4a30-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f4a30-105">開始部署 Persistent Chat Server 之前，您必須在符合伺服器上系統需求的硬體上安裝必要的作業系統：</span><span class="sxs-lookup"><span data-stu-id="f4a30-105">Before starting the deployment of Persistent Chat Server, you must install the required operating system on hardware that meets system requirements on servers:</span></span>

<span data-ttu-id="f4a30-106">如需執行 Lync Server 2013、資料庫伺服器及檔案伺服器之伺服器支援硬體的詳細資訊，請參閱支援檔中的 [支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md) 。</span><span class="sxs-lookup"><span data-stu-id="f4a30-106">For details about supported hardware for servers running Lync Server 2013, database servers, and file servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span> <span data-ttu-id="f4a30-107">如需支援的作業系統和資料庫軟體的詳細資訊，請參閱支援檔中的 [伺服器軟體和基礎結構支援（Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="f4a30-107">For details about supported operating systems and database software, see [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="f4a30-108">如需 Windows 更新需求的詳細資訊，請參閱支援檔中的 [其他伺服器支援和 Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) 中的需求。</span><span class="sxs-lookup"><span data-stu-id="f4a30-108">For details about Windows update requirements, see [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f4a30-109">Persistent Chat Server 前端伺服器（ **PersistentChatService**）可以部署在 Lync Server 2013 Enterprise Edition 集區中的一或多個獨立電腦上。</span><span class="sxs-lookup"><span data-stu-id="f4a30-109">The Persistent Chat Server Front End Server, **PersistentChatService**, can be deployed on one or more stand-alone computers in a Lync Server 2013 Enterprise Edition pool.</span></span> <span data-ttu-id="f4a30-110">它們無法在 Lync Server Enterprise Edition 前端伺服器上組合。</span><span class="sxs-lookup"><span data-stu-id="f4a30-110">They cannot be collocated on the Lync Server Enterprise Edition Front End Servers.</span></span> <span data-ttu-id="f4a30-111">與其他 Lync Server 角色一樣，引導程式可以部署 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="f4a30-111">Persistent Chat Server can be deployed by the Bootstrapper, just like other Lync Server roles.</span></span> <span data-ttu-id="f4a30-112">在 Lync Server 2013 前端伺服器上部署的「 **檔上傳**」和「 **持久聊天 web 服務」的聊天室管理** 的 persistent chat web 服務是部署在 Lync Server 前端伺服器上的網頁元件。</span><span class="sxs-lookup"><span data-stu-id="f4a30-112">The **Persistent Chat Web Services for File Upload/Download**, and **Persistent Chat Web Services for Chat Room Management** are web components deployed on the Lync Server 2013 Front End Servers.</span></span>

<span data-ttu-id="f4a30-113">單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="f4a30-113">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="f4a30-114">您可以有最多4個作用中前端的持久聊天伺服器集區，支援總80000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="f4a30-114">You can have a Persistent Chat Server pool with up to 4 active front ends supporting a total of 80,000 concurrent users.</span></span> <span data-ttu-id="f4a30-115">Persistent Chat 後端伺服器（ **PersistentChatStore**）會儲存聊天室和類別。</span><span class="sxs-lookup"><span data-stu-id="f4a30-115">The Persistent Chat Back End Server, **PersistentChatStore**, stores the chat rooms and categories.</span></span> <span data-ttu-id="f4a30-116">建議您在 Enterprise Edition 集區的專用 SQL Server 後端伺服器上安裝 **PersistentChatStore** ;雖然我們支援在相同的 SQL Server 實例上組合 Lync Server 2013 後端伺服器和 **PersistentChatStore** 。</span><span class="sxs-lookup"><span data-stu-id="f4a30-116">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server in your Enterprise Edition pool; although we support collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance.</span></span>

<span data-ttu-id="f4a30-117">如果您的組織需要規範支援，您可以使用拓撲產生器進行安裝。</span><span class="sxs-lookup"><span data-stu-id="f4a30-117">If your organization requires compliance support, you can install it by using Topology Builder.</span></span> <span data-ttu-id="f4a30-118">Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="f4a30-118">The Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="f4a30-119">合規性需要個別的資料庫。</span><span class="sxs-lookup"><span data-stu-id="f4a30-119">A separate database is required for compliance.</span></span> <span data-ttu-id="f4a30-120">如需有關 Persistent Chat Server 之規範需求的詳細資訊，請參閱規劃檔中的在 [Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="f4a30-120">For details about compliance requirements for Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

<span data-ttu-id="f4a30-121">每個拓撲至少需要安裝 Lync Server 2013 的伺服器，以及已安裝 SQL Server 資料庫軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4a30-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span> <span data-ttu-id="f4a30-122">拓撲產生器支援多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="f4a30-122">Topology Builder supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="f4a30-123">依照部署檔中部署 [Lync server 2013](lync-server-2013-deploying-lync-server.md) 的任何集區的方式，遵循相同的部署指示來部署多個持久聊天伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="f4a30-123">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool from [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f4a30-124">您也可以使用 Lync Server 2013 Standard Edition 部署 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="f4a30-124">You can also deploy Persistent Chat Server with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="f4a30-125">在此情況下， **PersistentChatService** 前端伺服器在 Standard Edition Server 上是組合的，您可以在本機 SQL Server Express 實例上部署 **PersistentChatStore** 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4a30-125">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition server, and you can deploy the **PersistentChatStore** Back End Server on the local SQL Server Express instance.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f4a30-126">我們不支援 Persistent Chat Server &nbsp; Standard Edition 高可用性。</span><span class="sxs-lookup"><span data-stu-id="f4a30-126">We do not support Persistent Chat Server&nbsp;Standard Edition for high availability.</span></span> <span data-ttu-id="f4a30-127">效能及規模將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="f4a30-127">Performance and scale will be limited.</span></span> <span data-ttu-id="f4a30-128">此外，我們僅支援新的持久聊天伺服器 &nbsp; Standard Edition server 部署。</span><span class="sxs-lookup"><span data-stu-id="f4a30-128">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server deployments.</span></span> <span data-ttu-id="f4a30-129">我們不支援將 Lync Server 2010，Group Chat Server 升級成 Lync Server 2013 &nbsp; Persistent Chat server &nbsp; Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="f4a30-129">We do not support an upgrade of Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4a30-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4a30-130">See Also</span></span>


[<span data-ttu-id="f4a30-131">Lync Server 2013 中的其他伺服器支援和需求</span><span class="sxs-lookup"><span data-stu-id="f4a30-131">Additional server support and requirements in Lync Server 2013</span></span>](lync-server-2013-additional-server-support-and-requirements.md)  


[<span data-ttu-id="f4a30-132">Lync Server 2013 的支援硬體</span><span class="sxs-lookup"><span data-stu-id="f4a30-132">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)  
[<span data-ttu-id="f4a30-133">Lync Server 2013 中的伺服器軟體和基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="f4a30-133">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)  
[<span data-ttu-id="f4a30-134">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="f4a30-134">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
[<span data-ttu-id="f4a30-135">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4a30-135">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

