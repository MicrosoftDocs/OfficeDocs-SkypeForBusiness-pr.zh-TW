---
title: 規劃 Persistent Chat Server 拓撲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：閱讀此主題以瞭解商務用 Skype 2015 Server 中的持久聊天伺服器元件和拓撲。
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825503"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="1e1cf-103">規劃 Persistent Chat Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="1e1cf-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="1e1cf-104">**摘要：** 閱讀此主題以瞭解商務用 Skype 2015 Server 中的持久聊天伺服器元件和拓撲。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1e1cf-105">Persistent Chat Server 同時支援單一伺服器和多部伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="1e1cf-106">您可以在商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition Server 上安裝 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1e1cf-107">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1e1cf-108">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="1e1cf-109">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1e1cf-110">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="1e1cf-111">Persistent Chat Server 元件</span><span class="sxs-lookup"><span data-stu-id="1e1cf-111">Persistent Chat Server components</span></span>

<span data-ttu-id="1e1cf-112">Persistent Chat Server 包含下列元件：</span><span class="sxs-lookup"><span data-stu-id="1e1cf-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="1e1cf-113">一或多部執行 Persistent Chat Server 的電腦，並提供下列服務：</span><span class="sxs-lookup"><span data-stu-id="1e1cf-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="1e1cf-114">Persistent Chat service</span><span class="sxs-lookup"><span data-stu-id="1e1cf-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="1e1cf-115">規範服務，會在啟用規範時開啟</span><span class="sxs-lookup"><span data-stu-id="1e1cf-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="1e1cf-116">如果使用鏡像，一或多部伺服器 (一或多部) 執行 SQL Server 後端資料庫，以主控存放聊天室內容、會議室及類別的持久聊天內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e1cf-117">後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的資訊。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="1e1cf-118">如果已啟用相容性，一或多部伺服器 (會使用鏡像) 執行 SQL Server 後端資料庫，以裝載 Persistent 聊天室規範資料庫，以儲存相容性事件和聊天內容的目的。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="1e1cf-119">如需有關 Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱商務用 skype server 2015 中 [的商務用 Skype server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 和 [硬體和軟體需求的](hardware-and-software-requirements.md)伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="1e1cf-120">Persistent Chat Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="1e1cf-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="1e1cf-121">您可以在單一伺服器或多部伺服器集區中部署 Persistent Chat Server，並使用單一集區或多集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="1e1cf-122">Persistent Chat Server 支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="1e1cf-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="1e1cf-123">前端伺服器上具有 Persistent Chat Server 組合的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="1e1cf-124">個別伺服器上具有 Persistent Chat Server 的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="1e1cf-125">在不同伺服器上具有單一持久聊天伺服器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="1e1cf-126">在不同伺服器上有多部 Persistent Chat Server 的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="1e1cf-127">雖然您可以在 Standard Edition Server 上部署 Persistent Chat Server，但請注意，效能及規模會受到影響，而高可用性不是選項。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="1e1cf-128">因此，建議您在 Standard Edition Server 上部署持續性聊天，主要是用來做為概念證明和評估目的。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="1e1cf-129">商務用 Skype Server 2015 可支援各種組合案例，為您提供彈性，您可以在一部伺服器上執行多個元件，以在一部伺服器)  (上執行多個元件，或在不同的伺服器上執行個別元件 (如果您有較大的組織需要可擴充性和效能) 。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="1e1cf-130">您應考慮可伸縮性因素，再決定是否要組合元件。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="1e1cf-131">適用于商務用 Skype Server 2015 Enterprise Edition 和 Standard Edition server 的組合案例各有不同。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="1e1cf-132">下列各節將更詳細地說明拓撲，包括後端資料庫伺服器的組合案例和選項。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="1e1cf-133">如需組合所有伺服器角色及資料庫的詳細資訊，請參閱 [商務用 Skype server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="1e1cf-134">前端伺服器上具有 Persistent Chat Server 組合的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="1e1cf-135">使用 Standard Edition，您可以在前端伺服器上組合持久聊天。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="1e1cf-136">這是最簡單和最基本的設定。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="1e1cf-137">您必須確定現有的前端伺服器在實體資源方面具有足夠的容量： CPU、記憶體、磁碟空間等等。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="1e1cf-138">此外，您也可以在本機 SQL Server Express 後端伺服器上組合持久的 Chat Server 後端伺服器和 Persistent Chat database (（如果已啟用) ）。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="1e1cf-139">您也可以選擇使用個別的 SQL Server 搭配專用的實例。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1e1cf-140">如果第一個 Persistent Chat Server 是以 Standard Edition 前端伺服器組合，您就無法將其他伺服器新增至 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="1e1cf-141">建議您安裝第一部伺服器做為獨立實例，以便在需要時新增更多的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="1e1cf-142">在不同的伺服器上安裝具有 Persistent Chat Server 的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="1e1cf-143">使用 Standard Edition，您可以將 Persistent Chat Server 安裝為獨立實例，並在以後必要時新增更多伺服器。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="1e1cf-144">您可以在本機 SQL Server Express 後端伺服器上組合持久聊天伺服器後端伺服器和 Persistent Chat 合規性資料庫 (（如果已啟用）) 。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="1e1cf-145">您也可以選擇使用個別的 SQL Server 搭配專用的實例。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="1e1cf-146">單一持久聊天伺服器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="1e1cf-147">搭配 Enterprise Edition，您必須在不同的電腦上安裝 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="1e1cf-148">也就是說，您無法在 Enterprise Edition 前端伺服器上組合 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="1e1cf-149">此部署需要執行 Persistent Chat Server 和合規性服務 (的個別伺服器（如果已啟用) ）。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="1e1cf-150">不過，您可以在 Enterprise Edition 前端集區的後端資料庫上，組合適用于 Persistent Chat Server 的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e1cf-151">如果您打算使用 SQL AlwaysOn 可用性群組進行 HA DR，請注意，Persistent Chat Server 資料庫不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="1e1cf-152">如果您使用後端資料庫組合 Persistent Chat 資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，也可以針對每個資料庫使用不同的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e1cf-153">主控 Persistent Chat 資料庫的伺服器可以主控其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="1e1cf-154">不過，當您考慮將 Persistent Chat 資料庫與其他資料庫組合時，請注意，如果您儲存的是少數幾個使用者的郵件，則 Persistent Chat 資料庫所需的磁碟空間會變得非常大。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="1e1cf-155">基於這個理由，我們不建議組合 Persistent Chat 資料庫與後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="1e1cf-156">下圖顯示單一 Persistent Chat Server 的拓撲的所有元件（啟用相容性 (選用) ）。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="1e1cf-157">**單一伺服器拓撲**</span><span class="sxs-lookup"><span data-stu-id="1e1cf-157">**Single Server Topology**</span></span>

![Persistent Chat Server-單一伺服器拓撲](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="1e1cf-159">具有多個 Persistent 聊天伺服器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e1cf-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="1e1cf-160">使用 Enterprise Edition，您可以部署多部伺服器拓撲，以取得更大的容量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="1e1cf-161">多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="1e1cf-162">多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="1e1cf-163">每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="1e1cf-164">多部執行 Persistent Chat Server 的電腦應該位於與商務用 Skype Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="1e1cf-165">下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="1e1cf-166">**多伺服器拓撲**</span><span class="sxs-lookup"><span data-stu-id="1e1cf-166">**Multiple Server Topology**</span></span>

![Persistent Chat Server-多部伺服器拓撲](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="1e1cf-168">多伺服器拓撲提供伺服器功能的集區。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="1e1cf-169">在伺服器集區中，Persistent Chat service 會通訊和共用資料。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="1e1cf-170">例如，您可以從系統中的任何 Persistent Chat service 取得最初發佈到某項 Persistent Chat service 的聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="1e1cf-171">任何 Persistent chat service 都可以存取透過某項 Persistent Chat service 上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="1e1cf-172">使用者可以連線至不同的持久聊天伺服器前端伺服器，也可以相互通訊。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="1e1cf-173">TCP 8011 的預設埠會將伺服器連線至伺服器集區，而 Persistent Chat service 會使用該埠自身進行通訊，或用於管理目的。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="1e1cf-174">例如，在四部伺服器的持續聊天伺服器部署中，80000使用者可以同時登入持久聊天，此負載會在每一部伺服器的20000使用者上平均分配。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="1e1cf-175">如果一部伺服器無法使用，連接至該伺服器的使用者將無法存取其 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="1e1cf-176">連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。</span><span class="sxs-lookup"><span data-stu-id="1e1cf-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

