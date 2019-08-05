---
title: 規劃常設聊天室伺服器拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '摘要: 請閱讀本主題, 瞭解商務用 Skype Server 2015 中的持續聊天伺服器元件與拓撲。'
ms.openlocfilehash: c31cb8b0ada280b52d902e975f1bacf947fd19e7
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194015"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="39775-103">規劃常設聊天室伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="39775-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="39775-104">**摘要:** 閱讀本主題以瞭解商務用 Skype Server 2015 中的持續聊天伺服器元件與拓撲。</span><span class="sxs-lookup"><span data-stu-id="39775-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="39775-105">持續聊天伺服器支援單伺服器和多伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="39775-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="39775-106">您可以在商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition Server 上安裝持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="39775-107">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="39775-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="39775-108">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="39775-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="39775-109">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="39775-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="39775-110">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="39775-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="39775-111">持續聊天伺服器元件</span><span class="sxs-lookup"><span data-stu-id="39775-111">Persistent Chat Server components</span></span>

<span data-ttu-id="39775-112">持續聊天伺服器包含下列元件:</span><span class="sxs-lookup"><span data-stu-id="39775-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="39775-113">一或多台執行持續聊天伺服器且提供下列服務的電腦:</span><span class="sxs-lookup"><span data-stu-id="39775-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="39775-114">持續聊天服務</span><span class="sxs-lookup"><span data-stu-id="39775-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="39775-115">相容性服務, 在啟用合規性時開啟</span><span class="sxs-lookup"><span data-stu-id="39775-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="39775-116">一或多個伺服器 (如果使用鏡像的話的話), 會執行 SQL Server 後端資料庫, 以託管存放聊天室內容、會議室及類別的持續聊天內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="39775-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39775-117">後端資料庫會儲存聊天記錄資料, 包括所建立之類別和持續聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="39775-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="39775-118">如果已啟用相容性, 則會使用一或多個伺服器 (如果使用鏡像的話的話), 執行 SQL Server 後端資料庫來託管持續性聊天相容性資料庫, 並儲存合規性事件和聊天內容以滿足規範的目的。</span><span class="sxs-lookup"><span data-stu-id="39775-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="39775-119">如需持續式聊天伺服器的硬體和軟體需求的詳細資訊, 請參閱商務用 skype server 2015 中[的商務用 Skype server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)與[硬體及軟體需求 (商務用 skype server](hardware-and-software-requirements.md))。</span><span class="sxs-lookup"><span data-stu-id="39775-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="39775-120">持續聊天伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="39775-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="39775-121">您可以在單一伺服器或多重伺服器池中部署持久聊天伺服器, 以及使用單一池或多池拓撲。</span><span class="sxs-lookup"><span data-stu-id="39775-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="39775-122">持續聊天伺服器支援下列拓撲:</span><span class="sxs-lookup"><span data-stu-id="39775-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="39775-123">前端伺服器上具有持續聊天伺服器 collocated 的標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="39775-124">在個別伺服器上使用持續聊天伺服器的標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="39775-125">在個別伺服器上使用單一持久聊天伺服器的企業版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="39775-126">在個別伺服器上有多個持續聊天伺服器的企業版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="39775-127">雖然您可以在標準版伺服器上部署持續性聊天伺服器, 但請注意, 效能和規模會受到影響, 且不提供高可用性選項。</span><span class="sxs-lookup"><span data-stu-id="39775-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="39775-128">因此, 建議您在標準版伺服器上部署持續聊天, 主要是為了提供概念和評估用途。</span><span class="sxs-lookup"><span data-stu-id="39775-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="39775-129">商務用 Skype Server 2015 支援各種不同的 collocation 案例, 可讓您靈活地在一部伺服器 (如果您有小型組織) 上執行多個元件, 或在不同的伺服器上執行個別元件, 以節省硬體成本。如果您的組織規模較大, 且需要伸縮性和效能, 請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="39775-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="39775-130">在決定是否要 collocate 元件之前, 您應該先考慮可伸縮性因素。</span><span class="sxs-lookup"><span data-stu-id="39775-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="39775-131">商務用 Skype Server 2015 Enterprise Edition 和 Standard Edition 伺服器的 Collocation 案例有所不同。</span><span class="sxs-lookup"><span data-stu-id="39775-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="39775-132">下列各節將更詳細說明拓撲, 包括後端資料庫伺服器的 collocation 案例和選項。</span><span class="sxs-lookup"><span data-stu-id="39775-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="39775-133">如需 collocation 所有伺服器角色和資料庫的詳細資料, 請參閱[商務用 Skype server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="39775-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="39775-134">前端伺服器上具有持續聊天伺服器 collocated 的標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="39775-135">在標準版中, 您可以在前端伺服器上 collocate 持續聊天。</span><span class="sxs-lookup"><span data-stu-id="39775-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="39775-136">這是最簡單且最基本的配置。</span><span class="sxs-lookup"><span data-stu-id="39775-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="39775-137">您必須確認現有的前端伺服器具有足夠的容量, 就像是 CPU、記憶體、磁碟空間等。</span><span class="sxs-lookup"><span data-stu-id="39775-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="39775-138">此外, 您也可以在本機 SQL Server Express 後端伺服器上, collocate 持續式聊天伺服器後端伺服器和持續性聊天規範資料庫 (如果已啟用的話)。</span><span class="sxs-lookup"><span data-stu-id="39775-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="39775-139">您也可以選擇將個別的 SQL 伺服器與專用實例搭配使用。</span><span class="sxs-lookup"><span data-stu-id="39775-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39775-140">如果第一個持久聊天伺服器是與標準版前端伺服器 collocated, 則您無法將其他伺服器新增至持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="39775-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="39775-141">建議您將第一個伺服器安裝為獨立實例, 以便日後在需要時新增更多伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="39775-142">在個別伺服器上安裝持久聊天伺服器的標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="39775-143">在標準版中, 您可以將持續性聊天伺服器安裝為獨立實例, 並視需要新增更多伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="39775-144">您可以在本機 SQL Server Express 後端伺服器上, collocate 持續式聊天伺服器後端伺服器和持續性聊天規範資料庫 (如果已啟用的話)。</span><span class="sxs-lookup"><span data-stu-id="39775-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="39775-145">您也可以選擇將個別的 SQL 伺服器與專用實例搭配使用。</span><span class="sxs-lookup"><span data-stu-id="39775-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="39775-146">具備單一持久聊天伺服器的企業版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="39775-147">在 [企業版] 中, 您必須在另一部電腦上安裝永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="39775-148">也就是說, 您無法在企業版前端伺服器上 collocate 永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="39775-149">此部署需要獨立的伺服器來執行持續聊天伺服器與合規性服務 (如果已啟用的話)。</span><span class="sxs-lookup"><span data-stu-id="39775-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="39775-150">不過, 您可以在企業版前端池的後端資料庫上, collocate [SQL Server 資料庫], 以取得持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39775-151">如果您打算針對 HA 災害復原使用 SQL AlwaysOn 可用性群組, 請注意, 持久聊天伺服器資料庫不支援此功能。</span><span class="sxs-lookup"><span data-stu-id="39775-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="39775-152">如果您 collocate 與後端資料庫的持續聊天資料庫, 您可以針對任何或所有資料庫使用單一的 SQL Server 實例, 或者您可以針對每個資料庫使用個別的 sql Server 實例。</span><span class="sxs-lookup"><span data-stu-id="39775-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39775-153">主持持久聊天資料庫的伺服器可以裝載其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="39775-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="39775-154">不過, 當您考慮將持續聊天資料庫與其他資料庫 collocating 時, 請注意, 如果您要儲存的訊息超過幾個使用者, 持久聊天資料庫所需的磁碟空間可能會變得很大。</span><span class="sxs-lookup"><span data-stu-id="39775-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="39775-155">基於這個原因, 我們不建議您 collocating 與後端資料庫的持續聊天資料庫。</span><span class="sxs-lookup"><span data-stu-id="39775-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="39775-156">下圖顯示已啟用合規性 (選用) 之單一持久聊天伺服器的拓撲所有元件。</span><span class="sxs-lookup"><span data-stu-id="39775-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="39775-157">**單一伺服器拓朴**</span><span class="sxs-lookup"><span data-stu-id="39775-157">**Single Server Topology**</span></span>

![持續聊天伺服器-單一伺服器拓撲](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="39775-159">具有多個持續聊天伺服器的企業版伺服器</span><span class="sxs-lookup"><span data-stu-id="39775-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="39775-160">在企業版中, 您可以部署多重伺服器拓撲結構, 以獲得更大的容量與可靠性。</span><span class="sxs-lookup"><span data-stu-id="39775-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="39775-161">多重伺服器拓朴與單一伺服器拓朴一樣, 只是多個伺服器主機持久的聊天伺服器, 而且可以擴大規模。</span><span class="sxs-lookup"><span data-stu-id="39775-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="39775-162">多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦 (高可用性和災害復原設定允許最多八個, 但只有四個作用中的4個作用中, 還有四個作用中的四個)。</span><span class="sxs-lookup"><span data-stu-id="39775-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="39775-163">每個伺服器可支援多達20000並行的使用者, 總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="39775-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="39775-164">多台執行持續聊天伺服器的電腦應該位於與商務用 Skype Server 及合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="39775-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="39775-165">下圖顯示多伺服器拓朴中的所有元件, 其中多台電腦執行持續聊天伺服器、選用規範服務, 以及個別的合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="39775-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="39775-166">**多個伺服器拓朴**</span><span class="sxs-lookup"><span data-stu-id="39775-166">**Multiple Server Topology**</span></span>

![持續聊天伺服器-多重伺服器拓撲](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="39775-168">多伺服器拓朴提供伺服器功能的彙集。</span><span class="sxs-lookup"><span data-stu-id="39775-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="39775-169">在伺服器池中, 持續聊天服務會與資料進行通訊和共用。</span><span class="sxs-lookup"><span data-stu-id="39775-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="39775-170">例如, 您可以從系統中的任何持續聊天服務取得最初張貼到一個持續聊天服務的聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="39775-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="39775-171">透過一個持久聊天服務上傳的檔案, 可透過任何持續聊天服務存取。</span><span class="sxs-lookup"><span data-stu-id="39775-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="39775-172">使用者可以連線至不同的持續聊天伺服器前端伺服器, 而且可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="39775-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="39775-173">TCP 8011 的預設埠會將伺服器連線到伺服器池中, 且持續聊天服務會使用它來溝通, 或針對管理目的進行通訊。</span><span class="sxs-lookup"><span data-stu-id="39775-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="39775-174">例如, 在四個伺服器持續式聊天伺服器部署中, 80000 使用者可以同時登入持續聊天, 在每個伺服器上, 都會將負載平均分佈在20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="39775-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="39775-175">如果一個伺服器無法使用, 則連接至該伺服器的使用者將無法存取永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="39775-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="39775-176">已中斷連線的使用者會自動轉移到其餘的伺服器, 直到無法還原無法使用的伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="39775-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

