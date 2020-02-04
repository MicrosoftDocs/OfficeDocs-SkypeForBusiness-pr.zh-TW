---
title: 部署 Lync Server 2013 試用版池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe36710ab0acee23af1d8b83adece108cf86c4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="f8cd1-102">部署 Lync Server 2013 試用版池</span><span class="sxs-lookup"><span data-stu-id="f8cd1-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8cd1-103">_**主題上次修改日期：** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="f8cd1-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="f8cd1-104">遷移至 Lync Server 2013 所需的第一個步驟是部署試驗區。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="f8cd1-105">試驗池是您使用 Lync Server 2010 部署來測試 Lync Server 2013 的共存位置。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="f8cd1-106">[共存] 是一個暫時的狀態，一直持續到您將所有使用者和池移至 Lync Server 2013 為止。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="f8cd1-107">當您部署試生產池時，請使用 [定義新的前端池] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="f8cd1-108">您應該在 lync Server 2010 池中部署 Lync Server 2013 試驗池中的相同功能和工作負載。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="f8cd1-109">如果您已部署封存伺服器、監視伺服器或 System Center Operations Manager 以進行封存或監視您的 Lync Server 2010 環境，而且您想要在整個遷移期間繼續進行封存或監視，您也必須部署這些您的試點環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="f8cd1-110">您部署以封存或監視 Lync Server 2010 環境的版本，將無法在 Lync Server 2013 環境中捕獲資料。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8cd1-111">下列程式討論您在整個試驗池部署程式中應考慮的功能和設定。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="f8cd1-112">此區段只會醒目提示您要考慮的重要重點，做為您的試驗池部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="f8cd1-113">如需詳細步驟，請參閱<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="f8cd1-114">**部署 Lync Server 2013 試用版池**</span><span class="sxs-lookup"><span data-stu-id="f8cd1-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="f8cd1-115">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f8cd1-116">展開樹狀結構，直到您到達**Lync Server 2013** **企業版前端池**為止。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="f8cd1-117">以滑鼠右鍵按一下 [**企業版頂層端池**]，然後選取 [**新的前端池**]。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="f8cd1-118">![拓撲產生器伺服器集區選取子功能表](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓撲產生器伺服器集區選取子功能表")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="f8cd1-119">輸入 [池 FQDN]。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-119">Enter the pool FQDN.</span></span> <span data-ttu-id="f8cd1-120">當您定義您的試驗池時，您可以選擇部署企業版的前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f8cd1-121">Lync Server 2013 不需要您的試點專案池功能與舊版池中部署的功能相符。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f8cd1-122">您為試驗池定義的「池」或「伺服器」完整功能變數名稱（FQDN）必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="f8cd1-123">它無法與目前已部署的 Lync Server 2010 池或任何其他目前部署的伺服器名稱相符。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="f8cd1-124">![[定義新前端集區精靈 FQDN] 頁面](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "[定義新前端集區精靈 FQDN] 頁面")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="f8cd1-125">在 [**選取功能**] 頁面上，選取您要用於此前端池之功能的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="f8cd1-126">例如，如果您只部署立即訊息（IM）和目前狀態功能，您可以選取 [會議] 核取方塊以允許多方 IM，但不會選取 [撥入（PSTN）會議]、[企業語音] 或 [通話許可控制] 核取方塊。因為它們代表語音、影片和共同作業會議功能。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="f8cd1-127">如需有關選取功能的其他資訊，請參閱部署檔中的[Lync server 2013 中的定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="f8cd1-128">![前端集區的 [選取功能] 頁面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端集區的 [選取功能] 頁面")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="f8cd1-129">在 [**選取 collocated 伺服器角色**] 頁面上，我們建議您 Collocate Lync server 2013 中的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="f8cd1-130">當您將舊版拓撲與 Lync Server 2013 合併時，我們會要求您先 collocate Lync Server 2010 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="f8cd1-131">在合併拓朴並設定 Lync Server 2013 轉送伺服器之後，您可以決定是否要保留 collocated 轉送伺服器，或在部署期間將轉送伺服器角色移至 Lync Server 2013 時，將它變更為獨立伺服器。程式.</span><span class="sxs-lookup"><span data-stu-id="f8cd1-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="f8cd1-132">![前端集區的 [選取組合的伺服器角色] 頁面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端集區的 [選取組合的伺服器角色] 頁面")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="f8cd1-133">在 [**將伺服器角色與此前端池建立關聯**] 頁面上的 [試驗池] 部署期間，請不要選擇 [**啟用此前端池的媒體元件要使用 Edge 池**] 選項。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="f8cd1-134">這是您將在稍後的遷移階段啟用並加入線上的功能。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="f8cd1-135">暫時清除此設定。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="f8cd1-136">![[建立伺服器角色與前端集區的關聯] 頁面](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "[建立伺服器角色與前端集區的關聯] 頁面")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="f8cd1-137">在 [**選取 Office Web Apps 伺服器**] 頁面上，按一下 [**新增**]，然後指定應用程式伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="f8cd1-138">![定義新 Office Online Server FQDN 內容](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定義新 Office Online Server FQDN 內容")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="f8cd1-139">在**定義 [封存 Sql Server store** ] 頁面上，定義 [lync server 封存與監控的 sql server store] 時，請選取舊版 lync server 2013 建立的 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="f8cd1-140">![[定義封存 SQL Server 存放區] 頁面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "[定義封存 SQL Server 存放區] 頁面")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="f8cd1-141">若要發佈拓撲，請以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="f8cd1-142">![顯示設定拓撲的拓撲產生器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "顯示設定拓撲的拓撲產生器")</span><span class="sxs-lookup"><span data-stu-id="f8cd1-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="f8cd1-143">發佈程式完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="f8cd1-144">若要安裝 configuration store 的本機複本並啟動必要的服務，請參閱部署檔中的[Lync Server 2013 設定前端伺服器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="f8cd1-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

